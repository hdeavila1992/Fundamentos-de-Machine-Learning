# Tipos de Machine learning

Los sistemas de Machine learning(ML) se dividen en una o más de las siguientes categorías, dependiendo de como aprenden y los datos que generan

* Aprendizaje supervisado **(SL)**
* Aprendizaje No supervisado **(NSL)**
* Apremdizaje por refuerzo **(RL)**

## Aprendizaje supervisado

Los modelos de *ML* realizan predicciones después de analizar una cantidad significativa de datos que ya contienen las respuestas correctas. Luego, descubren las conexiones entre los elementos que producen dichas respuestas.

Es como un estudiante que aprende material nuevo revisando exámenes anteriores que contienen las preguntas y sus respectivas respuestas. Una vez que el estudiante se ha entrenado con suficientes exámenes, estará bien preparado para realizar examenes nuevos.

Se dice que estos sistemas están *supervisados* por que al sistema *ML* se le proporcionan los datos con los resultados conocidos.

Los casos más comunes de aprendizaje supervisado son:

### Regresión

Estos modelos predicen **valores numéricos**. Por ejemplo, un modelo meteorológico que predice la cantidad de lluvia, en pulgadas o milímetros, es un modelo de regresión.

---

!!! note "Algunos ejemplos de regresión ✍️."

    | Área de Aplicación | Ejemplo Específico | Variable a Predecir (Salida Numérica) |
    | :--- | :--- | :--- |
    | **Negocios / Ventas** | Predecir las ventas totales para el próximo trimestre basándose en el gasto en publicidad y la estacionalidad. | Ingresos en pesos (ej. $500,000,000) |
    | **Logística** | Estimar el tiempo de entrega de un paquete considerando la distancia, el peso del producto y la ruta. | Tiempo en horas (ej. 72.5 horas) |
    | **Recursos Humanos** | Determinar el salario justo para un nuevo candidato basándose en su experiencia, educación y el rol al que aplica. | Salario anual en pesos (ej. $95,000,000) |
    | **Negocios / Marketing** | Calcular el valor de vida de un cliente (Customer Lifetime Value) para enfocar los esfuerzos de retención. | Valor total en pesos que un cliente gastará (ej. $1,200,000) |
    | **Logística / Operaciones**| Optimizar los niveles de inventario para un producto y así evitar el exceso o la falta de stock. | Número de unidades a ordenar (ej. 850 unidades) |

### Clasificación

Predicen la provabilidad de que algo pertenezca a una categoría dada. A diferencia de los modelos de regresión en donde los resultados son un número, los modelos de clasifícación genera que tanto algo pertenece o no a una categoría.

Se pueden utilizar modelos de clasificación para predecir si un correo electrónico es spam o si una foto es de una vaca, gato o perro.

Los modelos de clasificación se dividen en dos grupos, clasificación binaria y clasificación multiclase. Las clasificación binaria predice un resultado entre dos categorías posibles, por ejemplo *llover* o *no llover*. Por otro lado, los modelos de clasificación multiclase predicen un resultado des entre varias categorias, por ejemplo, un modelo puede mostrar *lluvia*, *sequía*, *nieve* o *niebla*.

!!! video "🎥 Video: Clasificación binaria"

    <iframe width="100%" height="315" 
    src="https://www.youtube.com/embed/6Gcb-LlelvI" 
    frameborder="0" allowfullscreen></iframe>

!!! Image "🎥 Video: Clasificación binaria"

    <iframe width="100%" height="315" 
    src="https://www.youtube.com/embed/6Gcb-LlelvI" 
    frameborder="0" allowfullscreen></iframe>


## Aprendizaje No supervisado

## Aprendizaje por refuerzo


[Siguiente: Herramientas de Trabajo para el curso &rarr;](semana-1-herramientas.md)