---
layout: default
title: Inicio
nav_order: 1
description: "Documentacion del microservicio de pagos de SocioUnido"
---

# Microservicio de pagos

Microservicio encargado de la gestión, procesamiento y auditoría de los pagos y transacciones financieras de "SocioUnido".

## Utilidad y funcionalidad

El microservicio de pagos está diseñado para manejar las siguientes responsabilidades clave:

* **Procesamiento de transacciones:** Centraliza y procesa la lógica de cobro asociada a cuotas sociales, inscripciones a disciplinas, reservas de instalaciones y venta de entradas.
* **Historial y conciliación:** Registra de manera inmutable el estado de cada transacción financiera, permitiendo mantener un historial detallado para la posterior auditoría y conciliación contable.
* **Notificación de eventos:** Trabaja de forma asíncrona publicando eventos en el message broker para notificar a otros módulos (como el de Analíticas o el Club) sobre la confirmación o rechazo de un pago.

## ¿Qué vas a encontrar en esta página?

A continuación, se detalla toda la información técnica, arquitectónica y organizativa sobre esta implementación en particular:

* 🔌 **[Endpoints](endpoints.html):** Documentación estática y detallada de la API, ideal para consultar integraciones.
* 🛠️ **[Justificación tecnológica](justificacion.html):** El porqué de los lenguajes y frameworks elegidos, nuestro pipeline de CI/CD, la estrategia de testing y métricas de Code Coverage definidas.
* 🏗️ **[Arquitectura y diagramas](diagramas.html):** Representación visual de la arquitectura del microservicio utilizando el modelo C4.
* 📊 **[Métricas de la implementación](metricas.html):** Estadísticas del desarrollo, cantidad de commits, Pull Requests y distribución del trabajo en el equipo.
