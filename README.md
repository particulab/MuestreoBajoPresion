# Muestreo bajo presión

**Muestreo bajo presión** es un minijuego educativo de estadística en el que el estudiante debe estimar la media de una población mediante muestreo, administrar recursos limitados y construir un intervalo de confianza capaz de superar una estimación rudimentaria. Forma parte de **EulerGames**.

---

## Descripción del juego

El jugador observa una población de conejos cuyos pesos son desconocidos. Medir a cada individuo tiene un costo, por lo que no es posible conocer fácilmente a toda la población y es necesario trabajar con una muestra.

El estudiante decide manualmente qué conejos medir haciendo clic sobre ellos. Una vez seleccionado un individuo, su peso se revela y pasa a formar parte de la muestra.

Al mismo tiempo, **Ramiro** utiliza una estrategia mucho más simple: selecciona dos conejos al azar y afirma que la media poblacional se encuentra entre los pesos de ambos.

El objetivo del jugador es utilizar su muestra para construir un intervalo de confianza que proporcione una estimación más precisa que la de Ramiro.

---

## Objetivo educativo

El juego busca que el estudiante comprenda de forma práctica la relación entre:

* población y muestra;
* tamaño de muestra;
* media muestral;
* desviación estándar muestral;
* error estándar;
* distribución *t* de Student;
* nivel de confianza;
* amplitud de un intervalo de confianza;
* precisión de una estimación;
* costo de obtener información.

También se pretende mostrar que un nivel de confianza mayor no siempre constituye una elección trivialmente mejor, ya que normalmente produce intervalos más amplios.

El estudiante debe encontrar un equilibrio entre **confianza, precisión, tamaño de muestra y recursos disponibles**.

---

## Mecánica principal

Cada ronda genera una nueva población de conejos con diferentes pesos.

El jugador dispone inicialmente de:

```text
100 monedas
```

Medir un conejo cuesta:

```text
5 monedas
```

El estudiante puede seleccionar manualmente los individuos que desea incluir en su muestra. Cada conejo medido muestra posteriormente su peso.

El jugador puede continuar aumentando el tamaño de la muestra mientras disponga de recursos.

Además de medir individuos, puede utilizar sus monedas para comprar diferentes ayudas estadísticas:

| Herramienta                     | Costo |
| ------------------------------- | ----: |
| Media muestral                  |     6 |
| Desviación estándar muestral    |     8 |
| Valor crítico t                 |     8 |
| Gráfico Q-Q                     |    10 |
| Intervalo de confianza completo |    18 |

Comprar una herramienta no es obligatorio. El estudiante puede realizar el cálculo por su cuenta e introducir manualmente el resultado.

Los niveles de confianza disponibles son:

* 90 %
* 95 %
* 98 %
* 99 %

---

## Evaluación

Ramiro selecciona dos conejos al azar y utiliza sus pesos como extremos de su estimación:

$$
I_R=$(x_{\min},x_{\max})$
$$

El estudiante construye un intervalo de confianza para la media:

$$
IC=
\left[
\bar{x}-t_{\alpha/2,n-1}\frac{s}{\sqrt{n}},
\;
\bar{x}+t_{\alpha/2,n-1}\frac{s}{\sqrt{n}}
\right]
$$

Antes de comparar ambos procedimientos, el juego verifica los cálculos introducidos por el estudiante.

Al evaluar la ronda se revela la verdadera media de la población, \(\mu\).

La condición principal de victoria es:

1. el intervalo del estudiante debe contener la verdadera media poblacional;
2. si el intervalo de Ramiro también contiene la media, el intervalo del estudiante debe ser más estrecho.

Por tanto, un intervalo excesivamente amplio puede contener la media real pero perder frente a una estimación más precisa.

Si el intervalo del estudiante contiene la media y el de Ramiro no, el estudiante gana directamente.

Si ninguno de los dos intervalos contiene la media poblacional, la ronda termina sin ganador.

---

## Controles

La interacción se realiza mediante el ratón o pantalla táctil.

### Selección de muestra

