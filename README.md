# API Backend Despachos - Innovatech Chile 🇨🇱

Este repositorio contiene el microservicio encargado del control, asignación y seguimiento de la logística de despachos.

## 🛠️ Especificaciones Técnicas
- **Tecnología Base:** Java 17 / Spring Boot / Maven
- **Seguridad (IE2):** Ejecución aislada bajo el usuario No-Root `api-user`.
- **Optimización (IE2):** Proceso de compilación desacoplado del entorno de ejecución mediante Docker Multi-stage.
- **Puerto de Escucha:** `8082`

## 🌐 Integración de Entornos (IE7)
El microservicio opera dentro de una red aislada (`private_net`) para comunicarse con la base de datos de manera segura, exponiendo su puerto únicamente a la red de servicios internos del orquestador.