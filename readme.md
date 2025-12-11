# 🧠 Sistema de Clasificación Automática de PQRS Usando Modelos LLM Open Source

Este repositorio contiene un sistema completo para **procesar, analizar y clasificar automáticamente documentos de PQRS (Peticiones, Quejas, Reclamos y Sugerencias)** provenientes de sistemas de gestión documental como **ORFEO**, utilizando modelos de lenguaje **open source** de última generación (Mistral, LLaMA, Mixtral, etc.) ejecutados localmente.

El objetivo principal del sistema es **automatizar la interpretación semántica** del contenido de las PQRS, evitando procesos manuales repetitivos y permitiendo clasificaciones rápidas, estandarizadas y trazables.

---

## 1. 📄 ¿Qué es ORFEO?

**ORFEO** es un sistema de gestión documental ampliamente usado para el manejo de radicaciones oficiales, correspondencia, comunicaciones e historiales administrativos.  
Permite descargar los documentos asociados a cada radicación, generalmente en formato PDF.

Este sistema toma esas PQRS extraídas de ORFEO —o de cualquier otro sistema equivalente— y ejecuta un pipeline de análisis para:

- Extraer el texto del documento,
- Normalizar el contenido,
- Comprender la semántica del mensaje,
- Clasificarlo usando un modelo LLM open source,
- Emitir una salida estructurada para análisis posterior.

---

## 2. 🧠 ¿Qué hace este algoritmo?

El algoritmo completa automáticamente todo el proceso de análisis documental:

### 2.1 Flujo general del sistema
1. **Carga de PQRS**  
2. **Extracción de texto con pdfminer.six**  
3. **Normalización** (limpieza, eliminación de ruido, estandarización)  
4. **Clasificación semántica con modelos LLM**  
5. **Generación de salidas estructuradas** (Excel, JSON, texto limpio)

Los modelos usados son open source:  
- **Mistral 7B**  
- **LLaMA 3 8B**  
- **Mixtral 8x7B**  

Todos ejecutados localmente mediante `llama-cpp-python`.

---

## 3. 🔧 Requisitos del Entorno

### Versión mínima de Python:
- **Python 3.10** (mínimo)  
- **Python 3.11** (recomendado)

---

## 4. 🏭 Creación del Entorno Virtual

```bash
conda create --name pqrs_llm_env python=3.10 -y
conda activate pqrs_llm_env
pip install --upgrade pip
pip install -r requirements.txt
```

---

## 5. 📦 Dependencias Principales

- pdfminer.six — extracción de texto  
- llama-cpp-python — ejecución local de modelos LLM  
- pandas, numpy, pyarrow — análisis estructurado  
- regex, chardet — normalización avanzada  
- tqdm — progreso  
- filetype — detección de formato  

---

## 6. 📁 Estructura Recomendada del Proyecto

```
/project-root
├── notebooks/
├── models/
├── data/
├── outputs/
├── utils/
├── requirements.txt
└── README.md
```

---

## 7. 🚀 Ejecución del Sistema

1. Coloque los PDFs en `data/`.  
2. Seleccione el modelo LLM en el notebook.  
3. Ajuste parámetros de análisis.  
4. Ejecute el notebook de arriba hacia abajo.  
5. Revise resultados en `outputs/`.

---

## 8. 🧪 Validación del Entorno

```bash
python - << EOF
import pandas, numpy, llama_cpp
print("Entorno validado correctamente.")
EOF
```

---

## 9. ❗ Problemas Comunes

| Problema | Causa | Solución |
|----------|--------|----------|
| Error al cargar modelo | GGUF incompatible | Descargar versión correcta |
| Texto incompleto | PDF escaneado | Aplicar OCR (Tesseract) |
| Predicciones incoherentes | Modelo pequeño | Usar 7B+ |
| Unicode extraño | PDF irregular | Activar chardet + regex |

---

## 10. 📄 Créditos

Sistema diseñado para clasificar automáticamente PQRS usando LLM open source, garantizando independencia tecnológica, seguridad de datos y reproducibilidad del análisis.
