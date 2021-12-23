# CONFIGURACIÓN DE SOURCETREE CON KEY SSH DE GITHUB

(PARA LEER ESTE ARCHIVO DE MANERA MÁS AMIGABLE SE RECOMIENDA TOCAR LA SIGUIENTE COMBINACIÓN DE TECLAS)

```shell
clonar este repositorio a su computador y luego dentro del readme tocar el siguiente comando

ctrl + shift + v

```

## GENERACIÓN DE SSH EN GITHUB:

1 - Seguir los pasos en la documentación de GitHub para conectar una SSH key a nuestro local https://docs.github.com/en/authentication/connecting-to-github-with-ssh

## VINCULACIÓN CON SOURCETREE:

2 - Abrimos ST

- 2.1 - Skip a la opción de Bitbucket

- 2.2 - Destildamos el checkbox 'mercurial' y tocamos Next

  ![](./img/7.png)

- 2.3 - Agregamos un nombre de user y el mail de la empresa, next.

  ![](./img/8.png)

* 2.4 - Nos saldrá el siguiente cartel y seleccionamos 'no'

  ![](./img/9.png)

## Trabajando con ST

3 - Vamos al repositorio que queremos clonar y copiamos la opción con SSH.

![](./img/10.png)

- 3.1 - Otra vez ST apretamos la opción 'clone'.

  ![](./img/11.png)

- 3.2 - Pegamos la ruta SSH correspondiente al repositorio que necesitamos dentro de la zona indicada y le damos a enter (o puede hacerlo automático).

  ![](./img/12.png)

- 3.3 - Nos saldrá la siguiente leyenda y debemos tocar 'Yes'

  ![](./img/13.png)

- 3.4 - Nos pregunta si tenemos un SSH generada, le damos a no, porque la extensión de nuestra SSH no va a ser reconocida por putty, que es el programa que nos va a convertir a .ppk nuestra key para que funcione

  ![](./img/14.png)

## Putty

4 - Putty nos permite modificar la extensión de nuestra key para que pueda ser reconocida. A este accedemos de la siguiente manera dentro de ST.

- 4.1 - En la barra de ST Tools / Create or Import

  ![](./img/16.png)

- 4.2 - Nos aparecerá la siguiente ventana en donde tocaremos 'Load'

  ![](./img/17.png)

- 4.3 - (Suponiendo que nos abre la carpeta adonde tenemos nuestra SSH key, sino navegar hasta esta) Al tocar este botón nos querrá abrir un archivo .ppk pero aún no existe, por ende tocamos debajo en 'All files' para que nos liste todos los archivos disponibles

  ![](./img/21.png)

- 4.4 - Elegimos nuestra SSH y le damos a 'Abrir'

  ![](./img/22.png)

- 4.5 - Esto hará automáticamente un proceso de conversión de nuestra key a .ppk, dándonos como resultado el siguiente mensaje, tocamos 'Aceptar'.

  ![](./img/23.png)

- 4.6 - Tocamos en 'Save private key', nos preguntará si queremos activarla sin usar un passphrase, le damos a 'Sí'

  ![](./img/24.png)
  ![](./img/25.png)

- 4.7 - Nuevamente nos abrirá la ruta donde tenemos nuestras SSH, pero esta vez con la finalidad de que le demos un nombre a la misma. Lo hacemos y tocamos 'Guardar'. Esto convirtió la SSH a .ppk, pero aún debemos conectar nuestro proyecto con la misma.

  ![](./img/26.png)

## Conectando el proyecto con la SSH .ppk

5 - Abrimos Putty para autenticarnos, este se encuentra ahora abajo a la izquierda.

![](./img/28.png)

- 5.1 - Al hacerlo nos dará la posibilidad de cargar ls SSH .ppk que creamos. Le damos a 'Add key'

  ![](./img/27.png)

- 5.2 - Nos abrirá la carpeta (y sino navegar hasta esta) en donde tenemos las SSH, y debemos elegir la que creamos, en mi caso 'perp.ppk'

  ![](./img/29.png)

- 5.3 - Esto provoca que a partir de ahora ST esté vinculado a nuestra SSH.

## Clonando el proyecto

6 - Volvemos a ST, con el código SSH del repositorio a clonar copiado

- 6.1 - Apretamos la opción 'clone'
  ![](./img/11.png)

- 6.2 - Pegamos lo copiado dentro de la zona indicada y le damos a enter (o puede hacerlo automático).
  ![](./img/12.png)

- 6.1 - Elegimos un destino para nuestro proyecto, le ponemos el nombre correspondiente, tocamos 'Advanced options' y dentro de 'Checkout branch' elegimos 'Develop' como en la imagen.

  ![](./img/31.png)

- 6.3 - También deríamos tener marcado el checkbox 'Recurse submodules'.

  ![](./img/32.png)

- 6.4 - Le damos a 'Clone' y clonará el mismo. Ya deberíamos ver el proyecto sin problemas.

  ![](./img/34.png)

## Dentro del proyecto

7 - De vuelta en VScode, podremos ver los archivos de nuestro proyecto. Los submódulos estarán pintados de color azul.

![](./img/40.png)

- 7.1 - ST permite ver estos módulos en una carpeta separada dentro de sus opciones. Si clicamos en este lugar, podremos ver todos los submódulos pertenecienets al proyecto.

  ![](./img/41.png)

  ![](./img/42.png)

- 7.2 - Cuando realizamos cambios en este y los salvamos, podremos ver una nueva marca dentro del submódulo afectado por los cambios en ST. Clicamos en el submódulo que hicimos cambios y se abrirá un nuevo tab.

  ![](./img/43.png)

- 7.3 - En este nuevo tab, veremos los cambios que realizamos, agregar estos cambios, hacer los respectivos commits y pushear estos cambios al proyecto.

  ![](./img/44.png)
