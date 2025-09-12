# Actividad 2: HTTP, DNS, TLS y 12-Factor - Reporte

## Objetivo
Practicar despliegues seguros y reproducibles combinando aplicación (HTTP), resolución de nombres (DNS), cifrado en tránsito (TLS) y buenas prácticas 12-Factor (variables de entorno, port binding y logs a stdout).

## 1. HTTP: Fundamentos y herramientas

### Configuración inicial
- Puerto configurado via variable de entorno: `PORT=8080`
- Mensaje personalizado: `MESSAGE="Hola CC3S2"`
- Versión de release: `RELEASE="v1"`

### Evidencias curl
```bash
# Inspección básica con curl
curl -v http://127.0.0.1:8080/

# Prueba método POST
curl -i -X POST http://127.0.0.1:8080/
```

### Logs en stdout
```
[Incluir aquí extractos de los logs de la aplicación]
```

### Puertos abiertos
```bash
ss -ltnp | grep :8080
```

## 2. DNS: nombres, registros y caché

### Configuración hosts
Agregado a `/etc/hosts`:
```
127.0.0.1 miapp.local
```

### Verificación resolución DNS
```bash
dig +short miapp.local
getent hosts miapp.local
```

### Análisis TTL
```bash
dig example.com A +ttlunits
```

**Pregunta guía:** Diferencia entre `/etc/hosts` y zona DNS autoritativa:
- `/etc/hosts` es resolución local estática en el sistema
- Zona DNS autoritativa es servidor que responde queries DNS para dominio específico
- `/etc/hosts` sirve para laboratorio porque permite mapeo local sin configurar DNS

## 3. TLS: seguridad en tránsito con Nginx

### Certificado autofirmado
```bash
# Generación de certificado (comando usado)
```

### Configuración Nginx
Snippet clave del server block:
```nginx
server {
    listen 443 ssl;
    server_name miapp.local;
    
    ssl_certificate /path/to/cert.crt;
    ssl_certificate_key /path/to/cert.key;
    
    location / {
        proxy_pass http://127.0.0.1:8080;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
        proxy_set_header Host $host;
    }
}
```

### Validación TLS handshake
```bash
openssl s_client -connect miapp.local:443 -servername miapp.local -brief
curl -k https://miapp.local/
```

### Evidencias de puertos y logs
```bash
ss -ltnp | grep -E ':(443|8080)'
journalctl -u nginx -n 50 --no-pager
```

## 4. 12-Factor App: port binding, configuración y logs

### Port binding
Evidencia que la app escucha en puerto configurado por variable de entorno.

### Configuración por entorno
Pruebas con diferentes valores de `MESSAGE` y `RELEASE`.

### Logs a stdout
Redirección a archivo y explicación de por qué no se configura log file en la app.

## 5. Operación reproducible

### Comandos documentados
| Comando | Resultado esperado |
|---------|-------------------|
| `make prepare` | Configuración inicial |
| `make run` | Ejecutar aplicación |
| `make nginx` | Configurar Nginx |
| `make check-http` | Verificar HTTP |
| `make check-tls` | Verificar HTTPS |

## Respuestas a preguntas guía

### 1. HTTP: Idempotencia
Explicación de idempotencia de métodos HTTP y su impacto en retries/health checks.

### 2. DNS: hosts vs producción
Por qué hosts es útil para laboratorio pero no para producción, influencia del TTL.

### 3. TLS: SNI
Rol de SNI en el handshake y demostración con openssl s_client.

### 4. 12-Factor: logs y configuración
Por qué logs a stdout y config por entorno simplifican contenedores y CI/CD.

### 5. Operación: troubleshooting
Qué muestra `ss -ltnp` vs `curl`, cómo usar journalctl para diagnóstico.

## Mejoras incrementales

### Logs estructurados JSON
Ejemplo de logs estructurados y ventajas para parsing.

### Script make end-to-end
Descripción del flujo completo automatizado.

### Systemd (si aplica)
Configuración de unidad systemd y evidencias.