# Iniciativa E2E — Migración de clientes Movistar TV / TMA a Flow

**Versión:** 0.1 para Discovery y validación  
**Fecha de corte:** 29/09/2026  
**Tipo:** Producto / Tecnología / Operación — Mixta  
**Estado general:** Discovery en curso; diseño funcional y técnico parcial; DoR E2E no alcanzado.  

## Convención de evidencia

- **CONFIRMADO:** surge de los blueprints, transcripciones, distribución funcional BSS o definición expresa de la Delivery Lead.
- **SUGERIDO / A VALIDAR:** participación o solución coherente con la capacidad, pero aún no confirmada para esta iniciativa.
- **GAP:** la iniciativa necesita la definición, owner o entrega y todavía no está resuelta.
- **NO DETERMINADO:** la información disponible no permite concluir.

---

# 1. Problema / oportunidad

La compañía necesita migrar los clientes residenciales de Movistar TV / TMA hacia Flow, contemplando seis caminos operativos:

1. Sin deco y sin OTT-Pack.
2. Sin deco y con OTT-Pack.
3. Con deco Linux/incompatible y sin OTT-Pack.
4. Con deco Android TV reflasheable y sin OTT-Pack.
5. Con deco Linux/incompatible y con OTT-Pack.
6. Con deco Android TV reflasheable y con OTT-Pack.

La migración atraviesa producto CRM, catálogo, identidad, dispositivos, pedidos, fulfillment, provisión, activación, OTT, facturación, atención y baja del legado. Actualmente existen diseños y trabajos por frente, pero no se encontró evidencia de una única iniciativa Jira E2E con owner, cronograma, épicas vinculadas y criterios de cierre consolidados.

**Fuentes:** `Migra TMA(1).pdf`, págs. 10–13; `Flujo proceso de envio de decos TMA.pdf`; `Impact_Scan_E2E_Migracion_Movistar_TV_a_Flow.md`, secciones 8–15.

---

# 2. Objetivo

Migrar los clientes Movistar TV / TMA a Flow de forma controlada y trazable, asegurando:

- construcción y evolución del producto Flow desde CRM;
- continuidad del servicio durante la transición;
- tratamiento diferencial por tipo de dispositivo y OTT-Pack;
- activación basada en eventos de negocio confiables;
- ausencia de doble facturación;
- cierre y baja TMA únicamente después del gate correspondiente;
- recuperación operativa ante fallas parciales;
- trazabilidad por cliente, cuenta, producto, orden, dispositivo, OTT y ola.

---

# 3. Beneficio esperado

## ¿Qué gana la compañía?

| Beneficio | Resultado esperado | Estado / medición requerida |
|---|---|---|
| Reducción de costos | Disminuir costos de operación y mantenimiento asociados a la convivencia TMA–Flow y al soporte de plataformas/productos duplicados. | **A VALIDAR:** falta baseline y objetivo porcentual. |
| Simplificación tecnológica | Unificar progresivamente la oferta de TV sobre Flow y reducir dependencias del legado TMA. | **CONFIRMADO** como propósito general de la migración; fecha y alcance del apagado aún deben validarse. |
| Protección de ingresos | Mantener la continuidad de facturación durante la migración, evitando pérdida de ingresos, doble cobro y compensaciones. | **CONFIRMADO** como necesidad; falta estimar impacto económico. |
| Incremento de ingresos | Habilitar evolución de ofertas, packs y OTT sobre Flow. | **SUGERIDO / A VALIDAR:** no existe objetivo incremental cuantificado en las fuentes. |
| Mejora de experiencia cliente | Reducir fricción de acceso, preservar credenciales cuando corresponda y ofrecer una experiencia unificada en Flow. | **CONFIRMADO** como resultado buscado; faltan baseline y meta CX/NPS. |
| Eficiencia operativa | Contar con estados, eventos, conciliación y colas de excepción comunes para olas, dispositivos y partners. | **GAP:** solución y ownership E2E pendientes. |
| Cumplimiento regulatorio | Garantizar comunicaciones, consentimiento, privacidad, facturación y tratamiento de reclamos según las reglas aplicables. | **A VALIDAR:** no se encontró evidencia de que la iniciativa sea regulatoria ni una exigencia específica. |

