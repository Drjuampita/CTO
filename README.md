# CTO

Funciones personales de desarrollo de producto para Grupey. Lo más importante es el roadmap para establecer relaciones con proveedores, propuestas de producto y ejecución efectiva.

## Funciones de un CPO en Grupey

Un CPO decide qué se construye, para quién y por qué, y responde por que el producto genere negocio. En una startup de viajes de tres personas eso incluye la relación con proveedores e inventario, porque el inventario es parte del producto.

| Función | Qué significa en general | Cómo se ve en Grupey hoy |
| --- | --- | --- |
| Visión y estrategia de producto | Definir hacia dónde va el producto y qué problema resuelve mejor que nadie | "Viajar en grupo sin pelear por el dinero": lo que no sirva a eso queda fuera del roadmap |
| Roadmap y priorización | Decidir qué se hace primero y a qué se dice que no | Ordenar: lanzamiento, migración de proveedor, políticas de cancelación grupal, promociones |
| Descubrimiento con usuarios | Hablar con usuarios cada semana y validar antes de construir | Entrevistar organizadores de viajes y ver dónde se atora el grupo al poner tarjetas |
| Estrategia de inventario y proveedores | En una OTA, el proveedor define precio, cobertura y márgenes | Llevar la migración de LiteAPI a TNL, Expedia o Hotelbeds y abrir contratos directos con hoteles |
| Modelo de negocio y precios | Definir cómo gana dinero cada reserva | Markup sobre tarifa neta, costo de meses sin intereses, comisiones de pasarela |
| Métricas | Elegir pocas métricas y revisarlas cada semana | Grupos creados, grupos completados, tiempo para completar, margen por reserva |
| Experiencia y confianza | Cuidar que el producto sea fácil y seguro | Resolver "¿qué pasa si alguien cancela?" y "¿qué pasa si alguien se baja antes del cobro?" |
| Alineación del equipo | Que CTO, finanzas y marketing trabajen sobre las mismas prioridades | Revisión semanal con el CTO y Báez, y un brief claro para la agencia de marketing |
| Cumplimiento | Asegurar que el producto pueda operar legalmente | Constitución, RNT de Sectur, aviso de privacidad, términos de cancelación y PROFECO |

**Lo que no le toca al CPO:** escribir el código de la integración (CTO) ni llevar la contabilidad (Báez). Sí le toca decidir qué se integra primero y qué margen necesita cada reserva.

## Qué es Grupey

OTA de viajes grupales para México: cada viajero pone su tarjeta y se cobra solo cuando el grupo está completo, con meses sin intereses. Ticket de 14,000 a 28,000 MXN por persona (3 a 5 noches). Primer destino: Cancún y Riviera Maya.

- **Estado:** plataforma de reservas hoteleras 100% funcional, pendiente de operar hasta tener la constitución legal (después, RNT ante Sectur).
- **Proveedor actual:** LiteAPI. Funciona bien, pero es temporal.
- **Meta:** migrar a un mayorista (TNL como primera opción; Expedia EPS Rapid y Hotelbeds APItude como alternativas), destino por destino y con LiteAPI como respaldo.
- **Equipo:** Pablo (CPO), Báez (finanzas) y CTO.

## Documentos

| Documento | Qué contiene |
| --- | --- |
| [Roadmap de relaciones al 15 de diciembre](pdfs/roadmap-y-relaciones/Grupey-Roadmap-Relaciones-15dic.pdf) (PDF) | Plan de 5 semanas (10 nov al 15 dic de 2026) para cerrar proveedor mayorista, hoteles y aliados. Metas, plan semana por semana, rutina diaria, preguntas para proveedores y el bloque de constitución. |
| [CPO: funciones y roadmap de 90 días](cpo/CPO-Funciones-y-Roadmap-90-dias.md) ([PDF](pdfs/roadmap-y-relaciones/Grupey-CPO-Funciones-y-Roadmap-90-dias.pdf)) | Funciones del CPO aterrizadas a Grupey, plan de migración de proveedor, roadmap de 4 fases (10 nov 2026 al 13 feb 2027), rutina, relaciones, modelo de negocio, promociones, KPIs y preguntas abiertas. |
| [Requisitos legales para operar como OTA](pdfs/legal-y-estructura/Grupey-Requisitos-Legales-OTA.pdf) (PDF) | Checklist priorizado de 16 requisitos (SAT, ISH, RNT, NOM-010-TUR, PROFECO, datos personales, PCI, marca) y lo que piden los mayoristas para dar de alta. Asume México. |
| [Holding, impuestos y empleados](pdfs/legal-y-estructura/Grupey-Holding-Impuestos-Empleados.pdf) (PDF) | Análisis de la estructura holding extranjera + SAPI sin empleados en México: doble tributación, IMSS, opciones de estructura y cómo pagar a los fundadores. |

