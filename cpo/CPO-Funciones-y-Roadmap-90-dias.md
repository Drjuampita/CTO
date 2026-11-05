# CPO: funciones y roadmap de 90 días

Nov 5, 2026 · @Juan Pablo Palma

Tu trabajo como CPO en los próximos 90 días se resume en tres cosas: lanzar con LiteAPI en cuanto la constitución esté lista, firmar e integrar un proveedor mayorista antes de febrero, y cerrar acuerdos directos con hoteles en tus primeros destinos.

## Supuestos de contexto

Tomé el contexto del Brief de Descubrimiento de Grupey. Lo que no venía ahí lo supuse y está marcado para que lo corrijas.

| Tema | Lo que asumo | Fuente |
| --- | --- | --- |
| Producto | OTA de viajes grupales: cada viajero pone su tarjeta, se cobra solo cuando el grupo está completo, con meses sin intereses | Brief |
| Estado | 100% funcional, sin operar por la constitución legal; después viene Sectur (RNT) | Brief |
| Ticket | 14,000 a 28,000 MXN por persona, 3 a 5 noches | Brief |
| Mercado | México primero, empezando por los destinos con más viajes (Cancún y Riviera Maya en primer lugar) | Brief + supuesto |
| Equipo | Tú (CPO), Báez (finanzas), un CTO; sin equipo comercial dedicado | Supuesto |
| Volumen | Cero reservas reales hoy; meta de los primeros 30 a 50 grupos en 90 días | Supuesto |
| Fecha de arranque | Constitución lista a mediados de noviembre de 2026 | Supuesto |

## Funciones de un CPO, aterrizadas a Grupey

Un CPO decide qué se construye, para quién y por qué, y responde por que el producto genere negocio. En una startup de viajes de tres personas, eso incluye también la relación con proveedores e inventario, porque el inventario es parte del producto.

| Función | Qué significa en general | Cómo se ve en Grupey hoy |
| --- | --- | --- |
| Visión y estrategia de producto | Definir hacia dónde va el producto y qué problema resuelve mejor que nadie | "Viajar en grupo sin pelear por el dinero": todo lo que no sirva a eso queda fuera del roadmap |
| Roadmap y priorización | Decidir qué se hace primero y qué se dice que no | Ordenar: lanzamiento, migración de proveedor, políticas de cancelación grupal, promociones |
| Descubrimiento con usuarios | Hablar con usuarios cada semana y validar antes de construir | Entrevistar organizadores de viajes y ver dónde se atora el grupo al poner tarjetas |
| Estrategia de inventario y proveedores | En una OTA, el proveedor define precio, cobertura y márgenes | Llevar la migración de LiteAPI a TNL, Expedia o Hotelbeds y abrir contratos directos con hoteles |
| Modelo de negocio y precios | Definir cómo gana dinero cada reserva | Markup sobre tarifa neta, costo de meses sin intereses, comisiones de pasarela |
| Métricas | Elegir pocas métricas y revisarlas cada semana | Grupos creados, grupos completados, tiempo para completar, margen por reserva |
| Experiencia y confianza | Cuidar que el producto sea fácil y seguro | Resolver "¿qué pasa si alguien cancela?" y "¿qué pasa si alguien se baja antes del cobro?" |
| Alineación del equipo | Que CTO, finanzas y marketing trabajen sobre las mismas prioridades | Una revisión semanal con el CTO y Báez, y un brief claro para la agencia de marketing |
| Cumplimiento | Asegurar que el producto pueda operar legalmente | Constitución, RNT de Sectur, aviso de privacidad, términos de cancelación y PROFECO |

Lo que no te toca como CPO: escribir el código de la integración (CTO) ni llevar la contabilidad (Báez). Sí te toca decidir qué se integra primero y qué margen necesita cada reserva.

## Migración de proveedor