* Hacer clic sobre un conejo para medirlo.
* El peso aparece una vez realizada la medición.
* Los individuos seleccionados quedan marcados visualmente.

### Herramientas

Los botones permiten comprar:

* media muestral;
* desviación estándar;
* valor crítico *t*;
* gráfico Q-Q;
* intervalo de confianza completo.

### Análisis

El estudiante puede introducir manualmente:

* \(\bar{x}\);
* \(s\);
* valor crítico \(t\);
* límite inferior del intervalo;
* límite superior del intervalo.

También puede seleccionar el nivel de confianza mediante un menú desplegable.

---

## Visualización

La interfaz muestra de forma permanente:

* monedas disponibles;
* número de individuos muestreados;
* costo de cada medición;
* tamaño de la población;
* pesos de los individuos seleccionados;
* herramientas estadísticas disponibles;
* propuesta de Ramiro.

Una recta numérica permite comparar visualmente:

* el intervalo propuesto por Ramiro;
* el intervalo de confianza construido por el estudiante.

Ambos aparecen sobre exactamente la misma escala para facilitar la comparación de su posición y amplitud.

La verdadera media poblacional permanece oculta durante el análisis.

Después de evaluar aparece como una línea vertical sobre la misma recta, permitiendo observar directamente si cada intervalo consiguió contenerla.

---

## Modelo matemático simplificado

Cada ronda utiliza una población finita de conejos cuyos pesos se generan alrededor de una media y una dispersión determinadas para esa población.

El estudiante observa únicamente los individuos que decide medir.

Para una muestra de tamaño \(n\), la media muestral es:

$$
\bar{x}=\frac{1}{n}\sum_{i=1}^{n}x_i
$$

La desviación estándar muestral se calcula como:

$$
s=
\sqrt{
\frac{
\sum_{i=1}^{n}(x_i-\bar{x})^2
}{
n-1
}
}
$$

El error estándar de la media es:

$$
SE=\frac{s}{\sqrt{n}}
$$

y el margen de error:

$$
E=t_{\alpha/2,n-1}\frac{s}{\sqrt{n}}
$$

por lo que el intervalo de confianza utilizado en el juego es:

$$
\bar{x}\pm E
$$

La amplitud del intervalo es:

$$
A=LS-LI
$$

Esta amplitud se utiliza para comparar la precisión de la estimación del estudiante con la propuesta de Ramiro.

El modelo está diseñado con fines educativos y busca representar las relaciones fundamentales entre tamaño de muestra, variabilidad, nivel de confianza y precisión.

---

## Tecnologías utilizadas

El juego está desarrollado únicamente con:

* HTML5;
* CSS3;
* JavaScript;
* Canvas.

No utiliza librerías externas ni requiere conexión a un servidor.

Todo el juego está contenido en un único archivo:

```text
index.html
```

---

## Cómo ejecutar

1. Descargar o clonar el proyecto.
2. Abrir la carpeta correspondiente al juego.
3. Abrir `index.html` en un navegador web moderno.

No es necesario instalar dependencias ni ejecutar un servidor local.

También puede publicarse directamente mediante servicios de alojamiento estático como GitHub Pages.

---

## Estructura del proyecto

```text
Muestreo-bajo-presion/
└── index.html
```

---

## Filosofía EulerGames

**EulerGames** es una colección de minijuegos educativos de física, matemáticas y áreas relacionadas diseñados para que el estudiante no se limite a observar una simulación.

La propuesta busca que el jugador tenga que:

1. leer datos;
2. discriminar información útil;
3. razonar o calcular;
4. tomar una decisión;
5. probar su respuesta;
6. recibir retroalimentación después de haber decidido.

En **Muestreo bajo presión**, el cálculo estadístico no aparece únicamente como un procedimiento algebraico. El estudiante debe decidir cuánto muestrear, qué información necesita, qué puede calcular por sí mismo y qué nivel de incertidumbre está dispuesto a aceptar.

---

## Autor

**Fausto Muñoz Esparza**

Proyecto desarrollado como parte de **EulerGames**.
