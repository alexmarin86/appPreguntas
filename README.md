<h1>App preguntas</h1>

<h2>Descripción</h2>

Esta sencilla app sirve al usuario una serie de preguntas con cuatro respuestas posibles, de las cuales sólo una es correcta. Cuando el usuario clica en una respuesta correcta, su color de fondo se vuelve verde, y el color de fondo de las demás respuestas se vuelve negro. Si, por otra parte, el usuario clica en una de las respuestas incorrectas, el color de fondo de esta se vuelve rojo, y el borde y color del texto de la respuesta correcta se vuelven verdes para resaltarla. El último componente de la app es el botón siguiente pregunta que sirve al usuario una nueva pregunta.

<h2>Trabajando con arrays complejos</h2>

En este ejercicio he creado un array compuesto por objetos que he utilizado para poblar las preguntas y respuestas. La estructura de datos es muy importante en javascript y este es el ejercicio perfecto para demostrar cómo funciona.
Cada objeto tiene una clave y un valor. La clave es un nombre descriptivo del valor y se utiliza para acceder a él, mientras que el valor es la información que queremos almacenar. Esta información puede ser una cadena de texto, un número, un valor booleano (true o false), null (valor vacío), un array, u otro objeto. Podemos anidar muchos niveles y crear arrays muy complejos, dependiendo del tipo de datos que necesitamos almacenar.

<h2>Planteamiento de la app</h2>

1. Creación de las variables iniciales que iremos utilizando a lo largo de la app

    a. numeroPregunta es una variable inicializada a 0 que iremos modificando cada vez que el usuario clica en “siguiente pregunta” <br>
    b. elemPregunta selecciona el elemento con la clase pregunta<br>
    c. elemRespuestas selecciona todos los elementos con la clase respuesta y los almacena en un array<br>
    d. botonSiguiente selecciona el elemento con la clase siguiente-pregunta<br>

2. Poblar la pregunta y respuestas iniciales<br>

    a. Asignar como texto interior del elemento pregunta el valor almacenado dentro del índice número pregunta de nuestro array, con la clave pregunta<br>
    b. Asignar las cuatro respuestas iterando el array que contiene la clave respuestas del mismo índice<br>

3. Crear la función esCorrecto que recibe un argumento event para comprobar que la respuesta clicada por el usuario es la correcta<br>

    a. Crear la variable respuesta que es el objetivo del evento<br>
    b. Asignar la clase clicado a la variable respuesta<br>
    c. Comprobar si el texto interior de la respuesta coincide con la respuesta correcta: <br>
      1. Si es así, iterar elemRespuestas para cambiar el color de fondo a negro, y después cambiar el color de fondo de la respuesta a verde<br>
      2. Si no es así, cambiar el color de fondo de la respuesta a rojo, iterar elemRespuestas hasta encontrar la respuesta correcta y cambiarle el color de fondo y borde a verde para resaltarla como correcta<br>
 
    d. Quitar los escuchadores de click de las respuestas. Esto es una medida preventiva, ya que todavía no hemos añadido dichos escuchadores. Su función es impedir al usuario clicar otras respuestas después de su click inicial. Para ello comprobamos si la variable clicado que crearemos a continuación tiene una longitud mayor que 0 (es decir, comprobamos si existe algún elemento con la clase clicado) e iteramos elemRespuestas utilizando el método removeEventListener.
4. Añadir los escuchadores de eventos click de las respuestas de la misma forma que los hemos quitado anteriormente, y crear la variable clicado que selecciona todos los elementos de la clase clicado.
5. Crear la función siguientePregunta que sirve al usuario otra pregunta <br>
  a. Comprobamos si la variable numeroPregunta es menor que la longitud de nuestro array preguntas. Esto es para prevenir que el usuario reciba una página en blanco si no hay más preguntas que servir. Para ello haremos lo siguiente: 
    - Primero, incrementar la variable numeroPregunta en 1. <br>
    - Cambiar el texto interior del elemento pregunta de la misma forma que en el paso 2.a. <br>
    - Repetimos el bucle for del paso 2.b, pero además añadimos las siguientes instrucciones dentro del mismo: <br>
      - Cambiar el color a negro
      - Cambiar el borde a “2px solid black”
      - Cambiar el color de fondo a “initial”
      - Añadir de nuevo escuchadores de click para la función esCorrecto
    Esto es necesario para resetear los cambios de estilo que se hayan podido producir al clicar una respuesta.
6. Añadir el escuchador de evento click para la función siguientePregunta en el botonSiguiente.
