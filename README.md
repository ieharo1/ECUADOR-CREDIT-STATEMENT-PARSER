# 💳 Ecuador Credit Statement Parser

Parser especializado para extraer automáticamente información financiera desde estados de cuenta bancarios en PDF de instituciones ecuatorianas. Desarrollado por **Isaac Esteban Haro Torres**.

---

## 📝 Descripción

Sistema de extracción de datos profesionales diseñado específicamente para estados de cuenta de bancos ecuatorianos. Convierte PDFs no estructurados en datos tabulares listos para análisis.

### ¿Qué hace este proyecto?

- **Extracción de transacciones**: Parsea cada movimiento del estado de cuenta
- **Identificación de patrones**: Detecta automáticamente ingresos, gastos, transferencias
- **Categorización**: Clasifica transacciones por tipo automáticamente
- **Exportación múltiple**: Excel, CSV, JSON, Base de datos
- **Validación de datos**: Verifica consistencia y detecta anomalías

---

## ✨ Características Principales

| Característica | Descripción |
|----------------|-------------|
| 📄 **Multi-formato PDF** | PDFs digitales y escaneados |
| 🏦 **Bancos soportados** | Banco del Pacífico, Banco del Austro, Banco Pichincha, Banco Guayaquil |
| 💾 **Múltiples salidas** | Excel, CSV, JSON, SQLite |
| 🔍 **Validación** | Detecta datos inconsistentes |
| 📊 **Estadísticas** | Resumen automático de movimientos |
| 🎯 **Alta precisión** | Regex + NLP para extracción precisa |

---

## 🛠️ Stack Tecnológico

- **Lenguaje**: Python 3.10+
- **PDF**: pdfplumber, pdfminer.six, PyMuPDF
- **OCR**: Tesseract (para PDFs escaneados)
- **Datos**: Pandas, NumPy
- **Regex**: Expresiones regulares avanzadas
- **Validación**: Great Expectations (opcional)

---

## 🚀 Instalación y Uso

### Instalación

```bash
pip install pdfplumber pandas openpyxl PyMuPDF
```

### Uso básico

```python
from credit_parser import ParserEcuador

# Inicializar parser
parser = ParserEcuador()

# Extraer datos de PDF
datos = parser.extraer("estado_cuenta.pdf")

# Ver transacciones
print(datos.transacciones.head())

# Exportar a Excel
datos.exportar("reporte_financiero.xlsx")

# Generar resumen
resumen = datos.generar_resumen()
print(resumen)
```

### Configuración avanzada

```python
# Especificar banco y opciones
parser = ParserEcuador(
    banco="banco_pacifico",  # o 'pichincha', 'guayaquil', 'austro'
    modo_ocr=True,           # Habilitar OCR para PDFs escaneados
    idioma="es",            # Idioma del documento
    fecha_inicio="2025-01-01",
    fecha_fin="2025-12-31"
)

# Extracción con categorías automáticas
datos = parser.extraer("estado.pdf", categorizar=True)
```

---

## 📊 Salida de Ejemplo

```python
# DataFrame con transacciones procesadas
  fecha      descripcion                    monto    tipo      categoria
0 15/01/2025 COMPRA SUPER MERCADO          -45.50   Débito   Supermercado
1 16/01/2025 SUELDO EMPRESA                 850.00   Crédito  Ingreso
2 17/01/2025 TRANSFERENCIA BCO PICHINCHA   -100.00  Débito   Transferencia
3 18/01/2025 PAGO SERVICIOS                -65.00   Débito   Servicios
```

---

## 📁 Estructura del Proyecto

```
ecuador-credit-statement-parser/
├── Estados_de_cuenta.ipynb
├── credit_parser/
│   ├── __init__.py
│   ├── base_parser.py
│   ├── bancos/
│   │   ├── pacifico.py
│   │   ├── pichincha.py
│   │   └── guayaquil.py
│   └── exporters.py
├── test/
│   └── test_parsers.py
└── README.md
```

---

## 🏦 Bancos Soportados

| Banco | Estado | Notas |
|-------|--------|-------|
| Banco del Pacífico | ✅ Completo | Formato principal |
| Banco del Austro | ✅ Completo | Soporte total |
| Banco Pichincha | ✅ Completo | Formato nuevo |
| Banco Guayaquil | ✅ Completo | Mobile & Web |

---

## 💡 Casos de Uso

1. **Contabilidad personal**: Registra gastos automáticamente
2. **Auditoría financiera**: Consolida múltiples cuentas
3. **Análisis de gastos**: Categorización para presupuestos
4. **申报 fiscal**: Preparación de documentación tributaria

---

## 📈 Métricas Generadas

- Total de ingresos por período
- Total de gastos por categoría
- Saldo promedio
- Transacciones más frecuentes
- Distribución de gastos
- Tendencias mensuales

---

## 🔧 Opciones de Exportación

```python
# Excel con múltiples hojas
datos.exportar("reporte.xlsx", format="excel", 
               sheets=["Resumen", "Transacciones", "Gráficos"])

# CSV
datos.exportar("transacciones.csv", format="csv")

# JSON para API
datos.exportar("datos.json", format="json")

# SQLite
datos.exportar("db.sqlite", format="sqlite", table="movimientos")
```

---

## 👨‍💻 Desarrollado por Isaac Esteban Haro Torres

**Ingeniero en Sistemas · Full Stack · Automatización · Data**

- 📧 Email: zackharo1@gmail.com
- 📱 WhatsApp: 098805517
- 💻 GitHub: https://github.com/ieharo1
- 🌐 Portafolio: https://ieharo1.github.io/portafolio-isaac.haro/

---

© 2026 Isaac Esteban Haro Torres - Todos los derechos reservados.
