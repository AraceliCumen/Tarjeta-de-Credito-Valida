# TARJETA DE CRÉDITO VÁLIDA

## Objetivos del Programa:
<p> Crea una web que pida, por medio de un prompt(), el número de una tarjeta de crédito y
confirme su validez según el algoritmo de Luhn.</p>
<p>Consideraciones Específicas</p>

<p>Tu código debe estar compuesto por 1 función: isValidCard
El usuario no debe poder ingresar un campo vacío</p>

## Diagrama de Flujo:
![Diagrama de Flujo Tarjeta de Crédito Válida](/assets/docs/Tarjeta de Credito Valida.jpeg "Diagrama de Flujo Tarjeta de Crédito Válida")

## Explicación del Pseudocódigo:
<p>Función para encriptar una palabra</p>

### PROGRAMA TARJETA DE CRÉDITO VÁLIDA
* FUNCIÓN -->function isValidCard(number) retorna si el número de tarjeta el válido o no
  - arrOfNumberOfTarjet=[]: Declaramos un array vacío para almacenar el número invertido de la tarjeta en un array
  - Recorremos el número
  - PARA (i=0;i< Tamaño del String ;i++)
    - char: variable para Obtener el caracter de la posición i
    - char=number.charAt(i): obtenemos el caracter de la posición
    - arrOfNumberOfTarjet.push(parseInt(char)): Añadimos el caracter obtenido al array
  - Recorremos el array para obtener el producto en las posiciones pares, recorremos las posiciones pares
  - PARA (j=0;j< Tamaño del String ;j++)
    - prodDigitOfArray=(arrOfNumberOfTarjet[j]x2):Multiplicamos los dígitos de las posiciones pares por 2
    - SI (prodDigitOfArray>=10)
      - newProd=prodDigitOfArray.toString(): Covertimos el prodDigitOfArray en un String
      - sumProdDigitArray=0:Declaramos una variable para almacenar la suma de los digitos del producto
      - sumProdDigitArray=parseInt(newProd.charAt(0))+parseInt(newProd.charAt(1)):
    Sumamos lo dígitos
      - arrOfNumberOfTarjet.splice(j,1,sumProdDigitArray):Eliminamos en la posición par el elemento que se encuentra en este y agregamos la suma de los dígitos del producto del número x2 que esta en la posición par.
   - sumTotal=0:Creamos una variable sumTotal, para almacenar la suma de todos los dígitos del nuevo array
   - PARA(l=0;l<arrOfNumberOfTarjet.length;l++):Recorremos el nuevo arrOfNumberOfTarjet que guarda los dígito nuevos que vamos a sumar
      - sumTotal+=arrOfNumberOfTarjet[l]:Sumanos los números de  todas las posiciones
   - SI (sumTotal%10===0):Evaluamos que la suma total dividada entre 10,tenga residuo 0 para qe sea un número de tarjeta válida
      - MOSTRAMOS:('Usted a ingresado un número de tarjeta válida')
   - SI NO
      - MOSTRAMOS:('Usted a ingresado un número de tarjeta no válida, por favor verifique sus datos!!!')

* Validamos que el usuario no ingrese campor vacíos
  - SI(numberOfTarjetClient===''):
     - MOSTRAMOS:('Usted no ingresado su número de tarjeta,Debe ingresar un número')
  - SI NO
     - isValidCard(numberOfTarjetClient):validamos el número de tarjeta
     

* Hacemos un Menú:
  - HACER
     - op=0: Almacena las opciones del menú
     - strMenu: String que almacena el menú
     - strMenu = 1. Validar Número de Tarjeta\n2. Apagar\n:
    - op = Convertir a Entero lo que ingrese el usurio en (prompt(strMenu))

  - PARA (op === 1):
      - numberOfTarjetClient=prompt('Ingrese el número de tarjeta:'):Ingresamos el numero de la tarjeta de credito
      - Validamos que el usuario no ingrese campos vacíos
        - SI (numberOfTarjetClient==='')
          - MOSTRAMOS ('Usted no ingresado su número de tarjeta,Debe ingresar un número')
        - CASO CONTRARIO
          - isValidCard(numberOfTarjetClient): validamos el número de tarjeta
  - MIENTRAS (op !== 2);
