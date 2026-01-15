# ecuador-credit-statement-parser

Herramienta en Python para **extraer automáticamente información financiera clave** desde estados de cuenta bancarios en PDF, incluso cuando los archivos no contienen texto (OCR).

Pensado para análisis personal, control financiero, simulación de pagos y consolidación de tarjetas de crédito en Ecuador.

---

## 🚀 Funcionalidades principales

- Soporte para **PDFs con texto y PDFs escaneados**
- OCR automático con **Tesseract (español)**
- Parsers específicos por banco:
  - Banco del Austro
  - Banco del Pacífico
- Normalización robusta de texto
- Extracción de:
  - Saldos
  - Pagos
  - Consumos
  - Intereses
  - Tasas
  - Cupos
- Almacenamiento histórico en **SQLite**
- Prevención de duplicados por período
- Resumen financiero consolidado
- Simulador real de pagos e intereses
- Compatible con **Google Colab**

---

## 📊 Datos extraídos

Por cada estado de cuenta:

- Banco
- Período de corte
- Saldo anterior
- Pagos / créditos
- Consumos / débitos
- Saldo total
- Pago mínimo
- Interés del mes
- Tasa anual
- Cupo autorizado
- Cupo utilizado
- Cupo disponible
- Extracupo

---

## 🗂️ Estructura de la base de datos

Tabla: `estados_cuenta`

```sql
banco,
periodo_inicio,
periodo_fin,
saldo_anterior,
pagos_creditos,
consumos_debitos,
saldo_total,
pago_minimo,
interes_mes,
tasa_anual,
cupo_autorizado,
cupo_utilizado,
cupo_disponible,
extracupo
