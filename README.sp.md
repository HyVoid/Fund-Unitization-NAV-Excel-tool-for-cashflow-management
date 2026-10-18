[ 🌐 عربي ](README.ar.md) | [ 🇩🇪 Deutsch ](README.de.md) | [ 🇫🇷 Français ](README.fr.md) | [ 🇳🇱 Nederlands ](README.nl.md) | [ 🇪🇸 Español ](README.sp.md) | [ 🇬🇧 English ](README.md)

# Rastrear la propiedad de fondos de inversión de forma justa cuando el capital entra en momentos diferentes

<div align="center">

![License](https://img.shields.io/badge/license-MIT-blue)
![Platform](https://img.shields.io/badge/platform-Microsoft%20Excel-217346)
![Domain](https://img.shields.io/badge/domain-Fund%20NAV%20Accounting-orange)

**Diseñado para fondos de inversión, sindicatos y grupos de negociación donde los participantes aportan capital en múltiples fechas y necesitan un libro de propiedad transparente y continuamente actualizado.**

[Demo en vivo](https://hyvoid.github.io/Fund-Unitization-NAV-Excel-tool-for-cashflow-management/) | [Comprar el Excel completo (gratis)](https://www.theseusworkshop.com/l/FundUnitizationDashboad?utm_source=github&utm_medium=GitHub%20README&utm_campaign=readme%20new%20launch&utm_content=fund-unitization-nav)

</div>

Rastrea la propiedad de cada participante de forma continua, resuelve la dilución automáticamente en la capa contable y mantiene un único registro auditable de cada saldo—actualizado en cada transacción.

---

## Vista previa rápida
<img width="1536" height="1024" alt="ChatGPT Image May 18, 2026, 04_56_08 PM" src="https://github.com/user-attachments/assets/42e2fe30-0173-45cc-945a-0d066ac2c974" />
<img width="1672" height="941" alt="ChatGPT Image May 18, 2026, 04_56_14 PM" src="https://github.com/user-attachments/assets/1b9a5b9c-5037-4e2a-8ddb-fd1584d48a5c" />
<img width="1448" height="1086" alt="ChatGPT Image May 18, 2026, 04_56_17 PM" src="https://github.com/user-attachments/assets/71d0cb5b-76f8-4152-b13d-0b58f792e9bc" />


> Observa el modelo contable interactivo: [demo del simulador de NAV y unitización de fondos](https://hyvoid.github.io/Fund-Unitization-NAV-Excel-tool-for-cashflow-management/)

---

## Por qué existe esto

La mayoría de las disputas en fondos de inversión no son causadas por malas intenciones.

Ocurren porque los porcentajes fijos, las fechas de entrada mixtas y la asignación manual de pérdidas y ganancias son difíciles de conciliar cuando un participante se retira—especialmente meses o años después de que se establecieran las posiciones que causaron el desacuerdo.

El riesgo es estructural:

```text
New capital contributed
-> Percentage split adjusted manually
-> Prior market gains not ring-fenced
-> Dispute surfaces at withdrawal
```

Este libro cambia el flujo de trabajo:

```text
New capital contributed
-> Units issued at current NAV
-> Prior participants' balances unaffected
-> Ownership tracked continuously from day one
```

El problema comercial no es solo la equidad. Es la claridad operativa. Los operadores de fondos, los tesoreros y los inversores principales necesitan saber exactamente cuánto se le debe a cada participante—en cualquier momento, no solo en el instante en que alguien pide salir.

---

## Tres trampas de asignación que atrapan incluso a los operadores de fondos

### Trampa 1 — Porcentajes estáticos malinterpretados como propiedad justa

La propiedad porcentual parece intuitiva. Se desmorona en el momento en que dos participantes entran en un fondo en alza en fechas diferentes.

Un fondo valorado en $130,000 tras una ganancia del 30 % recibe una aportación de $65,000. Si el nuevo participante recibe el 33 % de la propiedad directamente contra el valor actual del fondo, la ganancia del 30 % previa a la entrada del participante original ahora se comparte parcialmente con alguien que no estuvo presente para ella. El número parece internamente consistente. La economía no lo es.

Los operadores de fondos que asignan porcentajes fijos en el momento de la aportación—en lugar de valorar la entrada al valor de mercado actual—compensan insuficientemente a los participantes tempranos de forma rutinaria sin darse cuenta. El error se acumula silenciosamente. Sale a la luz en la salida.

### Trampa 2 — XIRR aplicado a un problema de propiedad que no puede resolver

XIRR calcula un rendimiento anualizado sobre un único flujo de caja. Responde: *¿Qué rendimiento obtuvo este inversor durante este período?* No responde: *¿Cuál es el saldo actual de este inversor, y cuánto recibe si sale hoy?*

Son preguntas diferentes. Los operadores que usan XIRR como mecanismo de asignación están resolviendo un problema de reporte de rendimientos con una herramienta de medición de desempeño.

Hacerlo funcionar requiere calcular un flujo de rendimiento separado por participante, recalcular después de cada transacción y conciliar manualmente los saldos resultantes cuando entra capital nuevo. El cálculo es válido en el momento en que se ejecuta. No mantiene ningún estado continuo. Cada depósito, retiro o entrada de pérdidas y ganancias requiere una ejecución manual nueva y una nueva pasada de conciliación.

Los operadores que rastrean rendimientos individuales con XIRR y luego derivan los saldos actuales de esos rendimientos están uniendo dos problemas con una sola herramienta—y generando brechas de conciliación cada vez que se mueve el capital.

### Trampa 3 — Efectos de dilución calculados después de la liquidación

En los modelos de porcentaje fijo, el impacto económico de una nueva aportación normalmente se resuelve en el siguiente período de conciliación, no en el momento en que entra el capital. Para entonces, el precio de entrada del nuevo participante ya no es visible en el libro. Solo quedan los saldos actuales.

Esto crea una ambigüedad estructural que no puede resolverse retroactivamente: si el fondo subió un 25 % entre la entrada de un inversor temprano y la entrada de un inversor posterior, y ambos recibieron propiedad porcentual asignada en la fecha posterior, la ventaja de temporalidad del inversor temprano ha sido absorbida silenciosamente en la división estática.

El error no está en la aritmética de nadie. Está en el modelo contable. Y normalmente se descubre en el peor momento posible—cuando alguien intenta irse.

---

## Para quién es esta herramienta

| Usuario | Caso de uso práctico |
|---|---|
| Tesoreros de clubes de inversión | Rastrear la propiedad por miembro a través de fechas de aportación irregulares sin recálculo manual |
| Operadores de sindicatos | Gestionar entradas y salidas de socios de capital sin renegociar divisiones porcentuales cada vez |
| Administradores de fondos pequeños | Mantener un libro transparente y auditable sin software contable institucional |
| Coordinadores de family offices | Asignar ganancias y pérdidas de forma justa entre familiares que aportan en momentos diferentes |
| Líderes de grupos de negociación discrecionales | Emitir units cuando se une capital nuevo; liquidar retiros a un valor actual verificable |

Es más adecuado para fondos con 3–20 participantes con tiempos de aportación mixtos, donde el software institucional de administración de fondos es prohibitivamente costoso pero la asignación manual con hojas de cálculo ya no produce respuestas limpias.

---

## Lo que hace el libro

### Libro de transacciones
Un único punto de entrada de datos para depósitos, retiros y eventos de pérdidas y ganancias de mercado. Registra cada transacción una vez; los recuentos de units, el NAV y los saldos por participante se actualizan automáticamente en segundo plano.

### Motor de cálculo de NAV
El valor liquidativo se recalcula continuamente a medida que se registran las pérdidas y ganancias de mercado. El saldo de cada participante se deriva del NAV actual × units mantenidas—no de una tabla de porcentajes que requiere mantenimiento manual.

### Emisión y reembolso de units
Los depósitos compran units al NAV actual. Los retiros reembolsan units al NAV actual. Los nuevos participantes reciben units valoradas al valor de mercado en el momento de la entrada, no a la par. Las ganancias acumuladas de los participantes anteriores se preservan estructuralmente—sin necesidad de aislamiento manual.

### Panel por participante
El saldo actual, el recuento de units, el porcentaje de propiedad, el NAV de entrada y el historial de aportaciones de cada participante son visibles en tiempo real. Sin recálculo manual. Sin ciclo de conciliación requerido para responder la pregunta: *¿cuánto se le debe a este inversor ahora mismo?*

### Registros listos para auditoría
Cada transacción se registra con fecha, NAV en la transacción, units emitidas o reembolsadas y saldos resultantes. Los registros están estructurados para revisión, exportación y resolución de disputas desde la primera entrada.

---

## Escenario de ejemplo

<!-- SCREENSHOT PLACEHOLDER: Before/after comparison or ledger entry view — recommended 1200 × 700 -->

**Perfil del fondo:** 8 participantes. Aportaciones repartidas a lo largo de 18 meses. El valor del fondo creció aproximadamente un 40 % durante ese período. Gestionado por el participante principal en una hoja de cálculo manual compartida.

**El problema:** Tres participantes se unieron en distintos momentos durante el período de crecimiento. El inversor principal ajustó los porcentajes de propiedad en cada entrada. Las pérdidas y ganancias se distribuyeron mensualmente en función de la tabla de porcentajes actual.

Cuando dos participantes tempranos solicitaron reembolsos totales, surgieron tres disputas simultáneas: una sobre el tratamiento correcto de una caída del 15 % que ocurrió entre las fechas de entrada de la primera y la segunda cohorte; una sobre una aportación que se había registrado en el mes equivocado; y una sobre qué porcentaje se aplicaba al último mes parcial antes de la salida.

La reconstrucción requirió rastrear a mano 18 meses de entradas de asignación manuales. El proceso tomó tres semanas, requirió un contador externo y resultó en que un participante aceptara una cifra diferente de su derecho real antes que continuar la disputa.

| | Antes | Después |
|---|---|---|
| Modelo de propiedad | Porcentajes fijos, ajustados manualmente en cada aportación | NAV basado en units; units emitidas al valor de mercado actual en el depósito |
| Tratamiento del nuevo participante | Porcentaje negociado en la entrada; ganancias previas no aisladas | Units compradas al NAV actual; participantes anteriores no afectados estructuralmente |
| Asignación de pérdidas y ganancias | Recálculo manual contra la tabla de porcentajes cada período | Automático vía movimiento del NAV; recuentos de units sin cambios |
| Liquidación de retiros | Reconstruir saldos a partir de entradas porcentuales históricas | Reembolsar units al NAV actual; saldo leído directamente del estado del libro |
| Superficie de disputa | Cualquier punto de conciliación manual | Resuelto en la capa contable |

---

## Por qué la contabilidad NAV funciona así

La contabilidad de los fondos de inversión adoptó la estructura de units/NAV específicamente porque la temporalidad de los inversores crea un problema de equidad económica que la propiedad estática no puede resolver sin intervención manual en cada punto de transacción.

Un participante que aportó a un fondo en alza el día 90 no compartió la exposición al riesgo de un participante que entró el día 1. Tratarlos como tenedores de propiedad equivalentes requiere ignorar la diferencia económica en sus condiciones de entrada—lo que los porcentajes fijos hacen por diseño.

La estructura de units codifica la temporalidad directamente: el precio pagado por unit en la entrada refleja el valor del fondo en el momento de la aportación. El movimiento del mercado después de la entrada fluye a través de cambios en el NAV, no a través de ajustes porcentuales. Los retiros se liquidan al valor de mercado actual. La contabilidad produce un estado continuo y verificable en cada momento sin requerir un ciclo de corrección manual.

Por eso cada fondo de inversión regulado—fondos mutuos, ETF, fondos de cobertura—usa la contabilidad NAV como su libro de propiedad. La estructura no se desarrolló para el cumplimiento normativo. Se desarrolló porque es el único mecanismo que maneja las cuatro preocupaciones de propiedad simultáneamente:

| Preocupación | Manejada por |
|---|---|
| Temporalidad de la entrada de capital | Precio de compra de la unit (NAV en la fecha de depósito) |
| Rendimiento del mercado | Movimiento del NAV; recuentos de units sin cambios |
| Tamaño de la aportación | Cantidad de units emitidas |
| Dilución por nuevos participantes | Units emitidas al NAV actual; no a la par |

Referencias útiles:
- [CFA Institute: Pooled Investment Vehicles](https://www.cfainstitute.org)
- [IOSCO: Principles for the Valuation of Collective Investment Schemes](https://www.iosco.org)
- [FASB ASC 946: Financial Services — Investment Companies](https://www.fasb.org)

---

## Cómo funcionan la emisión de units y el NAV

El valor liquidativo del fondo equivale al valor de mercado total dividido por las units en circulación. Cuando entra capital nuevo, compra units al NAV actual—no a la par. Las ganancias y pérdidas de mercado cambian el NAV; no cambian los recuentos de units.

| Evento | Valor del fondo | Units en circulación | NAV por unit |
|---|---|---|---|
| El inversor A deposita $100,000 | $100,000 | 100,000 | $1.00 |
| Ganancia de mercado: +30 % | $130,000 | 100,000 | $1.30 |
| El inversor B deposita $65,000 | $195,000 | 150,000 | $1.30 |
| Pérdida de mercado: −15 % | $165,750 | 150,000 | $1.105 |
| El inversor A reembolsa 50,000 units | $110,250 | 100,000 | $1.105 |

**El mecanismo en números:**
El inversor B entra a un NAV de $1.30—no a la par—y recibe 50,000 units por $65,000. Tras una pérdida del 15 %, el inversor B mantiene 50,000 × $1.105 = $55,250. El inversor B absorbió exactamente su parte proporcional de la caída en relación con su punto de entrada. La ganancia del 30 % previa a la entrada del inversor A no se transfirió.

**El modelo de porcentaje estático en el mismo escenario:**
Al inversor B se le asigna el 33 % de la propiedad en la entrada (una aportación de $65K en un fondo de $195K). Ese porcentaje se aplica directamente contra todas las pérdidas y ganancias futuras. En la próxima conciliación, el inversor B recibe el 33 % de la pérdida del 15 %—pero la ganancia del 30 % que el inversor A obtuvo antes de la entrada del inversor B ahora también se asigna parcialmente según la misma tabla de porcentajes. Los dos períodos económicamente distintos se han fusionado en un único número de propiedad.

El modelo NAV los separa estructuralmente. El cálculo porcentual se convierte en una consecuencia de los recuentos de units, no en una decisión de gestión tomada en cada límite de período.

Para un fondo con 8 participantes y actividad transaccional quincenal, eso son 8 cálculos de saldo continuos que se actualizan en cada depósito, retiro y registro de pérdidas y ganancias—sin un ciclo de ajuste manual.

---

## Lógica del libro

El libro está organizado en torno a un flujo práctico de administración de fondos:

1. Introduce la información de los participantes y las aportaciones iniciales.
2. Emite units al NAV actual para cada depósito.
3. Registra las pérdidas y ganancias de mercado a medida que ocurren—diarias, semanales o mensuales.
4. Reembolsa units al NAV actual para cada solicitud de retiro.
5. Revisa los saldos, recuentos de units y porcentajes de propiedad por participante en cualquier momento.
6. Exporta el historial de transacciones para conciliación, documentación fiscal o revisión de disputas.
7. Verifica si hay huecos de entrada o inconsistencias de saldo antes de realizar cualquier distribución.

El libro está pensado como una herramienta de apoyo a la decisión y transparencia contable. No reemplaza el asesoramiento legal cualificado sobre la estructura del fondo, el tratamiento fiscal de las asignaciones a inversores o el cumplimiento normativo en la jurisdicción del operador.

---

## Compra

Usa el libro de Excel completo aquí:

[Compra el rastreador de Excel completo](https://www.theseusworkshop.com/l/FundUnitizationDashboad?utm_source=github&utm_medium=GitHub%20README&utm_campaign=readme%20new%20launch&utm_content=fund-unitization-nav)

---

## Limitaciones

- **Dependencia de la integridad de los datos** — los cálculos de NAV son tan precisos como las entradas; las transacciones faltantes, mal fechadas o mal clasificadas producen saldos incorrectos sin advertencia
- **No es asesoramiento legal ni fiscal** — este libro refleja principios estándar de contabilidad NAV; el tratamiento fiscal de las asignaciones de units y las distribuciones a inversores varía según la jurisdicción y debe validarse con asesores cualificados
- **Solo entrada manual de datos** — los valores de mercado deben introducirse manualmente; el libro no se conecta a feeds de precios externos, API de corretaje ni sistemas de gestión de carteras
- **Alcance: solo depósitos, retiros y pérdidas y ganancias de mercado en efectivo** — las estructuras de carried interest, las cascadas de comisiones de rendimiento, las distribuciones de ingresos acumulados y los fondos multidivisa implican condiciones no codificadas en esta versión
- **Techo de escala** — diseñado para fondos con 3–20 participantes con frecuencia de transacción semanal a mensual; un volumen mayor puede degradar el rendimiento de Excel
- **Sensibilidad a la versión de Excel** — requiere Excel 2016 o posterior en Windows; el comportamiento en Excel para Mac u Office 365 web puede diferir
- **Casos límite no totalmente automatizados** — las asignaciones de side pocket, las disposiciones de capital bloqueado y las compuertas de reembolso escalonadas implican condiciones regulatorias o contractuales que requieren tratamiento manual no codificado en esta versión

---

## Acerca de este proyecto

Este libro forma parte de un esfuerzo más amplio por traducir requisitos contables operativos y financieros complejos en herramientas ligeras que las organizaciones pequeñas y medianas realmente puedan usar.

Sin suscripción a software de administración de fondos. Sin proyecto de desarrollo personalizado. Sin cuentas adicionales.

Solo lógica contable clara, datos de transacciones estructurados y cálculos de propiedad repetibles—entregados en software que tu equipo ya tiene.

Si tu operación involucra problemas de asignación, conciliación o rastreo de propiedad que actualmente viven en el modelo mental de alguien o en una hoja de cálculo desconectada, [mira qué más está disponible →](https://www.theseusworkshop.com)

---

## Licencia

Distribuido bajo la [Licencia MIT](https://opensource.org/licenses/MIT).
