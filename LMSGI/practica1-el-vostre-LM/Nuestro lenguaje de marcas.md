# Juason mark lang

## Juason - Práctica 1: Lenguajes de marcas

Autores: Arnau Postigo y Zehui Wang
Curso: 1. ASIX
Módulo: Lenguajes de marcas

Nuestro proyecto consiste en crear un lenguaje de marcas propio llamado Juason. Su objetivo es guardar la información de las partidas de un videojuego llamado eljuego.py.

El lenguaje utiliza archivos de texto con la extensión .juson.

## 1. ¿Qué es un lenguaje de marcas?

Un lenguaje de marcas es una forma de organizar información utilizando texto y símbolos que permiten identificar las diferentes partes de un documento.

Estos lenguajes pueden servir tanto para representar información como para indicar cómo debe interpretarse o mostrarse.

Su origen está relacionado con las marcas que se utilizaban en las imprentas para indicar cómo debía aparecer el texto.

Con el desarrollo de la informática aparecieron diferentes lenguajes de marcas:

1969: GML, desarrollado en IBM.

1986: SGML, convertido en un estándar internacional.

1991: HTML, utilizado para crear páginas web.

1998: XML, diseñado para estructurar e intercambiar información.

## ¿Para qué sirven los lenguajes de marcas?

Los lenguajes de marcas tienen diferentes aplicaciones.

Páginas web: HTML permite organizar el contenido de una página mediante títulos, párrafos, enlaces e imágenes.

Almacenamiento de datos: XML permite guardar información de forma estructurada para que pueda ser interpretada por programas.

Documentación: Markdown permite crear documentos con títulos, listas y otros elementos utilizando texto sencillo.

Documentos de oficina: los formatos DOCX y PPTX utilizan internamente documentos XML.

Una de sus principales ventajas es que muchos de estos lenguajes pueden escribirse con un editor de texto normal.

## Nuestro lenguaje: Juason

Juason es un lenguaje de marcas que hemos diseñado para guardar las partidas de eljuego.py, un juego de rol por turnos.

La idea es que toda la información necesaria para recuperar una partida pueda almacenarse en un archivo de texto.

Por ejemplo, necesitamos guardar:

El nombre del jugador.

La vida actual y la vida máxima.

Los objetos que tiene en su inventario.

Las pociones y los amuletos.

Las habilidades que tiene activadas.

Juason permite organizar todos estos datos mediante unas reglas sencillas.

El proyecto es un prototipo, por lo que todavía no hemos desarrollado un programa que interprete automáticamente los archivos.

## ¿Cómo funciona Juason?

Juason utiliza distintas marcas para organizar los datos.

Los nombres identifican qué información se está guardando.

Los dos puntos indican que un elemento contiene otros datos.

Las barras indican el nivel de profundidad de un elemento dentro de otro.

Los corchetes permiten agrupar varios datos que pertenecen a un mismo objeto.

Los puntos y coma separan los elementos de una lista.

Los textos se escriben entre comillas simples.

Los valores numéricos se escriben directamente.

Para los valores de verdadero o falso utilizamos las letras t y f.

De esta manera, el lenguaje permite distinguir entre diferentes tipos de información sin necesidad de utilizar un formato complicado.

## Reglas de Juason

Para que el lenguaje funcione correctamente hemos establecido algunas reglas.

Los nombres de los elementos se escriben en minúsculas, sin espacios ni tildes. Si necesitamos separar palabras, utilizamos el guion bajo.

Los elementos principales no llevan barras delante.

Los elementos que se encuentran dentro de un grupo llevan una barra.

Los elementos que están dentro de un subgrupo llevan dos barras.

Cada barra adicional representa un nivel más de profundidad.

Los grupos se identifican mediante dos puntos.

Las listas contienen elementos agrupados entre corchetes, que pueden separarse mediante puntos y coma.

Dentro de los corchetes, los datos de cada objeto se escriben sin barras, porque ya pertenecen al objeto correspondiente.

Los valores pueden ser textos, números o valores booleanos.

## Clasificación de nuestro lenguaje

Los lenguajes de marcas pueden clasificarse según su función.

Lenguajes de presentación: indican cómo debe mostrarse la información.

Lenguajes procedimentales: contienen instrucciones relacionadas con el formato del contenido.

Lenguajes descriptivos o semánticos: identifican qué representa cada elemento.

Juason pertenece principalmente al grupo de los lenguajes descriptivos o semánticos.

Esto se debe a que sus marcas indican el significado de los datos, pero no su apariencia.

Por ejemplo, Juason permite identificar la vida actual de un personaje, pero no indica si debe mostrarse mediante una barra verde, un número o cualquier otro elemento visual.

Esa decisión correspondería al videojuego.

## Ejemplo de uso de Juason

Imaginemos una partida de eljuego.py con la siguiente información.

El jugador se llama apb.

