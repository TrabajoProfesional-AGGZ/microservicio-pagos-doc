---
layout: default
title: Justificación tecnológica
nav_order: 3
---

# 🛠️ Justificación tecnológica

En esta sección documentamos las decisiones técnicas tomadas para la construcción del microservicio de pagos, asegurando que cada herramienta elegida aporte valor real al desarrollo y mantenimiento del producto.

## Lenguajes y frameworks

Para este microservicio, cuyo dominio requiere un estricto control transaccional y fiabilidad, la selección tecnológica se basó en los siguientes pilares:

* **Python:** Elegido por su legibilidad, eficiencia en el desarrollo y robustez para modelar la lógica de negocio financiera.
* **FastAPI:** Seleccionado como framework web por su alto rendimiento, soporte asíncrono y la validación nativa de esquemas de datos. Su capacidad para autogenerar la documentación Swagger/OpenAPI resulta vital para que los equipos de frontend y móvil integren las pasarelas de pago sin fricciones.
* **SQLAlchemy y Alembic:** Implementados como ORM y gestor de migraciones[cite: 8]. En un dominio financiero, asegurar la integridad relacional de la base de datos es innegociable, y estas herramientas nos proporcionan un control total sobre las transacciones y la evolución del esquema de datos.
* **Redis:** Utilizado para la gestión de caché y como sistema de mensajería (message broker) para orquestar eventos asíncronos[cite: 8]. Esto garantiza que los procesos pesados no bloqueen el flujo de pago del usuario.
* **Pytest:** Nuestro framework de pruebas para validar rigurosamente los cálculos de montos, la lógica de estados de pago y prevenir regresiones críticas.
* **Docker y Docker Compose:** La contenerización es indispensable en nuestra arquitectura. Nos permite aislar el microservicio y garantizar la paridad exacta entre entornos (desarrollo, *staging* y producción).

## Integración y despliegue continuo (CI/CD)

La implementación de pipelines de CI/CD es fundamental en el microservicio para garantizar entregas ágiles y seguras. Nos permite automatizar la ejecución de pruebas y el despliegue a los distintos entornos, reduciendo el error humano y acelerando el *time-to-market*.

## Pruebas unitarias y Code Coverage

Para asegurar la robustez y estabilidad del código, mantenemos un estándar estricto de calidad:

* Se ha implementado una gran cantidad de pruebas unitarias cubriendo los casos de uso principales y casos borde.
* Mantenemos un **estricto nivel de Code Coverage** (cobertura de código) fijado en un mínimo del **90%**, el cual es validado automáticamente en cada Pull Request mediante nuestro pipeline.

## Documentación integral

Utilizamos **JustTheDocs** para mantener esta documentación viva, versionada junto con el código y fácilmente accesible para cualquier miembro del equipo. Esto centraliza el conocimiento y reduce los cuellos de botella en la comunicación.
