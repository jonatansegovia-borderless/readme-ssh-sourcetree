# CONFIGURACIÓN DE SOURCETREE CON KEY SSH DE GITHUB

(PARA LEER ESTE ARCHIVO DE MANERA MÁS AMENA DEBERÍA TOCAR LA SIGUIENTE COMBINACIÓN DE TECLAS)

```shell
ctrl + shift + v
```

## GENERACIÓN DE SSH EN GITHUB:

1 - Descargar sourcetree https://sourcetreeapp.com/

2 - Seguir los pasos en la documentación de GitHub para conectar una SSH key a nuestro local https://docs.github.com/en/authentication/connecting-to-github-with-ssh

- 2.1 - Verificar en terminal si contamos con una key ya generada en nuestro local

![](./img/1.png)

- 2.2 - Si contamos con esta podemos seguir al paso 3.1
- 2.3 - Sino contamos con archivos como los específicados en la imagen de arriba debemos crear esta key
- 2.4 - Generando una key https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent

3 - En terminal ponemos el código a continuación, reemplazando por nuestro mail y dejando todo por default con enter, esto genera un archivo que podremos ver con el código de la referencia 2.1

![](./img/2.png)

- 3.1 - Vamos a la carpeta adonde generamos esta key y abrimos la misma con algún notepad o similar

![](./img/3.png)

- 3.2 - Copiamos todo ese código y vamos a la nuestra cuenta ade GitHub
- 3.3 - Abrimos Settings y dentro buscamos "

![](./img/4.png)

![](./img/5.png)

- 3.4 - Ahora tocamos en el botón New SSH key

![](./img/6.png)

- 3.5 - Ponemos un título y pegamos lo copiado en el punto 3.2, le damos al botón Add

- 3.6 - De esta manera la conexión entre nuestra cuenta de GitHub y nuestros trabajo locales quedará establecidas

## VINCULACIÓN CON SOURCETREE:

1 - Abrimos ST

- 1.1 - Skip a la opción de Bitbucket

- 1.2 - Destildamos el checkbox 'mercurial' y tocamos Next

  ![](./img/7.png)

- 1.3 - Agregamos un nombre de user y el mail de la empresa, next.

  ![](./img/8.png)

* 1.4 - Nos saldrá el siguiente cartel y seleccionamos 'no'

  ![](./img/9.png)

## Trabajando con ST

2 - Vamos al repo que queremos clonar y copiamos la opción con SSH.

![](./img/10.png)

- 2.1 - Otra vez ST apretamos el botón 'clone'

  ![](./img/11.png)

- 2.2 - Pegamos lo copiado en el punto 2 dentro de la zona indicada y le damos a enter (o puede hacerlo automático).

  ![](./img/12.png)

- 2.3 - Nos saldrá la siguiente leyenda y debemos tocar 'Yes'

  ![](./img/13.png)

- 2.4 - Nos pregunta si tenemos un SSH generada, le damos a no, porque la extensión de nuestra SSH no va a ser reconocida por putty, que es el programa que nos va a convertir a .ppk nuestra key para que funcione

  ![](./img/14.png)

## Putty

3 - Putty nos permite modificar la extensión de nuestra key para que pueda ser reconocida. A este accedemos de la siguiente manera dentro de ST.

- 3.1 - En la barra de ST Tools / Create or Import

  ![](./img/16.png)

- 3.2 - Nos aparecerá la siguiente ventana en donde tocaremos 'Load'

  ![](./img/17.png)

- 3.3 - (Suponiendo que nos abre la carpeta adonde tenemos nuestra SSH key, sino navegar hasta esta) Al tocar este botón nos querrá abrir un archivo .ppk pero aún no existe, por ende tocamos debajo en 'All files' para que nos liste todos los archivos disponibles

  ![](./img/21.png)

- 3.4 - Elegimos nuestra SSH y le damos a 'Abrir'

  ![](./img/22.png)

- 3.5 - Esto hará automáticamente un proceso de conversión de nuestra key a .ppk, dándonos como resultado el siguiente mensaje, tocamos 'Aceptar'.

  ![](./img/23.png)

- 3.6 - Tocamos en 'Save private key', nos preguntará si queremos activarla sin usar un passphrase, le damos a 'Sí'

  ![](./img/24.png)
  ![](./img/25.png)

- 3.7 - Nuevamente nos abrirá la ruta donde tenemos nuestras SSH, pero esta vez con la finalidad de que le demos un nombre a la misma. Lo hacemos y tocamos 'Guardar'. Esto convirtió la SSH a .ppk, pero aún debemos conectar nuestro proyecto con la misma.

  ![](./img/26.png)

## Conectando el proyecto con la SSH .ppk

4 - Abrimos Putty para autenticarnos, este se encuentra ahora abajo a la izquierda.

![](./img/28.png)

- 4.1 - Al hacerlo nos dará la posibilidad de cargar ls SSH .ppk que creamos en el paso 3, le damos a 'Add key'

  ![](./img/27.png)

- 4.2 - Nos abrirá la carpeta (y sino navegar hasta esta) en donde tenemos las SSH, y debemos elegir la que creamos, en mi caso 'perp.ppk'

  ![](./img/29.png)

- 4.3 - Esto provoca que a partir de ahora ST esté vinculado a nuestra SSH.

## Conectándo al proyecto

5 - Volvemos a ST, y realizamos nuevamente el paso 2 y 2.1 (ir a GitHub y copiarnos el repo a clonar)

- 2.1 - Otra vez ST apretamos el botón 'clone'
  ![](./img/11.png)

- 2.2 - Pegamos lo copiado en el punto 2 dentro de la zona indicada y le damos a enter (o puede hacerlo automático).
  ![](./img/12.png)

- 5.1 - elegimos un destino para nuestro proyecto, le ponemos el nombre correspondiente, tocamos 'Advanced options' y dentro de 'Checkout branch' elegimos 'Develop' como en la imagen.

  ![](./img/31.png)

- 5.2 - También deríamos tener marcado el checkbox 'Recurse submodules'.

  ![](./img/32.png)

- 5.3 - Le damos a 'Clone' y clonará el mismo. Ya deberíamos ver el proyecto sin problemas.

  ![](./img/34.png)
