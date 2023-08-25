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
