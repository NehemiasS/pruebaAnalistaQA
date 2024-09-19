Nehemias Simon
melquisx@gmail.com

- error 1 
la interfas del cliente no muestra ninguan accion, se procede a revisar la consola del navegador y obtenomos este mensaje en consola 
index.html:87 Uncaught TypeError: guessSubmit.addeventListener is not a function
    at index.html:87:15
"addeventListener" tiene un error de sintaxis se realiza el cambio a "addevEntListener" gracias al ide de trabajo se detecta el mismo fallo en la linea 95 
index.html:95 Uncaught TypeError: resetButton.addeventListener is not a function
    at setGameOver (index.html:95:16)
    at HTMLInputElement.checkGuess (index.html:72:7)
setGameOver	@	index.html:95 
se realizan las modificaciones corespondientes el error 1 queda ok  

- error 2
la aplicacion mostro poder realizar aaciones pero en consolo mostro  los siqueintes errores 
index.html:79 Uncaught TypeError: Cannot set properties of null (setting 'textContent')
    at HTMLInputElement.checkGuess (index.html:79:29)
checkGuess	@	index.html:79
Uncaught TypeError: Cannot set properties of null (setting 'textContent')
    at HTMLInputElement.checkGuess (index.html:77:29)
checkGuess @ index.html:77

se dectecto otro erro de sintaxis le falta de "." lowOrHi semodifica y se hace las pruebas el error2 queda ok  

---caso de uso 1--- 
resultado esperado :
El número a adivinar debe pertenecer al conjunto de los enteros (e.g. 1, 2, 3...)

resultado obtenido:
El número a adivinar muestra numeros decimales los cuales no pertencen a los enteros 
solucion:
  "Math.random() * 10;" genera numero flotantes, tambien solo generaba nnumero del 1 y 10  se cambio por "Math.floor(Math.random() * 100) + 1;" el cual cumple el numero de rango de 1 a 100 y enteros 
CASO DE USO FUNCIONANDO!

---caso de uso 2 ---
Resultado esperado:
El número que ingresará el jugador debe pertenecer al conjunto de los enteros (e.g. 1, 2, 3...), en caso que no ingrese un número entero, debe mostrarse una alerta al usuario y no se debe incrementar un intento de prueba.

Resultado obtenido:
la aplicacion permite el ingreso de string y float no muestra alerta o mensaje alguno el contador de oportunidades se incremeta

se encuentra que se estaba comparando un string con un numero dentro del codigo 
 
 solucion:
 ya que no se cuenta con con algo programado dentro del codigo se notifica al equipo de desarrolo y adjunto una nota como posiblres ideas se debe modificar la funcion "checkGuess" validar el dato de entrada ejemplo "if (isNaN(userGuess) || userGuess < 1 || userGuess > 100 || userGuess.includes('.')" y mostras el mensjae o la alerta corespondiente 

 se modifica "guessField.value;"  por "Number(guessField.value)" 

CASO DE USO NO FUNCIONANDO SE PROCEDE A ESPERA DE SOLUCION Y SU POSTERIOR TEST DE VERIFICACION 

 ---caso de uso 3---
 Resultado esperado:
 Sí el número que ingresó el jugador es mayor al número a adivinar, se debe mostrar el siguiente mensaje en color negro: "Incorrecto! El número es mayor!", en caso que sea menor, se debe mostrar: "Incorrecto! El número es menor!".

 Resultado obtenido:
 el mensaje se muestra en color verde 

 Solucion:
      lastResult.style.backgroundColor = 'black'; 
      se modifica lalinea 75 de verde a negro 
CASO DE USO FUNCIONANDO!

  ---caso de uso 4---
 Resultado esperado:
 Si después de 10 intentos, el usuario no adivina el número, se debe mostrarse el mensaje de color rojo: "!!!Pérdistes!!!"

 Resultado obtenido:
se hace perder el juego intencional mente y el mesaje que muestra es Felicitaciones! adivinaste el número! el mensaje se muestra en rojo 

 Solucion:
 se modifica " lastResult.textContent = 'Felicitaciones! adivinaste el número!';" por "lastResult.textContent = 'perdiste!';"
 CASO DE USO FUNCIONANDO!

  ---caso de uso 5---
 Resultado esperado:
 Si el usuario adivina el número antes de los 10 intentos, se debe mostrar el mensaje de color verde: "Felicitaciones! adivinaste el número!".

 Resultado obtenido:
se procede aganar el juego se muestra un mesaje "perdiste" en color negro 

 Solucion:
 lastResult.textContent = '!!!Pérdistes!!!';
      lastResult.style.backgroundColor = 'black';
 se modifican a
    lastResult.textContent = '!!!Felicitaciones! adivinaste el número!!!!';
    lastResult.style.backgroundColor = 'green';
    CASO DE USO FUNCIONANDO!