> No se incorpora todavía “reducir 30% los costos” como compromiso: no existe baseline ni aprobación que permita confirmar ese porcentaje.

---

# 4. Alcance

## ✅ Incluye

- Clientes B2C residenciales incluidos en los seis caminos definidos.
- Mapping de productos y planes Movistar TV / TMA → Flow.
- Construcción y evolución del producto Flow desde CRM/BSS.
- Migración o adecuación de credenciales e identidad, según el escenario aprobado.
- Migración o preservación de perfiles, cuando la solución y los datos de origen lo permitan.
- Migración/alta de OTT-Packs y entitlements por partner.
- Alta y estados del producto Flow en CRM.
- Tratamiento de clientes Solo-App.
- Recambio físico de decos Linux/no compatibles mediante delivery, retiro o visita, sujeto a reglas de elegibilidad.
- Reflash OTA de decos Android TV compatibles.
- Asociación cliente–producto–orden–serial.
- Provisión y activación del servicio/dispositivo.
- Facturación Flow y prevención de doble cobro con TMA.
- Baja/cierre del producto TMA después del gate acordado.
- Comunicaciones, atención, excepciones, observabilidad, conciliación y soporte de la migración.

## ❌ No incluye — propuesta a validar

- Clientes corporativos/B2B, salvo decisión explícita posterior.
- Sustitución de dispositivos que no pertenezcan al universo TMA definido.
- Evoluciones generales de Flow, BSS u OSS no necesarias para esta migración.
- Migración de OTT o partners no incluidos en el catálogo y alcance aprobado.
- Renovaciones tecnológicas de plataforma sin relación demostrada con el E2E.

> **Corrección importante:** “cambio de decodificadores” no puede figurar fuera de alcance en esta iniciativa, porque los caminos Linux/incompatibles requieren recambio y constituyen una parte central del trabajo.

---

# 5. Métricas de éxito

Los valores siguientes deben aprobarse durante Discovery. Se separa la métrica de su objetivo para no convertir ejemplos en compromisos.

| Métrica | Definición propuesta | Objetivo |
|---|---|---|
| Clientes migrados exitosamente | Clientes con Flow utilizable, estado CRM correcto, facturación conciliada y gate de cierre cumplido / clientes ejecutados en la ola. | **TBD**. Aspiración: 100% de los clientes elegibles ejecutados; requiere definición de remanentes/excepciones. |
| Migraciones sin intervención manual | Clientes finalizados sin reparación manual / clientes migrados. | **TBD** |
| Reclamos atribuibles a migración | Reclamos asociados a la migración / clientes migrados. | **Propuesta a validar:** <2%. |
| Errores de login/identidad | Clientes con falla de acceso / clientes que intentaron primer ingreso. | **Propuesta a validar:** <1%. |
| Activación de deco | Decos REGISTRADOS/INSTALADOS y activos / decos entregados o intervenidos. | **TBD** |
| Entitlements OTT conciliados | Packs activos y conciliados / packs incluidos en la ola. | **TBD por partner** |
| Doble facturación | Clientes con cargo simultáneo incorrecto TMA–Flow / clientes facturados. | **Objetivo propuesto:** 0 casos; sujeto a validación Billing. |
| Rollback técnico ATV | Dispositivos revertidos a TMA / dispositivos reflasheados. | **No debe fijarse en 0:** el rollback es un mecanismo de protección; establecer umbral y causa aceptable. |
| Rollback comercial/E2E | Clientes revertidos después de activación comercial / clientes ejecutados. | **TBD** |
| Tiempo de recuperación | Tiempo desde detección de falla hasta resolución o rollback. | **TBD por severidad** |
| Clientes pendientes fuera de SLA | Clientes sin estado terminal después del timeout / clientes ejecutados. | **TBD** |
| Baja TMA segura | Bajas TMA con gate completo / bajas ejecutadas. | **Objetivo propuesto:** 100%. |

---

# 6. Roadmap

