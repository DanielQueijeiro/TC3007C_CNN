# Proyecto de Reconocimiento de Lenguaje de Señas (ASL)

Este repositorio contiene el desarrollo y comparación de dos modelos de redes neuronales convolucionales (CNN) diseñados para clasificar imágenes del alfabeto de lenguaje de señas americano (ASL).

## Descripción general
El objetivo del proyecto es traducir imágenes estáticas de manos realizando señas a sus letras correspondientes. Se exploraron diferentes arquitecturas y estrategias de procesamiento de datos para optimizar la precisión.

Enlace al dataset principal: [Kaggle ASL Alphabet](https://www.kaggle.com/datasets/grassknoted/asl-alphabet/data)

## Modelos desarrollados

Se entrenaron dos modelos con enfoques distintos:

### 1. Primer modelo (Base)
*   **Ubicación:** `primerModelo/`
*   **Clases:** 29 clases (A-Z, del, nothing, space).
*   **Arquitectura:** CNN profunda utilizando `GlobalAveragePooling`.
*   **Limitaciones:** Menor precisión debido a la inclusión de clases ambiguas ("nothing", "space") y menor diversidad en los datos de entrenamiento.

### 2. Segundo modelo (Optimizado)
*   **Ubicación:** `segundoModelo/`
*   **Clases:** 26 clases (A-Z).
*   **Mejoras Clave:**
    *   **Datos:** Combinación de 3 datasets diferentes para mayor diversidad de manos e iluminación.
    *   **Aumentación:** Uso de `RandomBrightness` y `RandomContrast` para que el modelo no dependa de la iluminación.
    *   **Arquitectura:** Uso de capa `Flatten` y capas densas más grandes (512 neuronas) para capturar mejor los detalles espaciales finos de los dedos.

## Pruebas y validación

Cada modelo cuenta con su propio notebook de entrenamiento y un notebook separado para pruebas con imágenes propias.

*   **Entrenamiento:**
    *   `primerModelo/primerModeloASL.ipynb`
    *   `segundoModelo/segundoModeloASL.ipynb`

*   **Pruebas:**
    *   `primerModelo/primerModeloTest.ipynb`
    *   `segundoModelo/segundoModeloTest.ipynb`