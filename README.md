# README.md
# Simulación y Optimización del Proceso de Producción de Biodiésel
Fabiana Elizabeth Feijoo Casabona

Este proyecto, desarrollado por **Fabiana Elizabeth Feijóo Casabona**, implementa un modelo computacional para simular y optimizar el proceso de producción de biodiésel, incluyendo las etapas de reacción, separación y purificación. Utiliza Python y herramientas interactivas para analizar la eficiencia y proponer mejoras.

## Tabla de Contenidos
- [Introducción](#introducción)
- [Objetivo](#objetivo)
- [Requisitos](#requisitos)
- [Ejecución](#ejecución)
- [Estructura del Código](#estructura-del-código)
- [Resultados](#resultados)
- [Anexo: Variables y Parámetros](#anexo-variables-y-parámetros)
- [Contribución](#contribución)
- [Licencia](#licencia)



## Objetivo

Simular y optimizar el proceso de producción de biodiésel para maximizar su rendimiento, reducir residuos y minimizar el consumo energético. El modelo implementa:
- Reacción de transesterificación.
- Separación de biodiésel y glicerina.
- Purificación del biodiésel.
## Variables utilizadas

Variables Globales:
 k_forward: Constante de velocidad hacia adelante (mol/L·s). Controla la rapidez con la que
 los triglicéridos y metanol reaccionan para formar biodiésel y glicerina.
 
 k_reverse: Constante de velocidad inversa (mol/L·s). Controla la rapidez con la que el
 biodiésel y la glicerina reaccionan de vuelta para formar triglicéridos y metanol.
 
 MAX_TIME: Tiempo máximo de simulación en segundos (800). Se utiliza para limitar la
 duración de la simulación, evitando que dure más de lo necesario.
 
 Variables en la Función transesterificación:
 C_t: Concentración inicial de triglicéridos (mol/L). Representa la cantidad de triglicéridos en
 el sistema al inicio de la reacción.
 
 C_m: Concentración inicial de metanol (mol/L). Representa la cantidad de metanol al inicio
 de la reacción.
 
 t: Tiempo total de reacción en segundos. Determina cuánto tiempo durará la simulación de la
 transesterificación.
 
 steps: Número de pasos para la simulación (1000). Cuántos intervalos de tiempo pequeños se
 toman durante la simulación.
 
 C_b: Concentración de biodiésel (mol/L). Representa la cantidad de biodiésel formado a lo
 largo de la reacción.
 5.
 C_g: Concentración de glicerina (mol/L). Representa la cantidad de glicerina formada
 durante la reacción.
 
 dt: Paso de tiempo (segundos). Determina cuánto tiempo transcurre entre cada paso de
 simulación.
 
 delta_H: Calor de reacción (kJ/mol). Estima la cantidad de calor liberado o absorbido por
 cada mol de triglicéridos transformado en biodiésel.
 
 heat_capacity: Capacidad calorífica (kJ/(kg·K)). Define la cantidad de energía necesaria para
 elevar la temperatura de un kilogramo de material por un grado Kelvin.
 
 mass: Masa del sistema (kg). La cantidad total de material involucrado en el proceso (en este
 caso, el sistema tiene 10 kg).
 
 temperature: Temperatura del sistema en Kelvin (K). Se actualiza a lo largo del tiempo según
 el balance de energía.
 
 ambient_temperature: Temperatura ambiente en Kelvin (K). Se usa para calcular la pérdida de
 calor al entorno.
 
 heat_loss_coeff: Coeficiente de pérdida de calor (kJ/(mol·s)). Estima la cantidad de calor
 perdido del sistema debido a la diferencia de temperatura con el ambiente.

Listas para Almacenar Resultados:
 C_t_values: Lista para almacenar la evolución de la concentración de triglicéridos a lo largo
 del tiempo.
 C_m_values: Lista para almacenar la evolución de la concentración de metanol a lo largo del
 tiempo.
 C_b_values: Lista para almacenar la evolución de la concentración de biodiésel a lo largo del
 tiempo.
 C_g_values: Lista para almacenar la evolución de la concentración de glicerina a lo largo del
 tiempo.
 temperature_values: Lista para almacenar la evolución de la temperatura del sistema durante
 la simulación.
 Variables en las Funciones de Separación y Purificación:
 eficiencia: Es un parámetro utilizado en las funciones separacion y purificacion que indica qué
 tan eficiente es el proceso de separación o purificación. En la función de separación, se asume
 que una fracción del biodiésel y la glicerina se obtiene tras la separación, mientras que en la
 purificación se considera que se obtiene una fracción del biodiésel tras el proceso de
 purificación.

 Variables en la Función simulacion_interactiva:
 C_t0: Concentración inicial de triglicéridos en la simulación (mol/L). Es el valor que el usuario
 ingresa a través del control deslizante en la interfaz interactiva.
 C_m0: Concentración inicial de metanol en la simulación (mol/L). Es el valor que el usuario
 ingresa a través del control deslizante en la interfaz interactiva.
 t_reaccion: Tiempo total de reacción en segundos. El usuario puede ajustar este parámetro a
 través de un control deslizante.
 eficiencia_separacion: Eficiencia de la separación entre biodiésel y glicerina. Es un valor que
 el usuario puede ajustar entre 0.9 y 1.0.
 eficiencia_purificacion: Eficiencia de la purificación del biodiésel. También es un valor
 ajustable por el usuario, entre 0.9 y 1.0.
 
 Widgets para Interactividad:
 C_t_slider: Control deslizante para ajustar la concentración inicial de triglicéridos. 1.
 C_m_slider: Control deslizante para ajustar la concentración inicial de metanol. 2.
 t_slider: Control deslizante para ajustar el tiempo de reacción. 3.
 ef_separacion_slider: Control deslizante para ajustar la eficiencia de separación. 4.
 ef_purificacion_slider: Control deslizante para ajustar la eficiencia de purificación.
## Requisitos

- Python 3.8+
- Librerías necesarias (instalables mediante `requirements.txt`):
  ```bash
  pip install -r requirements.txt
