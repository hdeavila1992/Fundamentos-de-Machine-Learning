# Aprendizaje supervisado

El aprendizaje supervisado se basa en los siguientes aspectos:

* Datos
* Modelos
* Entrenamiento
* Evaluación 
* inferencia

## Datos

Los datos son el *motor* del machine learning, sin datos no ha Machine learning, solo modelos complicados ejecutando información inutil. Los tados pueden ser numeros o palabras almacenados en una tabla. valores de pixeles capturados de una imagen, archivos de audio, entre otros. Esta información es almacenada en los damosos *darasets* por ejemplo tenemos:

* [Imagenes de gatos](https://www.kaggle.com/datasets/crawford/cat-dataset)
* [Precio de las casas](https://www.kaggle.com/datasets/saurabhbadole/housing-price-data)
* [Información del clima](https://www.kaggle.com/datasets/ananthr1/weather-prediction)

Los data son conjuntos de ejemplos individuales que contienen *caracteristicas* y *etiquetas* Pordias pensar en un hoja de calculo con una fila, las *carácteristicas* son los valores que queremos que el modelo utilice para predecir las etiquetas. La etiqueta es la respuesta o el valor que queremos que nuestro modelo prediga. Por ejemplo, en el caso de un modelo del clima, queremos que pregiga si llovera o no, para eso podemos utilizar *latitud*, *longitud*, *temperatura*, *humedad*, *covertura de las nuves*, *dirección del viento* y presión atmosferica como las *carácteristicas* para predecir la etiqueta de *lluvia*

| date | lat | long | temp | humidity | cloud_coverage | wind_direction | atmp_pressure | rainfall |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 2021-09-09 | 49.71N | 82.16W | 74 | 28 | 3 | N | 18.6 | .01 |
| 2021-09-09 | 32.71N | 117.16W | 82 | 42 | 6 | SW | 29.94 | .23 |

Por otro lado, ejemplos sin *etiqueta* contienen solo las carácteristicas, la idea es que el modelo prediga la etiqueta para este dataset, basado en el entrenamiento que tuvo con el dataset con *etiqueta*

| date | lat | long | temp | humidity | cloud_coverage | wind_direction | atmp_pressure |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 2021-09-09 | 49.71N | 82.16W | 74 | 28 | 3 | N | 18.6 |
| 2021-09-09 | 32.71N | 117.16W | 82 | 42 | 6 | SW | 29.94 |

## Caracteristicas de los datasets

Los data set se pueden entender en dos dimensiones, el tamaño que indica en numero de ejemplo y la diversidad que indica el rango que esos ejemplos cubren. Los data set que son buenos, son gramdes y diversos.

| Tamaño del dataset | Diversidad del dataset | Características | Riesgo principal | Ejemplo práctico |
|---------------------|------------------------|-----------------|------------------|------------------|
| Grande              | Alta                   | Ideal: muchos ejemplos variados que representan bien el fenómeno. | Generalización sólida y buen desempeño. | Dataset de millones de imágenes de gatos en diferentes razas, poses, fondos e iluminaciones. |
| Grande              | Baja                   | Muchos datos pero muy parecidos entre sí. | El modelo aprende patrones limitados y no generaliza bien a nuevos casos. | Registros de inventario de Muebles Jamar con 1 millón de entradas, pero solo de un único tipo de sofá en una sola ciudad. |
| Pequeño             | Alta                   | Pocos ejemplos, pero con buena variedad. | Riesgo de underfitting (el modelo no logra aprender lo suficiente). | Dataset de 200 fotos de gatos, incluyendo distintos colores, posiciones y ambientes. |
| Pequeño             | Baja                   | Pocos datos y poco variados. | Dataset deficiente, alto riesgo de sobreajuste y mala generalización. | Inventario de Muebles Jamar con solo 50 registros de sillas de un mismo modelo y color. |

Otro ejemplo.

| Tamaño del dataset | Diversidad del dataset | Características | Riesgo principal | Ejemplo práctico |
|---------------------|------------------------|-----------------|------------------|------------------|
| Grande              | Alta                   | Ideal: muchos ejemplos variados que representan bien el fenómeno. | Generalización sólida y buen desempeño. | Dataset de entregas de Muebles Jamar con millones de registros que incluyen diferentes ciudades, tiempos de despacho, rutas de camiones, tipos de muebles y condiciones de tráfico. |
| Grande              | Baja                   | Muchos datos pero muy parecidos entre sí. | El modelo aprende patrones limitados y no generaliza bien a nuevos casos. | Registros de inventario de Muebles Jamar con 1 millón de entradas, pero solo de un único tipo de sofá en una sola ciudad. |
| Pequeño             | Alta                   | Pocos ejemplos, pero con buena variedad. | Riesgo de underfitting (el modelo no logra aprender lo suficiente). | Dataset de logística de Muebles Jamar con 200 registros de entregas en distintas ciudades y diferentes tipos de muebles, pero el tamaño aún es insuficiente para modelar bien los patrones. |
| Pequeño             | Baja                   | Pocos datos y poco variados. | Dataset deficiente, alto riesgo de sobreajuste y mala generalización. | Inventario de Muebles Jamar con solo 50 registros de sillas de un mismo modelo y color en una única tienda. |

!!!  Pregunta de repaso
    ¿Cuál es la característica de un buen dataset?

<form id="quiz1">
  <input type="radio" name="q1" value="a"> Que sea pequeño y poco diverso<br>
  <input type="radio" name="q1" value="b"> Que sea grande y diverso <br>
  <input type="radio" name="q1" value="c"> Que tenga solo un tipo de ejemplo<br>
  <button type="button" onclick="checkAnswer()">Enviar</button>
</form>

<p id="feedback"></p>

<script>
  function checkAnswer() {
    const selected = document.querySelector('input[name="q1"]:checked');
    const feedback = document.getElementById("feedback");
    if (!selected) {
      feedback.innerHTML = "⚠️ Por favor selecciona una opción.";
      return;
    }
    if (selected.value === "b") {
      feedback.innerHTML = "✅ ¡Correcto! Un buen dataset debe ser grande y diverso.";
    } else {
      feedback.innerHTML = "❌ Incorrecto. Intenta de nuevo.";
    }
  }
</script>

Un data set tambien se puede caracterizar por el numero de *carácteristicas*. Algunos pueden contener miles de caracteristicas, como imagenes por satelite o porcentaje de covertura de nubes. Otros datase, pueden contener 2 o 3 *carácteristicas*. Datasets con más caracteristicas pueden ayudar al modelo a descubrir más patrones y realizar mejores preduccciones. Sin embargo, en algunas ocaciones carcateristicas extras pueden hacer que el modelo empeore puesto que esta intentando buscar una relación entre una *carácteristica* incausal y la *etiqueta* por ejemplo en numero de habitantes que nacen en julio no es causal a la lluvia.  

## Modelos

En el aprendizaje supervisado, un modelo es una colección compleja de numeros que definene matematicamente los patrones entre las *carácteristicas* de entrada y las *etiquetas* de salida, el modelo aprende esto en el entrenamiento.

## Entrenamiento

Para entrenar un modelo, se debe dar el dataset y las etiquetas de ejemplo. El objetivo del modelo es encontrar la mejor solución para predecir las *etiquetas* de las caracteristicas.
El modelo puede encontrar la mejor solución al comparar su respuesta con la respuesta que debería dar, es decir, las *etiquetas* de ejemplo. Basado en la diferencia entre los valores predichos y el valor real, definida como la [*Perdida*](semana-1-perdida.md) el modelo se actualiza gradualmente para minimizar esta perdida. Dicho de otro modo, el modelo encuentra la relacieón matemática entre las *carácteristicas* y las *etiquetas*

Por ejemplo si tengo un modelo que preduce la intensidad de lluvia, digamos que
predice 28 cm de lluvia, pero el valor real es e 4 cm, el modelo modifica la solución
tal que la nueva predicción es más cercana a 4 cm.

<iframe src="https://unisimonedu-my.sharepoint.com/personal/hernando_deavila_unisimon_edu_co/_layouts/15/embed.aspx?UniqueId=d2c004a0-36d8-4727-9c44-10e21743d751" width="640" height="360" frameborder="0" scrolling="no" allowfullscreen title="Gemini_Generated_Image_revyvdrevyvdrevy"></iframe>

El modelo compara su predicción con el valore real en el dataset y actualiza su solución

<iframe src="https://unisimonedu-my.sharepoint.com/personal/hernando_deavila_unisimon_edu_co/_layouts/15/embed.aspx?UniqueId=9687aae1-be5e-4634-80cd-49db1e1babbf" width="640" height="360" frameborder="0" scrolling="no" allowfullscreen title="Gemini_Generated_Image_a8mc1ra8mc1ra8mc"></iframe>

Con el error el modelo actualiza sus parametros internos.

<iframe src="https://unisimonedu-my.sharepoint.com/personal/hernando_deavila_unisimon_edu_co/_layouts/15/embed.aspx?UniqueId=af7577f4-10e0-49b3-947b-31c480a11a2c" width="640" height="360" frameborder="0" scrolling="no" allowfullscreen title="Gemini_Generated_Image_e0ip7ue0ip7ue0ip"></iframe>

El modelo repite este proceso para cada una de las *etiquetas* de ejemplos de la base de datos.

<iframe src="https://unisimonedu-my.sharepoint.com/personal/hernando_deavila_unisimon_edu_co/_layouts/15/embed.aspx?UniqueId=d9b8948f-3674-4a71-8a93-b6c60f268775" width="640" height="360" frameborder="0" scrolling="no" allowfullscreen title="Captura de pantalla 2025-09-05 a la(s) 5.36.08 p.m."></iframe>

El modelo aprende gradualmente la relación entre las características y la etiqueta al procesar grandes y diversos conjuntos de datos, lo que mejora su rendimiento. Durante este entrenamiento, los profesionales de Machine Learning pueden realizar ajustes sutiles, como seleccionar o eliminar características (por ejemplo, la hora del día en un conjunto de datos meteorológicos) para observar si el modelo mejora sus predicciones y así optimizar su solución final.

## Evaluación

Se evalue el modelo entrenado para determinar como de bien ha aprendido. Cuando nosotros evaluamos un modelo,
se utiliza los datasets *etiquetados*. Pero solo le damos las caracterustucas  para comparar la predicciones del modelo con las *etiquetas*

!!! "📷 Imagen: Evaluación del modelo"

<figure markdown="span">
    ![Diagrama de clasificación](https://unisimonedu-my.sharepoint.com/personal/hernando_deavila_unisimon_edu_co/Documents/Documentos/Simon%20bolivar/Inteligencia%20artificial/Machine%20Learning/Imagenes_curso/Captura%20de%20pantalla%202025-09-05%20a%20la(s)%205.53.04%E2%80%AFp.m..png){ width="350" }<figcaption>Evaluación del modelo de Machine Learning.</figcaption></figure>


## Inferencia

Una vez que estamos satisfechos con los resultados de la evaluación, podemos usar el modelo para hacer predicciones, llamadas inferencias, sobre ejemplos sin etiquetar. En el caso de la aplicación del clima, le daríamos al modelo las condiciones meteorológicas actuales —como la temperatura, la presión atmosférica y la humedad relativa— y este predeciría la cantidad de lluvia.

---

### Pregunta 1

¡Es hora de poner a prueba lo que has aprendido! Responde la siguiente pregunta directamente aquí en la página.

**¿Por qué un modelo necesita ser entrenado antes de poder hacer predicciones?**

<form id="quiz2">
  <input type="radio" name="q1" value="a"> Un modelo necesita ser entrenado para que no requiera datos al hacer una predicción.<br>
  <input type="radio" name="q1" value="b"> Un modelo necesita ser entrenado para aprender la relación matemática entre las características y la etiqueta en un conjunto de datos.<br>
  <input type="radio" name="q1" value="c"> Un modelo no necesita ser entrenado. Los modelos están disponibles en la mayoría de las computadoras.<br>
  <button type="button" onclick="checkAnswer()">Enviar</button>
</form>

<p id="feedback"></p>

<script>
  function checkAnswer() {
    const selected = document.querySelector('input[name="q1"]:checked');
    const feedback = document.getElementById("feedback");
    if (!selected) {
      feedback.innerHTML = "⚠️ Por favor selecciona una opción.";
      return;
    }
    if (selected.value === "b") {
      feedback.innerHTML = "✅ ¡Correcto! Un modelo necesita ser entrenado para aprender la relación matemática entre características y etiquetas.";
    } else {
      feedback.innerHTML = "❌ Incorrecto. Intenta de nuevo.";
    }
  }
</script>

[Examen final de conceptos](semana-1-3.md)