La recomendación es lanzar con LiteAPI y migrar destino por destino, no de golpe. Los mayoristas grandes casi siempre piden empresa constituida, historial de ventas y un periodo de certificación, así que las primeras reservas con LiteAPI son lo que te abre la puerta con ellos.

1. **Preparar el terreno (ya):** pedirle al CTO una capa de proveedor dentro del código, para que buscar, cotizar, reservar y cancelar no dependan de LiteAPI. Así el cambio es conectar un adaptador nuevo, no reescribir la app.
2. **Abrir conversaciones con los tres a la vez:** TNL, Expedia (programa de afiliados EPS Rapid) y Hotelbeds (APItude). Pedir requisitos, modelo comercial, tarifa neta o comisión, garantía o depósito, y tiempos de certificación.
3. **Comparar con datos, no con intuición:** tomar 20 hoteles de Cancún y Riviera Maya y comparar precio, disponibilidad y políticas de cancelación entre LiteAPI y cada candidato.
4. **Firmar e integrar en sandbox:** integración y certificación con el proveedor elegido.
5. **Correr en paralelo:** mostrar el inventario del proveedor nuevo en un destino y comparar conversión, margen y errores contra LiteAPI.
6. **Cortar por destino:** cuando el nuevo proveedor gane en precio y estabilidad, se vuelve el principal ahí. LiteAPI queda como respaldo.

**El riesgo propio de Grupey:** tu flujo de "todos ponen tarjeta y luego se cobra" choca con la forma en que trabajan los mayoristas. Hay que preguntarle a cada proveedor cuánto tiempo se sostiene una tarifa, si puede cambiar de precio mientras el grupo se completa, y qué pasa si la habitación desaparece. Las preautorizaciones de tarjeta también caducan, normalmente en unos 7 días (aproximado, depende del banco y la red), así que el grupo necesita una fecha límite clara.

| Pregunta para cada proveedor | Por qué importa |
| --- | --- |
| ¿Qué requisitos legales piden (acta, RNT, RFC, estados financieros)? | Define cuándo puedes firmar |
| ¿Tarifa neta con markup libre, o comisión fija? | Define tu margen y tu libertad para promociones |
| ¿Piden depósito, garantía o prepago? | Impacta el flujo de efectivo de Báez |
| ¿Cuánto dura una cotización antes de reservar? | Clave para el cobro grupal |
| ¿Qué cobertura tienen en México y qué tan bien está el contenido en español? | Tu mercado inicial |
| ¿Cómo es la certificación y cuánto tarda? | Define la fecha de corte |
| ¿Tienen tarifas o bloques para grupos? | Puede ser tu ventaja frente a Airbnb |

No verifiqué en línea los requisitos actuales de cada proveedor; los de arriba son lo que se suele pedir y hay que confirmarlos en la primera llamada.

## Roadmap de 90 días

Cuatro fases del 10 de noviembre de 2026 al 13 de febrero de 2027. No se pasa de fase sin cumplir la condición del rombo; si la constitución se retrasa, todo el plan se recorre igual.

> El diagrama de las 4 fases y sus 3 condiciones de paso está en el [PDF](../pdfs/roadmap-y-relaciones/Grupey-CPO-Funciones-y-Roadmap-90-dias.pdf).

Del 20 de diciembre al 4 de enero el equipo baja el ritmo, pero es temporada alta: ahí la prioridad es atender a los grupos que ya reservaron.

### Fase 1 · Fundamentos (10 al 21 nov)

- [ ] Cerrar la constitución y arrancar el trámite del RNT en Sectur
- [ ] Acordar con el CTO la capa de proveedor (buscar, cotizar, reservar, cancelar)
- [ ] Escribir y enviar la solicitud a TNL, Expedia EPS Rapid y Hotelbeds
- [ ] Definir la política de cancelación grupal y qué pasa si alguien se baja
- [ ] Armar la hoja de margen por reserva con Báez
- [ ] Crear el CRM de relaciones y cargar los primeros 20 contactos

### Fase 2 · Lanzamiento controlado (24 nov al 19 dic)