## Apartado de PDFs

Todos los PDFs viven en [`pdfs/`](pdfs/), separados por tema:

- **[Roadmap y relaciones](pdfs/roadmap-y-relaciones/)**
  - [Roadmap de relaciones al 15 de diciembre](pdfs/roadmap-y-relaciones/Grupey-Roadmap-Relaciones-15dic.pdf)
  - [CPO: funciones y roadmap de 90 días](pdfs/roadmap-y-relaciones/Grupey-CPO-Funciones-y-Roadmap-90-dias.pdf)
- **[Legal y estructura](pdfs/legal-y-estructura/)**
  - [Requisitos legales para operar como OTA](pdfs/legal-y-estructura/Grupey-Requisitos-Legales-OTA.pdf)
  - [Holding, impuestos y empleados](pdfs/legal-y-estructura/Grupey-Holding-Impuestos-Empleados.pdf)

Los documentos editables en markdown siguen en [`cpo/`](cpo/).

## Foco actual: relaciones al 15 de diciembre

Para el 15 de diciembre Grupey debe tener **1 contrato firmado con un mayorista** con la integración arrancada, **3 acuerdos directos con hoteles** y un **pipeline de 30 relaciones activas**, todas con próximo paso y fecha.

| Semana | Fechas | Foco |
| --- | --- | --- |
| 1 · Base | 10 al 14 nov | CRM, one-pagers, solicitud formal a TNL, Expedia y Hotelbeds; capa de proveedor con el CTO; hoja de margen con Báez |
| 2 · Contacto | 17 al 21 nov | Llamadas con los 3 proveedores, 15 hoteles contactados, asociaciones, costos de MSI con la pasarela |
| 3 · Terreno | 24 al 28 nov | Visitas a 8 hoteles, comparación de 20 hoteles entre LiteAPI y cada candidato, aliados y creadores |
| 4 · Negociación | 1 al 5 dic | Elegir proveedor, propuestas escritas a hoteles, diseñar las 2 promos de lanzamiento |
| 5 · Cierre | 8 al 15 dic | Contrato y sandbox, 3 acuerdos con hoteles, MSI acordado, plan de enero |

**Rutina:** 2 horas diarias fijas (relaciones, preparación, producto y registro en CRM). Lunes prioridades con CTO y Báez, martes y jueves llamadas y visitas, viernes revisión del pipeline.

## Roadmap de 90 días

1. **Fundamentos** (10 al 21 nov): constitución y RNT, capa de proveedor, solicitudes a mayoristas, política de cancelación grupal, hoja de margen, CRM.
2. **Lanzamiento controlado** (24 nov al 19 dic): beta privada con LiteAPI, primeros 10 grupos pagados, comparación de proveedores, visitas a hoteles, 2 promociones iniciales.
3. **Integración** (5 al 30 ene): firmar proveedor, sandbox y certificación, 3 acuerdos directos con hoteles, costo de MSI negociado.
4. **Corte** (2 al 13 feb): inventario nuevo en paralelo en un destino, comparar conversión y margen, cortar destino y dejar LiteAPI de respaldo.

## Modelo de negocio y promociones

- **Ingresos a evaluar:** markup sobre tarifa neta (principal), comisión de hotel directo, cargo por organizar, costo de MSI trasladado y ventas adicionales (traslados, tours, seguro).
- **Primera tarea:** hoja de margen por reserva (precio de venta, tarifa neta, pasarela, MSI por plazo, cancelaciones esperadas).
- **Promociones de lanzamiento:** descuento al organizador del grupo y beneficio para los primeros 50 grupos. Después: descuento por grupo grande, referidos y paquetes de temporada baja con hoteles.

## Bloque aparte: constitución y legales

Va en paralelo y no es parte del trabajo de relaciones, pero los contratos dependen de él (los mayoristas y varios hoteles piden empresa constituida). Fecha límite sugerida: **1 de diciembre**.

- [ ] Constitución de la empresa y RFC
- [ ] Cuenta bancaria empresarial
- [ ] Registro Nacional de Turismo (RNT) ante Sectur
- [ ] Aviso de privacidad, términos y condiciones y política de cancelación grupal (PROFECO)
- [ ] Contrato con la pasarela de pagos a nombre de la empresa

Si la constitución no está lista para entonces, la semana 5 se usa para dejar los contratos listos para firma, y la firma se recorre al día en que salga el acta.

## Supuestos por confirmar

Primer destino Cancún y Riviera Maya; equipo de tres; requisitos de proveedores por confirmar en la primera llamada; volumen meta de 30 a 50 grupos en 90 días. Fuente de contexto: Brief de Descubrimiento de Grupey (2 de noviembre de 2026).