| Fase | Estado verificable | Salida necesaria para cerrar la fase |
|---|---|---|
| Discovery | **En curso / avanzado por frentes** | Alcance firmado, seis caminos, owner E2E, RACI, reglas de negocio, dependencias y preguntas P0 cerradas. No puede marcarse “Completo” mientras continúen abiertos agenda–OT–API BSS, Billing Gate, eventos, OTT, no respuesta y ownership. |
| Diseño funcional | **En curso** | AS-IS/TO-BE por camino, máquina de estados, decisiones de contacto, delivery/visita, reflash, OTT, billing y baja. |
| Diseño técnico | **En curso / parcial** | Contratos API/eventos, secuencias, idempotencia, errores, observabilidad, seguridad, volumen y rollback. |
| Refinamiento | **Pendiente de consolidación E2E** | Épicas/historias vinculadas, criterios de aceptación, estimaciones y dependencias confirmadas. |
| Desarrollo | **No determinado globalmente** | Existen trabajos parciales mencionados, pero no hay evidencia consolidada de inicio/fin por épica y equipo. |
| UAT / pruebas E2E | **Pendiente** | Estrategia, ambientes, datos, casos por camino, simuladores partner, gates de entrada/salida. |
| Piloto / Friendly | **Pendiente** | Cohorte, capacidad, observabilidad, soporte, stop-the-line y rollback. |
| Producción por olas | **Pendiente** | Go/no-go, calendario, capacidad por canal/equipo/partner y criterios de cierre. |
| Apagado / cierre TMA | **Pendiente / fecha no confirmada** | Remanentes resueltos, conciliación final, baja técnica/comercial y acta de cierre. |

---

# 7. Distribución funcional BSS revisada

La distribución funcional confirma que **BSS-B2C no equivale solamente al squad Entretenimiento**. Para esta iniciativa deben diferenciarse capacidades BSS y sus dependencias.

| Capacidad / squad BSS | Responsabilidad documentada | Participación en la iniciativa | Estado |
|---|---|---|---|
| Conectividad y Entretenimiento — Entretenimiento | Evolución de productos y experiencias de entretenimiento desde BSS/CRM. | Construcción del producto Flow desde CRM, mapping, estados comerciales, procesos masivos de migración, recambio y OTT desde la mirada de producto. | **CONFIRMADO** |
| PyS | ABM de catálogo, BAU, calidad, performance y soporte a evolutivos; aparecen Catálogo, CBS, EPC y BSCS. | Catálogo/SKU/planes/compatibilidades requeridos por la migración. | **SUGERIDO / A VALIDAR para esta iniciativa** |
| Apificación CRM / Integración Legados y Procesos Masivos | APIs CRM y procesos masivos/integraciones legadas. | APIs o archivos masivos, relación TMA–Flow y orquestación de altas/actualizaciones. | **SUGERIDO / A VALIDAR** |
| Provisión — OM | Ciclo de vida de pedidos. | Orden de producto/deco, estados, idempotencia, cancelación y cierre. | **SUGERIDO / A VALIDAR en solución final** |
| Provisión — SAM Backend Web | Activación de dispositivos y operatividad para journeys. | Activación del deco o integración con el evento de activación. | **SUGERIDO / A VALIDAR** |
| Provisión — MEC Delivery | Procesos de delivery gestionados mediante MEC. | Envío, estados logísticos y entrega en recambio Linux. | **SUGERIDO / A VALIDAR** |
| Provisión — SOM / FlowOne / InstantLinks | Solicitudes de servicio en plataformas de acceso. | Solicitud/provisión del servicio Flow según el diseño técnico. | **SUGERIDO / A VALIDAR** |
| Facturación Front / Back | Facturación orientada al cliente y procesos financieros, impositivos y contables. | Inicio de cobro, factura, prorrateo, doble facturación y compensaciones. | **CONFIRMADO como capacidad necesaria; owner específico a validar** |
| Tasación y Mediación / Apificación CBS | Tasación, mediación y APIs necesarias para productos. | Evaluar si el nuevo producto, los decos o packs requieren cambios de tasación/APIs CBS. | **SUGERIDO / A VALIDAR** |
| Cobranzas CBS / Morosidad CBS | Cobranza, pagos, mora, suspensión y reconexión. | Impact Scan obligatorio para continuidad del ciclo de vida, aunque no se demostró aún desarrollo requerido. | **SUGERIDO / A VALIDAR** |
| Aseguramiento E2E — Conciliaciones / Legados | Inconsistencias, causa raíz y legados. | Conciliación CRM/BSS/TMA/Flow, detección de parciales y derivación. | **SUGERIDO / A VALIDAR** |