- [ ] Beta privada con LiteAPI: amigos, familia y seguidores de Instagram
- [ ] Conseguir los primeros 10 grupos pagados y entrevistar a cada organizador
- [ ] Llamadas con los tres proveedores y comparación de 20 hoteles
- [ ] Visitar 10 hoteles independientes en Cancún y Riviera Maya
- [ ] Lanzar las dos promociones iniciales con marketing

### Fase 3 · Integración (5 al 30 ene)

- [ ] Elegir proveedor y firmar contrato
- [ ] Integración en sandbox y certificación
- [ ] Cerrar 3 acuerdos directos con hoteles
- [ ] Negociar costo de meses sin intereses con la pasarela

### Fase 4 · Corte (2 al 13 feb)

- [ ] Mostrar el inventario nuevo en un destino, en paralelo con LiteAPI
- [ ] Comparar conversión, margen y errores durante una semana
- [ ] Cortar el destino al nuevo proveedor y dejar LiteAPI de respaldo
- [ ] Revisar el roadmap del siguiente trimestre

## Rutina diaria y semanal

La regla para avanzar todos los días: cada día una conversación con alguien de fuera (proveedor, hotel o usuario) y una decisión de producto cerrada.

**Todos los días (unas 2 horas fijas)**

| Bloque | Duración | Qué haces |
| --- | --- | --- |
| Tablero | 15 min | Revisar grupos creados, grupos completados, errores de reserva y mensajes de soporte |
| Relaciones | 45 min | Una llamada o reunión con proveedor u hotel, y dos mensajes de seguimiento. Todo queda registrado en el CRM |
| Usuarios | 30 min | Una conversación con un organizador de viaje o revisar una sesión grabada del flujo grupal |
| Decisión | 30 min | Cerrar una decisión pendiente y escribirla en una línea para el CTO |

**Cada semana**

| Día | Ritual |
| --- | --- |
| Lunes | Prioridades de la semana con CTO y Báez (30 min): máximo tres objetivos |
| Martes y jueves | Bloque largo de proveedores y hoteles: llamadas, visitas, propuestas |
| Miércoles | Revisión de producto con el CTO: qué se entrega, qué se atora |
| Viernes | Métricas de la semana, margen por reserva y nota corta de aprendizajes; revisar contenido y campañas con marketing |

**Cada mes:** revisar el modelo de negocio con números reales, actualizar el roadmap y hacer una visita presencial a hoteles del destino principal.

## Relaciones: proveedores, hoteleros y demás

Las relaciones fuertes salen de un pipeline con seguimiento, no de reuniones sueltas. La propuesta para hoteles es simple: Grupey les lleva grupos ya pagados y confirmados de una sola vez.

| Quién | Qué quieres de ellos | Qué les ofreces | Meta a 90 días |
| --- | --- | --- | --- |
| Mayoristas (TNL, Expedia, Hotelbeds) | Contrato, tarifa neta competitiva, soporte de integración | Volumen creciente en un nicho que ellos no atienden bien: grupos | 1 contrato firmado y certificado |
| Hoteles en Cancún y Riviera Maya | Tarifas para grupos, bloques de habitaciones, beneficios para el grupo | Grupos cobrados por adelantado, ocupación en temporada baja, visibilidad en redes | 10 hoteles contactados, 3 acuerdos directos |
| Asociaciones hoteleras y de agencias del destino | Presentaciones con gerentes comerciales | Un modelo nuevo que les trae demanda | 1 presentación o evento |
| Pasarela de pagos y bancos | Mejor comisión y costo de meses sin intereses | Volumen de transacciones | Costo de MSI por plazo negociado y documentado |
| Experiencias y transporte (traslados, tours) | Comisión por venta adicional | Grupos completos que reservan juntos | 2 aliados para venta adicional |
| Creadores de contenido de viajes | Contenido y alcance en Instagram y TikTok | Viajes o comisión por grupo referido | 3 alianzas |

**Cómo trabajar cada relación**

