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

Medio Sumador
X	Y	Suma (S)	Carry (C)	Mínima Expresión Booleana
0	0	0	0	S = (X' Y) + (X' Y) = X⊕Y
0	1	1	0	C = X Y
1	0	1	0	
1	1	0	1	












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