**Fuente:** `DistribucionFuncionalidades - Tribu BSS (v 2026)(1).xlsx`, hoja `Organización Tribu BSS`, consolidada en `V0_Mapa_Maestro_Discovery_Dependencias_E2E.md`, sección 5.

---

# 8. Responsabilidad confirmada de Tribu Flow — Dispositivos

La Delivery Lead confirma que el **reflasheo de decos Android TV es responsabilidad de Dispositivos de Flow, dentro de la Tribu Flow**.

## Dispositivos de Flow desarrolla / opera

- compatibilidad de modelos y versiones;
- firmware/imagen Flow;
- distribución OTA;
- ejecución del reflash por lotes;
- telemetría OK / fail / pending;
- snapshot y rollback técnico a Movistar TV;
- calidad y performance del dispositivo;
- runbook técnico y stop-the-line.

## BSS Entretenimiento desarrolla / gestiona

- producto y plan Flow desde CRM;
- mapping del producto origen–destino;
- estado previo a la activación;
- consumo del evento de resultado/primer encendido;
- actualización del estado comercial del producto;
- coordinación con el Billing Gate y la baja TMA.

> BSS Entretenimiento **no desarrolla el reflash**. Tampoco debe asumir como propia la plataforma OTA o el rollback técnico.

**Evidencia:** definición expresa de la Delivery Lead del 29/09/2026; `Playbook Flow(1).pdf`, p. 10, dominio Dispositivos; `Migra TMA(1).pdf`, p. 12, blueprint ATV a reflashear.

---

# 9. Frente OTT y Packs Premium

## 9.1 Alcance OTT confirmado por el chat “Accionables | packs y OTTs TMA→FLOW”

El chat compartido por la Delivery Lead agrega las siguientes definiciones operativas. Se registran como confirmadas **dentro de ese chat**, pero requieren formalización en minuta/Jira y validación técnica antes de desarrollo o ejecución masiva.

| Tema | Definición observada | Estado |
|---|---|---|
| Universo a migrar | `Linked → Linked`. Los casos `Unlinked` no se migran. | **CONFIRMADO en el chat.** Falta definir funcional y técnicamente qué significa `Unlinked`, qué producto/cargo conserva y qué experiencia recibirá. |
| Freeze origen | TMA/Movistar TV se congela unos días antes de obtener la “foto” de la ola. Durante el freeze el cliente no debería comprar, dar de baja ni modificar suscripciones. | **CONFIRMADO en el chat.** Duración, operaciones bloqueadas, excepciones y sistema ejecutor: **GAP**. |
| Freeze en Flow | En el momento previo no se aplicaría un freeze equivalente en Flow porque los clientes todavía no existirían allí. | **CONFIRMADO como entendimiento del chat; A VALIDAR técnicamente.** |
| Secuencia macro | Freeze MTV → migración CRM y OTTs → alta en `MNV` → existencia/habilitación en Flow. | **CONFIRMADO en el chat como secuencia conceptual.** Debe detallarse con estados, contratos, reintentos y rollback. La equivalencia exacta entre `MNV` y otros nombres de plataforma debe confirmarse. |
| Segmentación por ola | Se agregará a la base el flag de Disney linkeado para obtener el corte/cantidad por ola. | **CONFIRMADO en el chat.** |
| Inventario de adicionales | Se plantea incorporar todos los adicionales/packs a la base, no únicamente Disney. | **NECESIDAD CONFIRMADA; alcance y campos A VALIDAR.** |

## 9.2 Disney+

### Objetivo

Permitir que Disney cambie la vinculación del cliente desde `Disney ↔ TMA` hacia `Disney ↔ TECO/Flow`, manteniendo continuidad de la suscripción para los clientes Linked incluidos en cada ola.

### Flujo candidato derivado del chat

