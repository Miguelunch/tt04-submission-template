![](../../workflows/gds/badge.svg) ![](../../workflows/docs/badge.svg) ![](../../workflows/wokwi_test/badge.svg)

# Calculadora Binaria de 3 Bits

El siguiente proyecto consiste en una Calculadora Binaria de 3 Bits conformada por 4 
opciones de operaciones y/o herramientas. Las operaciones capaces de realizar de este 
circuito son suma, resta y multiplicación; la cuarta opción consiste en un contador 
automático de 4 bits, el cual depende de una señal de reloj para cambiar el valor mostrado 
de forma consecutiva. Para poder desplazarse entre cada una de las distintas opciones se 
realizó un Multiplexor 4 a 1.

Todo este proyecto fue desarrollado en la plataforma en línea WOKWI, en donde es posible 
observar el circuito de forma libre e incluso simularlo para interactuar con sus funciones. La 
idea de realizar una Calculadora Binaria de 3 Bits nació de la actividad crear un proyecto 
propuesto por el campamento LATINPRACTICE, el cual, lo recomendable es realizarse con 
herramientas libres de diseño VLSI, sin embargo, como algunos no poseemos una base 
sólida de estas herramientas, se nos dio la oportunidad de crear nuestro propio circuito 
utilizando compuertas lógicas en la plataforma de WOKWI.

https://wokwi.com/projects/373184190141669377

# Desarrollo del Circuito
# Sumador

https://wokwi.com/projects/373005455971337217

Para poder desarrollar el sumador de 3 bits, es necesario comprender como funciona un 
medio sumador y un sumador completo.

## Medio Sumador
El medio sumador se conforma de dos bits de entrada (X, Y) y dos bits de salida. Las 2 
salidas posibles del medio sumador son una salida denominada “S”, y un carry o acarreo 
denominado “C”, así como se muestra a continuación.