- Un registro en el CRM por contacto, con etapa (contactado, reunión, propuesta, acuerdo) y próximo paso con fecha. Puedo armarlo en tu HubSpot si lo usas.
- Un one-pager de Grupey para hoteles y otro para proveedores, con el modelo de cobro grupal explicado en cinco líneas.
- Seguimiento a los 3 días de cada reunión y una actualización mensual a cada socio con sus números.
- Con hoteles, empieza por los independientes y boutique: deciden más rápido que las cadenas.

## Modelo de negocio y promociones

Antes de lanzar promociones hay que saber cuánto queda por reserva. Con un ticket de 14,000 a 28,000 MXN por persona, el margen se puede ir entero en comisiones de pasarela y meses sin intereses si no se calcula.

**Fuentes de ingreso a evaluar**

| Fuente | Cómo funciona | Comentario |
| --- | --- | --- |
| Markup sobre tarifa neta | Compras al mayorista y vendes con margen | La principal; depende del contrato con el proveedor |
| Comisión de hotel directo | El hotel te paga un porcentaje por reserva | Mejor margen; requiere acuerdos directos |
| Cargo por organizar | Cuota pequeña por grupo o por viajero | Probarlo después; al inicio puede frenar la conversión |
| Costo de MSI trasladado | El viajero que elige más meses absorbe parte del costo | Decidir qué plazos absorbe Grupey |
| Ventas adicionales | Traslados, tours, seguro de viaje | Margen extra sin tocar el precio del hotel |

**Primera tarea de modelo:** una hoja con el margen por reserva, de precio de venta a tarifa neta, menos pasarela, menos costo de MSI por plazo, menos cancelaciones esperadas. Esa hoja dice cuánto descuento puedes dar.

**Promociones que encajan con viajes en grupo**

- **El organizador viaja con descuento:** quien arma el grupo recibe un porcentaje de descuento o crédito si el grupo se completa. Premia justo el comportamiento que te trae clientes.
- **Grupo grande, mejor precio:** descuento escalonado a partir de 6 u 8 viajeros, financiado con tarifas de grupo de hoteles aliados.
- **Primeros 50 grupos:** precio de lanzamiento o beneficio en hotel aliado (upgrade, late checkout, cena) para conseguir casos y reseñas.
- **Referidos:** crédito para el siguiente viaje por cada nuevo organizador que traiga un viajero.
- **Temporada baja con hoteles:** paquetes de fecha fija con hoteles que necesitan ocupación. El hotel pone el descuento y tú el grupo.

La recomendación es lanzar solo dos al inicio: el descuento al organizador y el beneficio de los primeros 50 grupos.

## KPIs y preguntas abiertas

| KPI | Qué mide | Meta inicial (supuesto) |
| --- | --- | --- |
| Grupos creados por semana | Interés real | 10 por semana al final de los 90 días |
| Tasa de grupos completados | Si el cobro grupal funciona | 40% o más |
| Tiempo para completar un grupo | Fricción entre amigos | Menos de 72 horas |
| Margen neto por reserva | Si el negocio es sano | Positivo después de MSI y pasarela |
| Reservas fallidas por proveedor | Calidad del inventario | Menos de 2% |
| Relaciones activas en el CRM | Avance comercial | 20 contactos con próximo paso |

**Preguntas para ajustar el plan**

- [ ] ¿Qué es TNL exactamente y ya tienen contacto con ellos? Si ya hubo pláticas, el plan de migración se adelanta.
- [ ] ¿Para cuándo esperan tener la constitución y el RNT?
- [ ] ¿Cuántas horas a la semana tiene el CTO para la integración del nuevo proveedor?
- [ ] ¿Cuál es el primer destino: Cancún y Riviera Maya, u otro?
- [ ] ¿Qué modelo comercial tienen hoy con LiteAPI (markup propio o comisión)?
- [ ] ¿Usan algún CRM (HubSpot, Notion) para llevar las relaciones?
