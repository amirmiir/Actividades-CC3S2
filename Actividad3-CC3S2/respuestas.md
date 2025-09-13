# Actividad 3: Integración de DevOps y DevSecOps - Respuestas Teóricas

## Parte Teórica

### 1. Introducción a DevOps: ¿Qué es y qué no es?

DevOps es un nuevo paradigma de trabajo que busca unir a los equipos de desarrollo y operaciones para entregar software más rápido y confiable. A diferencia del modelo waterfall o tradicional, donde cada etapa se completa antes de pasar a la siguiente, DevOps promueve un trabajo continuo y colaborativo, lo cual implica un cambio en la mentalidad del desarrollador.

En las actividades podemos ver cómo se aplica el concepto "código a producción". Comenzamos con una aplicación simple en Python (app.py) que puede configurarse con variables de entorno. El Makefile nos permite automatizar todo el proceso desde la preparación del entorno hasta tener la aplicación funcionando con HTTPS. Esto se hace para que cualquier persona del equipo sea capaz de reproducir el mismo ambiente de trabajo facilitando la replicabilidad.

El principio "you build it, you run it" se evidencia en que no solo escribimos el código de la aplicación, sino que también nos encargamos de configurar Nginx, generar certificados TLS, y asegurar que todo funcione correctamente

Existe mucha confusión sobre qué es realmente DevOps. Muchas personas piensan que DevOps es solo usar herramientas como Docker o Jenkins, pero esto es incorrecto. DevOps es principalmente una cultura de colaboración (o un cambio de cultura de colaboración). 

Captura: Jenkins + Docker

![Automated Docker Deployment using Jenkins | TO THE NEW Blog](https://www.tothenew.com/blog/wp-ttn-blog/uploads/2015/10/docker-jenkins.png)

Los elementos clave de DevOps se resumen en el marco CALMS: Culture, Automation, Lean, Measurement, and Sharing. Es decir, cultura de colaboración, automatización de procesos, principios lean para eliminar desperdicios, medición y métricas para tomar decisiones, y compartir conocimiento entre equipos. 

Captura: Ciclo DevOps

![Moving to A Cloud DevOps Culture – The CALMS Framework ...](https://www.capgemini.com/fi-en/wp-content/uploads/sites/26/2022/11/DevOps.png)

### 2. Marco CALMS en acción

El marco CALMS nos ayuda a entender cómo implementar DevOps de manera efectiva, y el laboratorio nos da ejemplos concretos de cada elemento.

La Cultura se manifiesta en diseñar un proyecto para que cualquier persona pueda ejecutarlo, sin importar si viene de desarrollo u operaciones. La documentación detallada y los comandos claros fomentan la colaboración. Todos comparten la responsabilidad de entender tanto el código como la infraestructura.



### 3. Visión cultural de DevOps y paso a DevSecOps



### 4. Metodología 12-Factor App