1. Identificar clientes Disney Linked y asignarlos a una ola.
2. Congelar operaciones en TMA antes de generar la foto.
3. Generar archivo/manifest versionado con cliente, ola, pack y flag Linked.
4. Ejecutar la migración del producto en CRM.
5. Intercambiar con Disney los datos/formato acordados.
6. Cambiar el linking Disney–TMA por Disney–TECO/Flow.
7. Dar de alta/habilitar el producto en `MNV` y Flow.
8. Conciliar respuesta Disney, CRM/BSS, Flow y facturación.
9. Liberar o cerrar el freeze solamente cuando el resultado sea terminal.

> Los pasos 3–9 representan un refinamiento funcional propuesto. El chat confirma el objetivo, el freeze, el flag y la secuencia macro, pero no confirma todavía contratos, APIs/archivos, estados ni orden transaccional detallado.

### Dependencias y accionables detectados

| Acción / dependencia | Evidencia del chat | Estado |
|---|---|---|
| Cantidad de clientes por ola | Julieta López indicó que solicitó el volumen por ola a Juan Fernández Ussher. | **TRABAJO IDENTIFICADO**; entrega/fecha no confirmadas. |
| Flag Disney Linked | Juan Fernández Ussher informó que se sumará a la base para poder cortar por ola. | **TRABAJO IDENTIFICADO**; definición de campo y fuente pendientes. |
| Archivo para Disney | Se indicó que Jorge Suppicich tendría el archivo con datos y formato requerido por Disney. | **A VALIDAR:** confirmar versión, ubicación, campos, seguridad, owner y aprobación del partner. |
| Accionables por equipo | Se informó que ya hubo reunión Disney y cada equipo tiene accionables. | **NO DETERMINADO:** no se adjuntó la minuta ni el listado de accionables. |

## 9.3 HBO

| Tema | Situación informada | Estado |
|---|---|---|
| Integración | Se informó que fue presentada en QBR para Q4 2026 y que comenzaría en ese trimestre. | **PLAN INFORMADO; no compromiso confirmado.** |
| Finalización | Se indicó como probable finalización Q1 2027. | **PREVISIÓN, no fecha comprometida.** |
| Planificación | Depende de los Story Points que indiquen los PO de los equipos impactados y de la planificación técnica. | **DEPENDENCIA CONFIRMADA en el chat.** |
| Volumen | Queda pendiente compartir clientes con packs por ola. | **PENDIENTE.** |
| Comunicación al partner | Luego de la reunión de Inés/equipo se enviaría el correo formal solicitado por HBO. | **PENDIENTE / evidencia de envío no disponible.** |

### Preguntas de refinement HBO

- ¿El cliente conserva el mismo login o debe seleccionar/vincular proveedor nuevamente?
- ¿Qué estado del entitlement se migra y cuál se crea de cero?
- ¿Cómo se tratan cuentas duplicadas o ya vinculadas a otro proveedor?
- ¿Qué ocurre con los clientes de una ola si la integración no está disponible?
- ¿Se requiere contingencia manual, convivencia o exclusión de la ola?

## 9.4 Pack HOT / HOT GO

### Definición informada

Después de la baja del producto TMA, el cliente deberá seleccionar **Proveedor Flow** dentro de HOT GO para poder iniciar sesión.

**Estado:** CONFIRMADO en el resumen del chat. El diagrama enlazado `202609_Alta_Hot_GO.png` no fue incorporado como evidencia local; su contenido adicional no puede confirmarse todavía.

### Impactos

- cambio visible en la experiencia de login;
- comunicación previa y guía paso a paso;
- soporte para selección incorrecta de proveedor;
- definición de momento de baja TMA frente al alta Flow;
- conciliación de producto, entitlement y acceso;
- tratamiento de clientes que no completen la selección.

### Riesgo P0

La frase “seleccionar Proveedor Flow luego de dar de baja el producto en TMA” puede generar una ventana sin acceso si la habilitación Flow o el entitlement HOT todavía no están confirmados. Antes de aprobar el flujo debe definirse un gate:

`Flow base activo + entitlement HOT disponible + proveedor Flow habilitado → baja TMA → comunicación/cambio de login`.

Este orden es una **propuesta a validar**, no una decisión confirmada.

## 9.5 Paramount+

Se informó que la reunión con Paramount estaba pendiente y siendo gestionada.

