# Actividad 3: Integración de DevOps y DevSecOps con HTTP, DNS, TLS y 12-Factor App

## Índice de Evidencias

### Parte Teórica
- [Respuestas Teóricas](respuestas.md)
- [Informe Resumido (PDF)](informe-actividad3.pdf)

### Parte Práctica

**1. Automatización con Make**
- Tabla de rastreo de objetivos → `evidencias/makefile-rastreo.md`
- Evidencias de idempotencia → `evidencias/makefile-outputs/`

**2. 12-Factor Build/Release/Run**
- Variables de entorno y efectos → `evidencias/12factor-variables.md`
- Artefacto inmutable con git archive → `evidencias/build-artifacts/`

**3. HTTP como contrato**
- Análisis de cabeceras y SLO → `evidencias/http-contract.md`
- Mediciones de latencia → `evidencias/http-latency/`

**4. DNS y caché**
- Configuración Netplan y TTL → `evidencias/dns-cache.md`
- Comparaciones de consultas DNS → `evidencias/dns-queries/`

**5. TLS y seguridad**
- Certificados y configuración Nginx → `evidencias/tls-security.md`
- Gate de CI/CD para TLS v1.3 → `evidencias/cicd-gate.md`

**6. Puertos y procesos**
- Análisis ss/lsof → `evidencias/ports-processes.md`
- Integración systemd → `evidencias/systemd-integration/`

**7. Integración CI/CD**
- Script de verificación → `evidencias/cicd-verification.sh`
- Resultados antes/después → `evidencias/cicd-results/`

**8. Escenario integrado**
- Postmortem del incidente → `evidencias/postmortem.md`
- Runbook de procedimientos → `evidencias/runbook.md`
- Tabla 12-Factor App → `evidencias/12factor-table.md`

### Archivos del Laboratorio
- Archivos modificados del laboratorio copiados y adaptados

### Estado de la Actividad
- [ ] Parte teórica completa
- [ ] Parte práctica completa  
- [ ] Informe PDF generado
- [ ] Evidencias documentadas