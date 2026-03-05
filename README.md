# 📘 Ejercicio en Clase 3 – Modularización en Java
## Curso: Programación 1

---

## 🎯 Objetivo

Aplicar los conceptos de:

- Modularización mediante métodos.
- Uso correcto de variables locales y globales.
- Validación de entradas del usuario.
- Manejo básico de excepciones.
- Mejora de la organización y legibilidad del código.

---

## 📌 Instrucciones Generales

- Trabajar en parejas (**Obligatorio**).
- No utilizar IA para el análisis.
- Se proporcionará un programa base en Java.
- Analizarlo, mejorarlo y documentar el proceso en este archivo `README.md`.

---

## 📒INTEGRANTES
-Carlos Eduardo Corado Ibañez 0905-25-5315

-Gerson David Montufar Zeceña 0905-25-1463

# 🧠 Parte 1 – Análisis del Programa Original

En programa proporcionado por el Ingeniero Cordova pudimos observar un pequeños ejemplo de un programa para el control de una institución en este una escuela.
En dicho programa se podía optar por multiples tareas a implementar entre ellas:

-Agregar un estudiante

-Mostrar Lista de Estudiantes

-Calcular Promedio de Calificaciones

-Mostrar Estudiante con la calificacion más alta

-Salir

En el codigo de dicho programa pudimos observar que no poseía mudularización sino todo dentro del Main lo cual dificultaba la visibilidad y a la vez el poder comprender el código.

## 1️⃣ Identificación de Tareas Repetitivas

Responder:

- ¿Qué partes del código pueden convertirse en métodos?
Aprovechamos las recomendaciones brindadas por el Ingerniero Cordova y decidimos separar en distintos métodos las siguientes opciones a elegir del programa:

- Agregar estudiante.
- Mostrar estudiantes.
- Calcular promedio.
- Mostrar estudiante con mayor calificación.
- Salir


- ¿Qué bloques de código se repiten?
- Lectura de datos desde teclado.
- Validación de números.
-Impresión de listas.
-Cálculo de valores (sumas, promedios, máximos).

Estos bloques aparecen en varias partes del programa y se vuelven más fáciles de mantener si se agrupan en métodos.
Porque sino sería un poco confuso la legibilidad del código.

- ¿Qué responsabilidades pueden separarse?

-Entrada de datos (Scanner, validaciones).
-Procesamiento (cálculos, búsquedas).
-Salida de datos (impresiones en pantalla).
-Control del menú (switch o while principal).
-Separar estas responsabilidades evita que main se vuelva demasiado grande y difícil de leer.

Explicar por qué dividir estas tareas mejora el programa.

-Facilita la lectura: cada método tiene un nombre descriptivo.
-Mejora el mantenimiento: si algo falla, se revisa solo un método.
-Permite reutilizar código sin copiar y pegar.
-Reduce errores al evitar duplicación de lógica.

Hace que el programa sea más escalable si se agregan nuevas funciones.
---

## 2️⃣ Variables Locales vs Globales

Responder:

- ¿Qué variables deberían declararse como globales (atributos `static` de la clase)?

Arreglo o lista de estudiantes  
Necesita ser accesible desde varios métodos.

Contador de estudiantes  
Permite saber cuántos registros están ocupados.

Scanner  
Puede declararse global para evitar múltiples instancias.

- ¿Cuáles deberían ser locales dentro de un método?

Variables temporales como:

nombre

nota

promedio

maximo

Índices de recorrido

Estas solo se usan dentro de un método específico y no deben afectar otras partes del programa.

- ¿Por qué?

Porque hay algunas variales que solo se utilizan temporalmente y no durante toda la ejecución del programa, colocarlar dentro de un método optimizamos el rendimiento del programa.

Reflexionar sobre:

Alcance (scope): las variables locales solo existen dentro del método, evitando interferencias.

Tiempo de vida: desaparecen al terminar el método, liberando memoria.

Seguridad: reduce el riesgo de modificar datos globales por accidente.

Claridad: cada método controla sus propios datos internos.

---

# 🏗️ Parte 2 – Modularización del Programa

Reestructurar el programa aplicando modularización:

- Crear métodos claros y específicos.
- Cada método debe tener una sola responsabilidad.
- Todos los métodos deben ser llamados desde `main`.
- Mantener el programa completamente funcional.

No es obligatorio usar nombres específicos, pero deben ser descriptivos.

Ejemplo de buenas prácticas:

- Un método = una responsabilidad.
- No mezclar múltiples tareas en un mismo método.
- Mantener el código ordenado e indentado.

---

# 🔐 Parte 3 – Validaciones y Manejo de Excepciones

Implementar mejoras en el programa:

- Validar entradas numéricas.
- Evitar que el programa falle si el usuario ingresa texto en lugar de números.
- Verificar que las calificaciones estén en un rango válido.
- Usar `try-catch` cuando sea necesario.

Explicar en esta sección:

- Qué errores podrían ocurrir.

El usuario ingresa texto en lugar de números → InputMismatchException.

Calificaciones fuera de rango (ej. -5 o 200).

Intentar calcular promedio sin estudiantes registrados.

Buscar el mayor cuando la lista está vacía.

- Qué validaciones implementaron.

Uso de try-catch para capturar errores de entrada.

Repetir la solicitud hasta que el usuario ingrese un número válido.

Verificar que las notas estén entre 0 y 100.

Comprobar que existan estudiantes antes de calcular o mostrar datos.

- Por qué son importantes.

Es importante porque evita que a la hora de ejecutar el programa y queramos colocar una letra en lugar de un número nos de error o nos saque del programa.
Haciendo que el programa sea funcional y eficaz.

---

# 🧩 Parte 4 – Preguntas de Reflexión

Responder con sus propias palabras

## 1️⃣ ¿Qué ventajas tiene dividir el código en métodos?

Organización: a diferencia de trabajar todo el código dentro del Main el dividir las tareas en metodos hace que el código sea más entendible y claro.

Reutilización: esto nos es muy util a la hora de tener una parte de nuestro código que se repite varias veces y al volverlo un metodo solo necesitamos llamarlo para que se ejecute en cualquier parte de nuestro código.

Mantinemiento: esto al momento de hacer modificaciones o encontrar algun error nos ayuda a que no afecte todo el codigo sino solo el metodo que estamos modificando.

Claridad: el programa se ve más limpio y estético a la vez que facilita su comprension.

---

## 2️⃣ ¿Por qué no es recomendable usar muchas variables globales?

Reflexionar sobre:

- Posibilidad de errores inesperados: las variables globales al estar en funcion durante toda la ejecución del programa un cambio que no concuerde con sus parametros como por ejemplo una operacióm matematica invalida puede afectar a todo nuestro programa.

- Dificultad para depurar: puede que al momento de ingresar una cantidad o inicializar una variable que sea global se nos dificulte porque dicha variable tiene que estar cumpliendo todos los parametros que coloquemos en el programa o dichos metodos.

- Dependencia entre métodos: la dependencia entre metodos es importante ya que hay metodos que dependen de listas para guardar los datos.

---

## 3️⃣ ¿Cómo mejora la modularización la legibilidad del código?

Debido a que cada método identifica bien en su nombre su función o la operación a realizarse esto facilita su lectura y comprensión así también el implementar mejoras o actualizaciones en los procesos empleados que hacemos dentro del main.

---