**Estado:** NO DETERMINADO. No hay todavía definición de migración, login, archivo/API, fechas ni responsables verificables.

## 9.6 Capacidades y equipos del frente OTT

| Capacidad | Participación esperada | Estado |
|---|---|---|
| BSS Entretenimiento | Producto/packs desde CRM, mapping origen–destino y **desarrollo de la integración OTT desde BSS/CRM**: preparación y envío de datos, consumo de respuestas, estados, errores y conciliación con Flow/partner. | **CONFIRMADO por definición de la Delivery Lead; contrato por partner a validar.** |
| PyS / Catálogo | SKU, pack, compatibilidad, ABM y configuración de producto. | **A VALIDAR para cada partner.** |
| Flow Oferta y Onboarding / OTT | Suscripción, onboarding, integración con OTT de terceros y experiencia de acceso. | **CAPACIDAD CONFIRMADA; asignación concreta por partner a validar.** |
| Identidad Flow / Digital | Login, recuperación, selección de proveedor y matching de cuentas. | **A VALIDAR por partner.** |
| Partner Disney/HBO/HOT/Paramount | Linking, respuesta, reglas de cuenta y continuidad del entitlement. | **DEPENDENCIA CONFIRMADA.** |
| Billing/CBS | Alta/cese de cargos, prorrateo, no doble cobro y conciliación. | **DEPENDENCIA CONFIRMADA; owner exacto a validar.** |
| Migra/Core/Datos | Base de ola, flags, foto, manifest, IDs y conciliación. | **CONFIRMADO funcionalmente; owner formal pendiente.** |
| Martech/Journey/Atención | Comunicación, ayuda y tratamiento de clientes que deben re-vincular o seleccionar proveedor. | **A VALIDAR según experiencia definida.** |

## 9.7 Épicas específicas OTT

### OTT-1. Universo, flags y manifest de packs

- Inventariar todos los adicionales por cliente.
- Definir Linked/Unlinked por partner.
- Incorporar flags y fuente de verdad.
- Generar corte por ola y manifest versionado.
- Conciliar cambios ocurridos entre foto y ejecución.

### OTT-2. Freeze de operaciones en TMA

- Definir operaciones bloqueadas.
- Configurar inicio/fin y duración.
- Tratar excepciones operativas y atención.
- Evitar compras, bajas o modificaciones posteriores a la foto.
- Definir liberación y rollback.

### OTT-3. Migración Disney Linked

- Contrato de datos/archivo/API.
- Seguridad y transferencia.
- Cambio Disney–TMA a Disney–TECO/Flow.
- Respuesta, reintentos, errores y reconciliación.

### OTT-4. Integración HBO

- Refinamiento y estimación por equipos.
- Contrato de integración.
- Estrategia de login/vinculación.
- Contingencia si no llega antes de una ola.
- Plan Q4 2026 / Q1 2027 sujeto a estimación y planificación aprobada.

### OTT-5. Alta y cambio de proveedor HOT GO

- Habilitación del proveedor Flow.
- Baja segura del producto TMA.
- Comunicación y guía al cliente.
- Telemetría de primer acceso.
- Soporte y recuperación.

### OTT-6. Discovery Paramount y otros adicionales

- Reunión inicial.
- Universo y modalidad de vinculación.
- Login, datos, integración, billing y fechas.
- Decisión de inclusión por ola.

### OTT-7. Gate compuesto y conciliación OTT

- Definir si una falla de pack bloquea producto base, facturación o baja TMA.
- Tabla de verdad por partner.
- Dashboard base/pack/linking/billing.
- Colas de excepción, SLA y compensaciones.

## 9.8 Preguntas que deben cerrarse

1. ¿Qué significa exactamente `Unlinked` para cada partner?
2. ¿Un cliente Unlinked conserva el pack comercial, se excluye solamente su cuenta o no migra ningún componente OTT?
3. ¿Qué acciones quedan bloqueadas durante el freeze y por cuántos días?
4. ¿Cuál es la fuente de verdad de los flags y quién autoriza la foto?
5. ¿Qué sucede con cambios posteriores a la foto?
6. ¿El alta en `MNV` ocurre antes o después de la confirmación del partner?
7. ¿Qué evento confirma que el entitlement es utilizable?
8. ¿Una falla OTT bloquea facturación/baja TMA o se permite activación parcial?
9. ¿Cuál es el rollback por partner?
10. ¿Cómo se evita doble cobro entre TMA, Flow y facturación directa del partner?

