# Pérdida (Loss Functions)

En Machine Learning, una **función de pérdida** (o *Loss Function*) es una de las piezas más importantes del rompecabezas. Su trabajo es medir qué tan "equivocadas" están las predicciones de nuestro modelo en comparación con los resultados reales.

!!! info "Analogía Simple 🎯"
    Imagina que estás aprendiendo a lanzar dardos. La **función de pérdida** es como una regla que mide la distancia entre donde aterrizó tu dardo (la predicción) y el centro del tablero (el valor real). El objetivo del entrenamiento es usar esa medida para ajustar tu lanzamiento y minimizar la distancia en el futuro.

Las funciones de pérdida se dividen principalmente en dos categorías, dependiendo del tipo de problema que estés resolviendo.

---
## ## 1. Funciones de Pérdida para Regresión

Se utilizan cuando el objetivo es predecir un valor numérico continuo (ej. el precio de una casa, la temperatura de mañana).

### ### Error Cuadrático Medio (MSE - Mean Squared Error)

Es la función de pérdida más común para problemas de regresión. Calcula el promedio de los errores al cuadrado.

* **Fórmula:**
    $$
    MSE = \frac{1}{n} \sum_{i=1}^{n} (y_i - \hat{y}_i)^2
    $$
* **¿Cómo funciona?** Al elevar el error al cuadrado, penaliza mucho más los errores grandes. Si tu modelo predice un precio de una casa por $100,000 de diferencia, el MSE lo considerará un error mucho peor que 10 errores de $10,000.
* **Cuándo usarlo:** Es ideal cuando los errores grandes son particularmente indeseables y no tienes demasiados valores atípicos (*outliers*) en tus datos.

### ### Error Absoluto Medio (MAE - Mean Absolute Error)

Calcula el promedio de los errores en su valor absoluto, sin elevarlos al cuadrado.

* **Fórmula:**
    $$
    MAE = \frac{1}{n} \sum_{i=1}^{n} |y_i - \hat{y}_i|
    $$
* **¿Cómo funciona?** Trata todos los errores por igual, sin importar su magnitud. Un error de $100,000 es simplemente el doble de malo que un error de $50,000.
* **Cuándo usarlo:** Es una excelente opción cuando tus datos tienen valores atípicos (*outliers*), ya que es mucho más robusto y menos sensible a ellos que el MSE.

---
## ## 2. Funciones de Pérdida para Clasificación

Se utilizan cuando el objetivo es predecir una categoría (ej. 'perro' o 'gato'; 'spam' o 'no spam').

### ### Entropía Cruzada Binaria (Binary Cross-Entropy)

Es la función de pérdida por defecto para problemas de **clasificación binaria** (cuando solo hay dos clases posibles).

* **Fórmula:**
    $$
    BCE = - \frac{1}{N} \sum_{i=1}^{N} [y_i \log(\hat{y}_i) + (1 - y_i) \log(1 - \hat{y}_i)]
    $$
* **¿Cómo funciona?** Mide qué tan lejos está la probabilidad predicha por el modelo (un número entre 0 y 1) de la etiqueta real (que es 0 o 1). Penaliza fuertemente al modelo cuando está muy seguro de una predicción incorrecta.
* **Cuándo usarlo:** Siempre que tengas un problema con dos resultados posibles, como detección de fraude (`fraude` / `no fraude`) o diagnóstico médico (`enfermo` / `sano`).

### ### Entropía Cruzada Categórica (Categorical Cross-Entropy)

Es la extensión de la anterior, pero para problemas de **clasificación multiclase** (cuando hay más de dos categorías).

* **Fórmula:**
    $$
    CCE = - \sum_{i=1}^{C} y_i \log(\hat{y}_i)
    $$
* **¿Cómo funciona?** Compara la distribución de probabilidades que el modelo predice para todas las clases con la distribución real (donde solo la clase correcta tiene una probabilidad de 1).
* **Cuándo usarlo:** Cuando necesites clasificar algo en una de varias categorías, como reconocer dígitos escritos a mano (clases del 0 al 9) o clasificar imágenes de animales (`perro` / `gato` / `pájaro`).