Su personaje tiene 200 puntos de vida máxima y actualmente conserva 38.

En su inventario tiene dos pociones.

La primera tiene un valor de vida de 12, un efecto de ataque y una calidad épica.

La segunda tiene un valor de vida de -5, un efecto de curación y una calidad normal.

También tiene dos amuletos con esas mismas características.

Por último, tiene tres habilidades pasivas.

La primera está activada.

La segunda está desactivada.

La habilidad de ascenso está activada.

Toda esta información puede guardarse en un archivo .juson utilizando las reglas que hemos definido.

## ¿Cuándo sería útil Juason?

Un ejemplo de uso sería el sistema de guardado de eljuego.py.

Cuando el jugador cierre el juego, el programa podría guardar el estado de la partida en un archivo .juson.

Cuando vuelva a abrirlo, el programa podría leer ese archivo y recuperar los datos.

Este sistema tendría algunas ventajas.

Los archivos podrían abrirse con cualquier editor de texto.

La información estaría organizada de forma sencilla.

Los datos serían relativamente fáciles de modificar manualmente.

El juego podría interpretar los diferentes elementos siguiendo las reglas del lenguaje.

Además, al tratarse de texto plano, no necesitaríamos un programa especial para visualizar el contenido del archivo.

## ¿Cuándo no sería adecuado Juason?

Juason está pensado para almacenar información de partidas, pero no sería adecuado para cualquier situación.

Por ejemplo, no sería la mejor opción para crear la página web de eljuego.py.

Una página web necesita títulos, párrafos, enlaces, imágenes y otros elementos visuales.

Juason puede identificar datos, pero no dispone de marcas específicas para diseñar una página web.

En ese caso sería más adecuado utilizar HTML o Markdown.

Tampoco sería recomendable utilizar archivos Juason como único sistema para guardar los datos de un juego multijugador con miles de usuarios.

Para ese tipo de situaciones sería más conveniente utilizar una base de datos.

Otro inconveniente es que los archivos pueden modificarse fácilmente, por lo que no serían seguros para almacenar información que el jugador no debería poder alterar.

## Conclusión

Con esta práctica hemos aprendido cómo funcionan los lenguajes de marcas y cuáles son sus principales características.

Hemos creado Juason, un lenguaje sencillo basado en texto plano que permite organizar y almacenar los datos de un videojuego.

También hemos definido sus reglas, su clasificación y algunas situaciones en las que podría utilizarse.

Aunque todavía es un prototipo, nos ha permitido comprender cómo las marcas pueden dar estructura y significado a la información.

Aquí se puede ver las fases o ideas de desarrollo de nuestro idioma de lenguaje.

## ver 3 - unkown weirdo

```
name 'apb'
stats:
/pv:
//maximo 200
//actual 38

items:
/pociones [
  vida 12
  effecto 'attaque'
  calidad 'epico'
 ];
 [
  vida -5
  effecto 'curacion'
  calidad 'normal'
 ]
/amuletos:
  [
    vida 12
    effecto 'attaque'
    calidad 'epico'
   ];
   [
    vida -5
    effecto 'curacion'
    calidad 'normal'
   ]

habilidades:
/pasiva_1 t
/pasiva_2 f
/pasiva_ascenso t
```




## ver 2 - minimalistic star
```
name 'apb'
capitulo 1
stats (
  pv (
    maximo 200
    actual 38
  )
  items [
    vida 12
    effecto 'attaque'
    calidad 'epico'
  ],
  [
    vida -5
    effecto 'curacion'
    calidad 'normal'
  ]
)
```


## ver 1 - chonky lang

```
/name 'apb'
/stats:
//pv:
///maximo 200
///actual 38

/items:
//pociones [
  /vida 12
  /effecto 'attaque'
  /calidad 'epico'
 ];
 [
  /vida -5
  /effecto 'curacion'
  /calidad 'normal'
 ]
//amuletos:
  [
    /vida 12
    /effecto 'attaque'
    /calidad 'epico'
   ];
   [
    /vida -5
    /effecto 'curacion'
    /calidad 'normal'
   ]

/habilidades:
//pasiva_1 t
//pasiva_2 f
//pasiva_ascenso t
``` 

## ver 1 - array variant - promising?

```
/name 'apb'
/stats:
//pv:
///maximo 200
///actual 38

/items:
//pociones:
///*
///vida 12
///effecto 'attaque'
///calidad 'epico'
///*
///*
///vida -5
///effecto 'curacion'
///calidad 'normal'
///*

//amuletos:
///*
///vida 12
///effecto 'attaque'
///calidad 'epico'
///*
///*
///vida -5
///effecto 'curacion'
///calidad 'normal'
///*

/habilidades:
//pasiva_1 t
//pasiva_2 f
//pasiva_ascenso t
``` 



Prueba rancia num x times / before / for recursion level

```
78/problemas:
79/muchos 'problemas'
```