---

# 10. Épicas de la iniciativa

## Épicas propias o lideradas por BSS Entretenimiento

### E1. Mapping y construcción del producto Flow en CRM

- Definir producto/plan origen y destino.
- Construir/configurar producto Flow en CRM.
- Definir planes, packs, precio, grilla y compatibilidades.
- Preparar estados PENDING/ACTIVE/Baja.
- Mantener trazabilidad TMA–Flow.

### E2. Migración masiva y estados comerciales por cliente

- Recibir manifest/ola.
- Validar idempotencia y duplicados.
- Precargar/migrar producto.
- Registrar resultado por cliente.
- Gestionar errores, reintentos y estados terminales.

### E3. Producto deco y orden BSS para recambio Linux

- Alta del producto/deco.
- Cantidad y reglas de decos incluidos/adicionales.
- Creación/actualización de orden.
- Asociación cliente–producto–orden–serial.
- Integración con delivery o visita.
- Cancelación, devolución y reversa comercial.

### E4. Producto e integración OTT desde BSS/CRM

**Owner funcional/técnico principal dentro de BSS:** squad Entretenimiento.  
**Dependencias:** Flow OTT/Oferta y Onboarding, cada partner, Catálogo/PyS, Migra/Datos, Identity y Billing.

- Construcción del producto y packs OTT en CRM.
- Mapping TMA → Flow por partner.
- Identificación y tratamiento de Linked/Unlinked.
- Incorporación y consumo de flags por partner y ola.
- Definición del contrato de salida desde BSS: archivo, API o evento.
- Preparación y envío de datos desde BSS/Migra hacia Flow OTT o el partner.
- Recepción y procesamiento de respuestas.
- Estados por suscripción: pendiente, enviado, linkeado, rechazado, error y revertido.
- Correlación cliente–producto–pack–partner–ola.
- Idempotencia, reintentos, timeouts y tratamiento de duplicados.
- Cola y resolución de errores parciales.
- Reversa y compensación cuando la integración no finaliza.
- Conciliación CRM/BSS–Flow–partner–Billing.
- Información necesaria para facturación y baja TMA.
- Implementaciones específicas para Disney, HBO, HOT GO, Paramount y demás adicionales.

> BSS Entretenimiento desarrolla el lado BSS/CRM de la integración. Flow OTT y cada partner son responsables de sus capacidades receptoras, del entitlement/linking y de las respuestas acordadas; los límites exactos deben documentarse por contrato.

### E5. Consumo de eventos y activación comercial

- Definir eventos primer login, REGISTRADO, INSTALADO y primer encendido.
- Consumir y correlacionar eventos.
- Cambiar el producto Flow a ACTIVE en el hito correcto.
- Evitar activaciones duplicadas o fuera de orden.

### E6. Coexistencia, baja del producto TMA y cierre comercial

- Mantener visibilidad durante coexistencia.
- Validar condiciones del gate.
- Ejecutar/solicitar baja TMA.
- Reversar cuando corresponda.
- Conciliar remanentes por ola.

## Épicas BSS dependientes de otros squads/capacidades

### E7. Catálogo, SKU y capacidades PyS

**Owner candidato:** PyS / Catálogo.  
**Estado:** A VALIDAR.

### E8. Ciclo de vida de pedido y orden de recambio

**Owner candidato:** OM.  
Incluye orden, estados, idempotencia, cancelación y relación con SA/OT.

### E9. Activación y plataformas de acceso

**Owners candidatos:** SAM Backend Web; SOM/FlowOne/InstantLinks.  
**Estado:** A VALIDAR por arquitectura.

### E10. Delivery gestionado en MEC

**Owner candidato:** MEC Delivery.  
Incluye alta de envío, tracking, entregado, devolución y excepciones.

### E11. Facturación y prevención de doble cobro

**Owners:** Facturación Front/Back y capacidades CBS a confirmar.  
Incluye hito de inicio, decos incluidos/adicionales, OTT, prorrateo, compensación y baja de cargo TMA.