![image](https://github.com/Miguelunch/tt04-submission-template/assets/142178685/5704eb25-dd25-475d-ae19-a41496125d4f)

El carry o acarreo es el bit que se genera cuando ambas entradas (X, Y) están activadas y 
les llegan un bit a cada uno. Se podría decir que generan un 2 en binario (1 0), por lo tanto, 
la salida “S” no generaría un bit de salida.
Lo que caracteriza al medio sumador de su otra variante (sumador completo) es que 
solamente tiene dos bits de entrada y solo puede arrojar una sola salida a la vez, ya sea la 
salida “S” o la salida carry “C”, nunca las dos al mismo tiempo, así como se muestra en su 
tabla de verdad.

![T1](https://github.com/Miguelunch/tt04-submission-template/assets/142178685/c75f71ec-5db5-4060-91a0-d87b2030f285)

Con las expresiones booleanas de las salidas “S” y “C”, es posible generar un circuito con compuertas lógicas, por lo tanto, su circuito quedaría de la siguiente manera.

![image](https://github.com/Miguelunch/tt04-submission-template/assets/142178685/03622e8a-1b2e-454c-b88c-16683ae2e182)
![image](https://github.com/Miguelunch/tt04-submission-template/assets/142178685/7d8d628b-01a4-40f9-b20c-1187dd2f1049)

## Sumador Completo

A diferencia del medio, el sumador completo se conforma de tres bits de entrada (X, Y, Z) y 2 bits de salida. Las 2 salidas posibles del medio sumador son una salida denominada “S”, y un carry o acarreo denominado “C”, así como se muestra a continuación.

![image](https://github.com/Miguelunch/tt04-submission-template/assets/142178685/961360a2-78c8-4288-bcae-f8becd2e9677)

Cabe recalcar que otra forma de ver la entrada “Z” es como “Cin” y la salida “C” como “Cout”. Esto debido a que se pueden juntar varios sumadores para crear un sumador más grande con más entradas y salidas y está terminología permite una mejor comprensión de lo que se va a conectar. Esto se verá más adelante en el desarrollo del Sumador Binario de 3 Bits. 

![image](https://github.com/Miguelunch/tt04-submission-template/assets/142178685/5993e941-5e66-4475-9771-0203c13eed41)

Lo que caracteriza al sumador completo de su otra variante (medio sumador) es que, debido a sus tres bits de entrada, puede arrojar ambas salidas a la vez, la salida “S” y la salida carry “C”, esto porque al sumar los tres bits de las entradas es como si se generara un número 3 en binario (1 1). También puede arrojar una sola salida a la vez, ya sea la salida “S” o la salida carry “C” si la suma lo permite, así como en el medio sumador. Se puede ver claramente esto en su tabla de verdad.

![T2](https://github.com/Miguelunch/tt04-submission-template/assets/142178685/93307a57-068e-4830-9367-7456a5cf4148)

Con las expresiones booleanas de las salidas “S” y “C”, es posible generar un circuito con compuertas lógicas, sin embargo, también se puede generar un sumador completo con dos medios sumadores y una compuerta lógica OR de la siguiente manera:

![image](https://github.com/Miguelunch/tt04-submission-template/assets/142178685/96d9d565-3125-4443-b4c0-e084ab06a678)

Se les recuerda que la entrada “Cin” es la entrada “Z” y la salida “Cout” es la salida “C”.

## Sumador Binario de 3 bits

Ya que se sabe cómo funcionan y como se componen el medio sumador y el sumador completo, ya es posible realizar el Sumador Binario de 3 Bits. 
Características del sumador:
•	Va a sumar 2 valores de entrada.
•	Va a tener un sumando de 3 bits de entrada.
•	Va a tener otro sumando de 3 bits de entrada.
•	La salida va a tener en total 4 bits.
•	El valor máximo de cada sumando es de 7 en binario (1 1 1).
•	El valor máximo posible de resultado o salida es de 14 en binario (1 1 1 0).

Para realizar el Sumador Binario de 3 Bits, se tienen que utilizar 3 sumadores completos, los cuales van a ir interconectados de la siguiente manera: 
1.	Los sumadores completos se van a colocar en forma de lista (esto con el fin de tener un orden).
2.	El carry o acarreo (Cout) del primer sumador va a ir conectado al carry de entrada (Cin) del siguiente sumador. Se repite lo mismo, pero con el segundo y el tercer sumador.
3.	El carry de entrada (Cin) del primer sumador no va conectado a nada.
4.	
Por lo tanto, el Sumador Binario de 3 Bits quedaría de la siguiente manera:

![image](https://github.com/Miguelunch/tt04-submission-template/assets/142178685/dff61d0c-cd55-4cec-a5ba-95657ab0ef18)

En donde:

1.	X0, X1 y X2 representan el primer sumando, el cual X0 es el bit de menor valor y X2 es el bit de mayor valor.
2.	Y0, Y1 y Y2 representan el segundo sumando, el cual Y0 es el bit de menor valor y Y2 es el bit de mayor valor.
3.	Las salidas S0, S1 y S2 son los bits de salida que mostraran el resultado, en donde S0 es el bit de menor valor.
4.	El carry del último sumador (Cout) se puede considerar como una salida como si fuera un S3, el cual será el bit de mayor valor.

Finalmente, el Sumador Binario de 3 Bits quedaría de la siguiente manera en la plataforma de WOKWI:

![image](https://github.com/Miguelunch/tt04-submission-template/assets/142178685/a40dea0a-58e2-4598-aae5-70994793f536)


# Restador

https://wokwi.com/projects/373085920015867905 

Existe una forma de realizar un restador de una manera más sencilla a partir del circuito o diagrama de conexión de un sumador. Para este caso, se utilizará el Sumador Binario de 3 Bits para poder realizar un Restador Binario de 3 Bits. Las características del restador serán las siguientes:
•	La resta se va a realizar entre dos valores de entrada.
•	El minuendo (el número a restar) tendrá 3 bits de entrada.
•	El sustraendo (el número que va a restar al minuendo) tendrá 3 bits de entrada.
•	Los valores máximos del minuendo y sustraendo son de 7 en binario (1 1 1).
•	Será posible obtener números negativos
•	La salida va a tener en total 4 bits, de los cuales, el bit más significativo será el del signo.
•	La diferencia máxima posible de resultado o salida es de -7 en binario (0 0 0 1 con complemento a 2).

Para obtener el restador a partir de un sumador, basta con agregar una compuerta lógica XOR a cada una de las entradas de los bits que conforman al sustraendo; una de las patas de las compuertas XOR serán los bits de entrada del sustraendo y las otras patas de las compuertas XOR deben ir conectadas al voltaje de alimentación Vcc; el carry de entrada (Cin) del primer sumador debe de ir conectado de igual manera al voltaje de alimentación Vcc.
Por lo tanto, el Restador Binario de 3 Bits quedaría de la siguiente manera:

![image](https://github.com/Miguelunch/tt04-submission-template/assets/142178685/0e9113a9-586c-4945-96aa-9e9fd718238b)

En donde:
1.	X0, X1 y X2 representan el minuendo, el cual X0 es el bit de menor valor y X2 es el bit de mayor valor.
2.	Y0, Y1 y Y2 representan el sustraendo, el cual Y0 es el bit de menor valor y Y2 es el bit de mayor valor.
3.	Las salidas S0, S1 y S2 son los bits de salida que mostraran el resultado, en donde S0 es el bit de menor valor.
4.	El carry del último sumador (Cout) se puede considerar como una salida como si fuera un S3, el cual será el bit de signo.

Finalmente, el Restador Binario de 3 Bits quedaría de la siguiente manera en la plataforma de WOKWI:

![image](https://github.com/Miguelunch/tt04-submission-template/assets/142178685/80b3c5a3-020d-43e7-b2a2-6be8fad3889f)

# Multiplicador

https://wokwi.com/projects/373066755436024833 

Realizar una multiplicación entre dos bits en números binarios es realmente muy sencillo, ya que, como en una multiplicación normal, cada vez que se multiplica un número por cero el resulta seguirá siendo cero y en el caso de los bits solo tenemos dos números con los cuales trabajar, el uno y el cero.

![T3](https://github.com/Miguelunch/tt04-submission-template/assets/142178685/75b36256-4bc4-4d66-b854-a6075a24bbff)

La parte laboriosa empieza cuando los números a multiplicar tienen más de un bit de entrada, ya que, al igual que una multiplicación normal, después de multiplicar los dos valores numéricos, hay un momento en la multiplicación en donde se tienen que sumar los valores previamente multiplicados.

![image](https://github.com/Miguelunch/tt04-submission-template/assets/142178685/1fecb1e0-9bfb-4341-9d0b-272518fcc5c8)

Por lo tanto, para realizar el Multiplicador Binario de 3 Bits, se va a obtener su circuito de la misma manera que la multiplicación anterior; pero para eso, es necesario utilizar tanto el medio sumador y el sumador completo para realizar la parte de la suma de bits. Las características del multiplicador serán las siguientes:
•	La multiplicación se va a realizar entre dos valores de entrada.
•	El primer factor tendrá 3 bits de entrada.
•	El segundo factor tendrá 3 bits de entrada.
•	Los valores máximos de los factores son de 7 en binario (1 1 1).
•	La salida va a tener en total 6 bits, ya que se deben de sumar los bits de los factores de entrada para poder obtener la cantidad necesaria de bits de salida y abarcar el número más grande de multiplicación.
•	El valor máximo posible de resultado o salida es de 49 en binario (1 1 0 0 0 1).

Para realizar el Multiplicador Binario de 3 Bits, es un proceso más largo y laborioso que las operaciones anteriores, por lo tanto, se seguirán los siguientes pasos:
1.	Se van a acomodar los dos números a multiplicar como en una multiplicación normal, de tal forma que los bits más significativos queden a la izquierda y los menos significativos a la derecha.

![image](https://github.com/Miguelunch/tt04-submission-template/assets/142178685/fa2c1545-d6f7-4855-aa97-87b3c7d9d463)

2.	Ya que se tienen acomodados los números a multiplicar, A0 va a multiplicar todos los números de la parte superior de derecha a izquierda, como en cualquier multiplicación.

![image](https://github.com/Miguelunch/tt04-submission-template/assets/142178685/6692b103-967a-4a5c-93e8-18d935c9a675)

3.	Se repite el mismo procedimiento, pero ahora A1 multiplicará a cada uno de los términos superiores y se recorrerán los resultados obtenidos una casilla a la izquierda.

![image](https://github.com/Miguelunch/tt04-submission-template/assets/142178685/a6540473-5326-414c-be05-a08b55999e47)


4.	Finalmente, A2 multiplicará cada uno de los términos superiores y los resultados obtenidos se recorrerán otra casilla más a la izquierda.

![image](https://github.com/Miguelunch/tt04-submission-template/assets/142178685/c8393d99-8524-47ec-9f57-248d921cd3e5)

5.	Ya que se tienen todas las multiplicaciones, se proceden a sumar los términos en sus columnas correspondientes empezando de derecha a izquierda. Como se puede observar, A0*B0 no tiene nadie con quien sumarse, por lo tanto, el resultado de esa multiplicación se pasa directo como el resultado a mostrar, el cual se denominará S0.

![image](https://github.com/Miguelunch/tt04-submission-template/assets/142178685/08cc3e7f-1ec8-41f3-a7ca-07fbe799d3ff)

6.	Las siguientes multiplicaciones por sumar son A0*B1 con A1*B0 y, algo que hay que dejar muy en claro es que, cada vez que se cada vez que sumen dos términos, se va a utilizar un medio sumador, y también debemos de recordar que los medios sumadores solo pueden generar una salida “S” o un carry “C” nunca los dos al mismo tiempo, pero esto se comprenderá mejor más adelante. Por lo tanto, la suma entre A0*B1 con A1*B0 genera una salida S1 o un carry C0, quedando de la siguiente manera.

![image](https://github.com/Miguelunch/tt04-submission-template/assets/142178685/bef438c8-6ceb-4932-ab90-420533d989c5)

7.	Supongamos que de la suma anterior se genera el carry C0, eso quiere decir que se va a sumar con el siguiente conjunto de términos, los cuales son A0*B2, A1*B1 y A2*B0. Lo primero que se tiene que hacer es sumar el carry C0 con los primeros dos términos mencionados anteriormente, entonces se sumarían C0 con A0*B2 y con A1*B1, en esta ocasión se sumaran tres términos a la vez. También, algo que dejar muy en claro es que, cada vez que se cada vez que sumen tres términos, se va a utilizar un sumador completo, y también debemos de recordar que los sumadores completos pueden generar tanto una salida “S” y un carry “C” al mismo tiempo. Por lo tanto, la suma entre C0 con A0*B2 y con A1*B1, genera una salida R0 o un carry C1. En esta ocasión la salida se colocó como R0 (aunque puede tener el nombre que deseé el usuario) en lugar de S2 ya que todavía queda un término por sumar en este conjunto de términos (A2*B0). La suma quedaría de la siguiente manera.

![image](https://github.com/Miguelunch/tt04-submission-template/assets/142178685/6534db31-7610-4144-a8fb-186ec55200da)

8.	Como se puede observar, de la suma anterior se generaron una salida R0 y un carry C1. Por el momento se guardará y no se utilizará el carry C1 ya que, como su nombre lo indica (carry o acarreo), pasa a sumarse con el siguiente grupo de términos (A1*B2 y A2*B1), entonces, la salida R0 esta libre para utilizarse. La salida R0 se sumará con A2*B0, por lo tanto, se utilizará un medio sumador y las salidas que genera esta suma son la salida S2 ó el carry C2, quedando de la siguiente manera:

![image](https://github.com/Miguelunch/tt04-submission-template/assets/142178685/06f6bb2c-7f00-4b25-8d56-2307948da777)

9.	Como se puede observar, ahora se tienen dos carrys (C1 y C2) y ambos pasan a sumarse con el siguiente grupo de términos (A1*B2 y A2*B1), por lo tanto, se empezarán a sumar 3 términos en orden como se fueron generando. Entonces, se van a sumar C1 con C2 y con A1*B2 y la suma de estos tres términos generan una salida R1 y un carry C3.

![image](https://github.com/Miguelunch/tt04-submission-template/assets/142178685/8ce3f450-9030-47f1-a15d-5c5f360e7ca0)

10.	Nuevamente, el carry C3 se guarda para el siguiente grupo de términos (A2*B2) y la salida R1 se va a utilizar en el grupo de término actual. Por lo tanto, se van a sumar la salida R1 con A2*B1 y la suma de estos dos términos da como resultado una salida S3 o un carry C4.

![image](https://github.com/Miguelunch/tt04-submission-template/assets/142178685/26d852ae-41a3-4ce8-abf2-d2c0c3e1b824)

11.	Por segunda ocasión, se tienen dos carrys (C3 y C4) y ambos pasan a sumarse con el último grupo de términos (A2*B2). Por lo tanto, la suma de C3 con C4 y A2*B2 dan como resultado una salida S4 y un carry C5. El carry C5 pasaría al siguiente grupo de términos, pero como ya no queda nada con que sumar, pasa directamente como una salida, quedando de la siguiente manera:

![image](https://github.com/Miguelunch/tt04-submission-template/assets/142178685/8cad16bc-6bfe-47a6-84e4-e49bb93a64fc)

12.	Finalmente, el Multiplicador Binario de 3 Bits quedaría de la siguiente manera, en donde:
•	A0, A1 y A2 representan el primer término a multiplicar, el cual A0 es el bit de menor valor y A2 es el bit de mayor valor.
•	B0, B1 y B2 representan el segundo término a multiplicar, el cual B0 es el bit de menor valor y B2 es el bit de mayor valor.
•	Los términos marcados de color MORADO son las multiplicaciones previas antes de pasar a los sumadores. Para eso, se utilizan compuertas AND.
•	Los términos marcados de color ROJO son las salidas del Multiplicador. S0 es el bit de menor valor y C5 el bit de mayor valor.
•	Las sumatorias marcadas de color AZUL son los términos que requieren un sumador completo.
•	Las sumatorias marcadas de color VERDE son los términos que requieren un medio sumador.

![image](https://github.com/Miguelunch/tt04-submission-template/assets/142178685/3b03139a-8597-481c-8f51-0ba03bab3d76)

El Multiplicador Binario de 3 Bits quedaría de la siguiente manera en la plataforma de WOKWI:

![image](https://github.com/Miguelunch/tt04-submission-template/assets/142178685/e0693c50-a743-4656-9c77-f85e0ab9a012)

# Contador

https://wokwi.com/projects/373174994558429185 

Para este caso, se van a realizar dos contadores, los cuales van a estar trabajando de manera diferente con una misma señal de reloj. 

## Contador Síncrono de 4 bits

El primer contador que se realizará a continuación consiste en un contador síncrono 4 bits, esto quiere decir que va a necesitar 4 Flip-Flops de tipo D (se puede hacer con otro tipo de Flip-Flop) y será síncrono porque todos estos Flip-Flops utilizan una misma señal de reloj para poder funcionar. Las características de este primer contador serán las siguientes:
•	Utilizará 4 Flip-Flops tipo D.
•	Tendrá una señal de reloj automática de 1 de frecuencia o en su defecto, puede utilizar un botón como señal de reloj.
•	Para activarse, tendrá un switch que permita el paso de la señal de reloj.
•	Será capaz de contar de cero hasta 15 en binario (1 1 1 1) y de ahí volverá a contar desde cero.

Para este caso, no será necesario utilizar la tabla de verdad del Flip-Flop de tipo D, pero lo que sí se va a requerir es su Tabla de Transición o también llamada Tabla de Excitación, de la cual se obtendrán los estados cambiantes del Flip-Flop con forme pasa un periodo de tiempo y de ahí realizar una tabla de verdad en la que se muestre como van a ir cambiando los bits de salida para obtener los números binarios en orden.

![image](https://github.com/Miguelunch/tt04-submission-template/assets/142178685/7a74b943-5720-40e9-8902-136c91e12516)

![image](https://github.com/Miguelunch/tt04-submission-template/assets/142178685/11293979-f57e-4ef5-8e71-1fa21091923e)

1.	Como primer paso para realizar la tabla de verdad, se empezará haciendo una tabla donde se muestren todos los números posibles que se pueden crear con esos 4 bits de salida de los Flip-Flops, la cual se denominará Estado Actual Q(t) ya que, como su nombre lo indica, son los bits de salida previo a un cambio con forme al tiempo. A un lado se van a colocar las salidas futuras de los Flip-Flops denominada como Estado Futuro Q(t+1) y también se van a agregar la entrada de datos de cada uno de los Flip-Flops. Para identificar los Flip-Flops junto con sus entradas y salidas, se llamarán de la siguiente manera:
•	Flip-Flop A: Entrada de datos: DA; Salida de datos: QA
•	Flip-Flop B: Entrada de datos: DB; Salida de datos: QB
•	Flip-Flop C: Entrada de datos: DC; Salida de datos: QC
•	Flip-Flop D: Entrada de datos: DD; Salida de datos: QD

Por lo tanto, la tabla queda de la siguiente manera:

![image](https://github.com/Miguelunch/tt04-submission-template/assets/142178685/edc96b6f-4818-4e10-b6ae-dd19d753a07d)

2.	Para llenar la parte de Estado Futuro Q(t+1), es necesario fijarse en los bits del Estado Actual Q(t) y colocar el número que se desea que le suceda, por ejemplo: Se tiene el número cero (0 0 0 0) en la parte de Estado Actual Q(t) y se desea que cambie a uno (0 0 0 1), por lo tanto, en la parte de Estado Futuro Q(t+1) se colocarán los bits del número uno (0 0 0 1). Si se desea que el número once (1 0 1 1) cambié a doce, en el Estado Futuro Q(t+1) se deben de colocar los bits de ese número (1 1 0 0). Para este caso todos los números son consecutivos, entonces, la tabla queda de la siguiente manera:

![image](https://github.com/Miguelunch/tt04-submission-template/assets/142178685/2218a661-bd8a-4d7b-be59-543abb97d056)

3.	Para llenar las entradas de datos “D” de los Flip-Flops es necesario utilizar la Tabla de Excitación para observar como van cambiando las salidas Q del Estado Actual Q(t) al Estado Futuro Q(t+1), por ejemplo, para llenar la primera casilla del Flip-Flop D, se tiene que observar cómo cambia QD del Estado Actual Q(t) al Estado Futuro Q(t+1). Para este primer ejemplo, se puede observar que en el Estado Actual Q(t) esta en 0 y en el Estado Futuro Q(t+1) pasa a 1, por lo tanto, la entrada de datos “D” es 0 como indica la Tabla de Excitación.

![image](https://github.com/Miguelunch/tt04-submission-template/assets/142178685/f1c740fc-c71e-4670-9c38-1c276d26c584)

![image](https://github.com/Miguelunch/tt04-submission-template/assets/142178685/6904f85c-c630-40ed-b9dd-01eb070ca34c)

4.	Siguiendo este método, se llenan todas las casillas de entrada de datos “D” del Flip-Flop D.

![image](https://github.com/Miguelunch/tt04-submission-template/assets/142178685/c786bea1-8ee5-4a93-93d5-e242c0e5121e)

5.	Se repite este mismo procedimiento con las otras entradas de datos de los Flip-Flops faltantes. La tabla de verdad queda de la siguiente manera:

![image](https://github.com/Miguelunch/tt04-submission-template/assets/142178685/08613aac-b3ba-42ea-8881-e82215faff12)

6.	El siguiente paso es obtener una expresión Booleana de cada entrada de datos “D”, para realizar esto, se puede utilizar Algebra Booleana o mapas de Karnaugh. Para este caso, se realizaron mapas de Karnaugh con la herramienta en línea de The Quine-McCluskey Solver. Para obtener la expresión Booleana de la entrada de datos “DD” del Flip-Flop D se utiliza todas las salidas Q del Estado Actual Q(t).

![image](https://github.com/Miguelunch/tt04-submission-template/assets/142178685/3a0cedbb-eda5-4031-96ab-cea132ecb02d)

![image](https://github.com/Miguelunch/tt04-submission-template/assets/142178685/276d3055-ca64-4c39-b85f-ac37315e575d)

7.	Utilizando este método, la mínima expresión Booleana de la entrada de datos “DD” es: DD = QD'.

8.	Por lo tanto, las mínimas expresiones Booleanas de cada una de las entradas de datos son las siguientes:

![image](https://github.com/Miguelunch/tt04-submission-template/assets/142178685/63f09f58-0db5-4674-b552-3c49c69dbca5)

# Contador Síncrono de 2 bits

El segundo contador que se realizará a consiste en un contador síncrono 2 bits, esto quiere decir que va a necesitar 2 Flip-Flops de tipo D (se puede hacer con otro tipo de Flip-Flop) y será síncrono porque todos estos Flip-Flops utilizan una misma señal de reloj para poder funcionar. Las características de este primer contador serán las siguientes:
•	Utilizará 2 Flip-Flops tipo D.
•	Tendrá una señal de reloj automática de 1 de frecuencia o en su defecto, puede utilizar un botón como señal de reloj.
•	Para activarse, tendrá un switch que permita el paso de la señal de reloj.
•	Aunque es capaz de contar hasta 3 en binario (1 1), solamente mostrará dos valores, el uno (0 1) y el dos (1 0), simulando como si se apagaran y se encendieran dos leds de manera intercalada.

Al igual que el contador anterior, se utilizará la Tabla de Excitación del Flip-Flop tipo D, de la cual se obtendrán los estados cambiantes del Flip-Flop con forme pasa un periodo de tiempo y de ahí realizar una tabla de verdad en la que se muestre como van a ir cambiando los bits de salida para obtener los números binarios.

1.	Como primer paso para realizar la tabla de verdad, se empezará haciendo una tabla donde se muestren todos los números posibles que se pueden crear con esos 2 bits de salida de los Flip-Flops, la cual se denominará Estado Actual Q(t). A un lado se van a colocar las salidas futuras de los Flip-Flops denominada como Estado Futuro Q(t+1) y también se van a agregar la entrada de datos de cada uno de los Flip-Flops. Para identificar los Flip-Flops junto con sus entradas y salidas, se llamarán de la siguiente manera:
•	Flip-Flop X: Entrada de datos: DX; Salida de datos: QX
•	Flip-Flop Y: Entrada de datos: DY; Salida de datos: QY
Por lo tanto, la tabla queda de la siguiente manera:

![image](https://github.com/Miguelunch/tt04-submission-template/assets/142178685/62389a20-3593-492d-a4c8-1f68fdd8c3c0)

2.	Para llenar la parte de Estado Futuro Q(t+1), es necesario fijarse en los bits del Estado Actual Q(t) y colocar el número que se desea que le suceda. Para este caso, se tiene el número uno (0 1) en la parte de Estado Actual Q(t) y se desea que cambie a dos (1 0), por lo tanto, en la parte de Estado Futuro Q(t+1) se colocarán los bits del número dos (1 0). Se tiene el número dos (1 0) en la parte de Estado Actual Q(t), y para que cambie a uno (0 1) se deben de colocar los bits de salida en la parte de Estado Futuro Q(t+1). Con estos dos cambios en la transición, se dará el efecto de que los leds parpadean de forma intercalada. La tabla queda de la siguiente manera:

![image](https://github.com/Miguelunch/tt04-submission-template/assets/142178685/45282f04-e2ee-412c-a69d-34e067403f2e)

3.	Como se puede apreciar, hay casillas vacías en la parte de Estado Futuro Q(t+1). Esas partes se van a llenar solamente con números ceros, de esta manera estos estados de transición no se ejecutarán en el resultado final.

![image](https://github.com/Miguelunch/tt04-submission-template/assets/142178685/09960ce9-fbd4-4b37-bfd1-a61b0c098a21)

4.	Al igual que el contador anterior, las entradas de datos “D” se van a llenar con la Tabla de Excitación del Flip-Flop tipo D, por lo tanto, la tabla de verdad resultante es la siguiente:

![image](https://github.com/Miguelunch/tt04-submission-template/assets/142178685/9a287d32-f261-48a4-a0a5-67b98739eb9e)

5.	El siguiente paso es obtener una expresión Booleana de cada entrada de datos “D”, para realizar esto, se puede utilizar Algebra Booleana o mapas de Karnaugh. Para este caso, se realizaron mapas de Karnaugh con la herramienta en línea de The Quine-McCluskey Solver. Se les recuerda que para obtener las expresiones Booleanas de las entradas de datos “D” se utiliza todas las salidas Q del Estado Actual Q(t).

![image](https://github.com/Miguelunch/tt04-submission-template/assets/142178685/9f62eb38-80d8-44b6-b01f-0f4f4d921757)

## Diagrama de conexión de los contadores

Cabe recalcar que la salida Q del Flip-Flop A es el bit más significativo del contador, mientras que salida Q del Flip-Flop D es el bit menos significativo. También se puede apreciar que tanto la señal de Reloj como el Switch de activación están conectados a una misma compuerta AND, esto para que los contadores se activen cuando se encienda el Switch.

![image](https://github.com/Miguelunch/tt04-submission-template/assets/142178685/6a685855-b858-457b-b527-599aac34dd70)












![](../../workflows/gds/badge.svg) ![](../../workflows/docs/badge.svg) ![](../../workflows/wokwi_test/badge.svg)

# What is Tiny Tapeout?

TinyTapeout is an educational project that aims to make it easier and cheaper than ever to get your digital designs manufactured on a real chip!

Go to https://tinytapeout.com for instructions!

## How to change the Wokwi project

Edit the [info.yaml](info.yaml) and change the wokwi_id to match your project.

## How to enable the GitHub actions to build the ASIC files

Please see the instructions for:

- [Enabling GitHub Actions](https://tinytapeout.com/faq/#when-i-commit-my-change-the-gds-action-isnt-running)
- [Enabling GitHub Pages](https://tinytapeout.com/faq/#my-github-action-is-failing-on-the-pages-part)

## How does it work?

When you edit the info.yaml to choose a different ID, the [GitHub Action](.github/workflows/gds.yaml) will fetch the digital netlist of your design from Wokwi.

After that the action uses the open source ASIC tool called [OpenLane](https://www.zerotoasiccourse.com/terminology/openlane/) to build the files needed to fabricate an ASIC.

## Resources

- [FAQ](https://tinytapeout.com/faq/)
- [Digital design lessons](https://tinytapeout.com/digital_design/)
- [Learn how semiconductors work](https://tinytapeout.com/siliwiz/)
- [Join the community](https://discord.gg/rPK2nSjxy8)

## What next?

- Submit your design to the next shuttle [on the website](https://tinytapeout.com/#submit-your-design), the closing date is 8th September.
- Share your GDS on Twitter, tag it [#tinytapeout](https://twitter.com/hashtag/tinytapeout?src=hashtag_click) and [link me](https://twitter.com/matthewvenn)!