### E12. Cobranzas y mora durante coexistencia

**Owners candidatos:** Cobranzas CBS y Morosidad CBS.  
Debe determinarse si existen desarrollos o sólo regresión/validación.

### E13. Conciliación y aseguramiento E2E

**Owners candidatos:** Conciliaciones y Legados.  
Incluye inconsistencias CRM/TMA/Flow, causa raíz y derivación.

## Épicas externas a BSS

### E14. Reflash ATV

**Owner confirmado:** Dispositivos de Flow — Tribu Flow.  
Incluye firmware, OTA, ejecución, telemetría, rollback y performance.

### E15. Fulfillment físico, stock y visita

**Owners a confirmar:** Fulfillment, logística, Workforce/Agenda y Field Service/OSS.  
Incluye stock, delivery/retiro, cupos, cita, OT, instalación y recupero.

### E16. Identidad, SSO y primer acceso

**Owners a confirmar:** Flow Oferta/Onboarding, Identidad y canales digitales.

### E17. OTT, entitlements y partners

**Owners a confirmar:** Flow OTT/Oferta y Onboarding, Apificación/partners, Inventory y Catálogo.  
Lighthouse se mantiene como dependencia candidata, no confirmada para todos los casos.

### E18. Comunicación, atención y journey de migración

**Owners a confirmar:** Martech/Comms, Digital, Journey y Atención según canal/capacidad.  
Journey no se asigna automáticamente como owner de la comunicación.

### E19. Observabilidad, UAT, piloto e hiper-care

**Owners a confirmar:** QA E2E, Datos/GCP, Operaciones y representantes de cada frente.

---

# 11. Dependencias P0 antes del refinement

1. Owner E2E y RACI por capacidad.
2. Secuencia agenda → appointment/SA → OT → API/orden BSS.
3. Máquina de estados por cliente, producto, dispositivo y OTT.
4. Catálogo de eventos primer login / REGISTRADO / INSTALADO / primer encendido / migrado.
5. Billing Gate y reglas de múltiples decos.
6. Regla de no respuesta, rechazo y cliente que no instala.
7. Contratos BSS–OM–SAM/SOM–Flow–Fulfillment–Field Service.
8. Gate de baja TMA y rollback comercial.
9. Solución por partner OTT, especialmente login y vinculación.
10. Jira paraguas, épicas relacionadas, owners y fechas.

---

# 12. DoR de la iniciativa

La iniciativa no debería pasar a desarrollo E2E hasta contar con:

- alcance y seis caminos aprobados;
- definición de éxito por camino;
- mapping de producto/SKU/precio/grilla;
- owners de cada épica y dependencia;
- AS-IS/TO-BE y máquina de estados;
- contratos API/eventos;
- secuencia de recambio aprobada;
- reglas de facturación y baja;
- estrategia de excepciones y rollback;
- NFR de volumen, seguridad, resiliencia y observabilidad;
- datos, ambientes y estrategia UAT;
- criterios de piloto, go/no-go y cierre de ola.

---

# 13. Fuentes

1. `DistribucionFuncionalidades - Tribu BSS (v 2026)(1).xlsx`, hoja `Organización Tribu BSS`.
2. `V0_Mapa_Maestro_Discovery_Dependencias_E2E.md`, secciones 3, 5, 6 y 8.
3. `Migra TMA(1).pdf`, págs. 10–13.
4. `Flujo proceso de envio de decos TMA.pdf`.
5. `Impact_Scan_E2E_Migracion_Movistar_TV_a_Flow.md`, secciones 8–15.
6. `Playbook Flow(1).pdf`, págs. 8 y 10.
7. Definiciones organizacionales aportadas por la Delivery Lead, incluida la confirmación del 29/09/2026 sobre Reflash ATV → Dispositivos de Flow / Tribu Flow.
8. Historial del chat `Accionables | packs y otts TMA->FLOW`, compartido por la Delivery Lead el 29/09/2026: Linked/Unlinked, freeze MTV, secuencia CRM/OTTs/MNV/Flow, flag Disney, planificación HBO, HOT GO y Paramount pendiente.
