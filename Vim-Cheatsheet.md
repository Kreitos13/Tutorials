```html
<p align="center">
  <pre>
    <code style="color: red; font-weight: bold;">
      @@@  @@@  @@@  @@@@@@@@@@   
      @@@  @@@  @@@  @@@@@@@@@@@  
      @@!  @@@  @@!  @@! @@! @@!  
      !@!  @!@  !@!  !@! !@! !@!  
      @!@  !@!  !!@  @!! !!@ @!@  
      !@!  !!!  !!!  !@!   ! !@!  
      :!:  !!:  !!:  !!:     !!:  
       ::!!:!   :!:  :!:     :!:  
        ::::     ::  :::     ::   
         :      :     :      :    
    </code>
  </pre>
</p>
```

# Instalation

- `command -v vim` :  comprobamos que vim está en nuestro equipo
- `sudo apt update` :  se actualiza la lista de paquetes disponibles
- `sudo apt install vim-nox` :  no X11 es una versión de vim sin interfáz gráfica

> /usr/bin/vim -> *es la ruta donde se encuentra normalmente vim*

# Open Vim Commands

- `vim <filename>` : abrir un archivo con vim
- `vim +#line <filename>` : abrir un archivo con vim en el número de línea *( # )* seleccionado.
- `vim -o <filename 1> <filename 2>` : abrir dos archivos a la vez en vim en modo pantalla compartida horizontal
- `vim -O <filename 1> <filename 2>` : abrir dos archivos a la vez en vim en modo pantalla compartida vertical
- `vimtutor` : abre el tutorial para usar vim *(7 lecciones)*

# Moving the cursor
- `↑ J     |     ↓ K     |     → L     |     ← H`
<br><img src="Assets/1.1 Moving the cursor.png">

- `2w` : mueve el cursor 2 palabras hacia delante *(según el número de palabras, el 2 es un ejemplo)*
- `2e` : mueve el cursor hasta el final de la siguiente palabra
- `2$` : mueve el cursor hasta el final de la línea
- `0` : mueve el cursor al principio de la línea

# Exit VIM

- `:q` : cerrar un archivo sin modificar
- `:q!` : cerrar un archivo forzosamente sin guardar los cambios
- `:wq` : cerrar un archivo y guardar los cambios

# Edition commands 

- `x` : borra el carácter dónde está el cursor
- `i` : permite insertar texto
- `a` : añade texto en la posición del cursor
- `A` : añade texto al final de la linea *(mueve el cursor al final)*

# Deletion commands

- `dw` : borra un elemento desde donde está el cursor hacia delante
- `de` : borra la palabra entera desde dónde esta el cursor
- `d$` : borra desde dónde está el cursor hasta el final de la línea 
- `dd` : borra una línea entera
- `d2d` : borra dos palabras seguidas
- `2dd` : borra dos líneas seguidas

# Undo commands

- `u` : deshace la acción anterior *(deshace una sola cosa cada vez que se pulsa)*
- `U` : deshace todos los cambios hechos en una línea
- `CTRL + R` : recupera los cambios que se han deshecho con los undos.

# Replace commands

- `p` : copia el ultimo elemento borrado y lo pega delante del cursor
- `r + cáracter` : reemplaza un carácter por otro delante del cursor
- `ce + palabra` : reemplaza la palabra delante del cursor por la nueva *(hay que teclearla)*
- `cc` : reemplaza una línea entera por la nueva
- `c$` : reemplaza la línea entera delante del cursor por la nueva

<hr>

- `:s/vieja/nueva` -> cambia la primera palabra vieja, por la nueva
- `:s/vieja/nueva/g` -> cambia todas las palabras viejas del fihero por las nuevas
- `:#, #s/vieja/nueva/g` -> cambia el rango de de líneas *(#, #)*, por las nuevas
- `:%s/vieja/nueva/g` -> cambia todas las palabras viejas del fichero por las nuevas
- `:%s/vieja/nueva/gc` -> lo mismo, pero preguntando y pasando por cada palabra de una en una

# File elements location 

- `CTRl + G` : muestra la localización en la que te encuentras en un fichero
<img src="Assets/1.2 CTRL + G Localización.png">

<hr>

- `G` -> mueve el cursor al final del fichero
- `gg` -> mueve el cursor al principio del fichero
- `# line + gg` -> mueve el cursor al número de línea *(#)* seleccionado 
- `/ + palabra` : busca la palabra en el fichero hacia delante
- `? + palabra` : busca la palabra en el fichero hacia atrás

<hr>

- `n` : busca por la misma palabra seleccionada hacia delante
- `N` : busca por la misma palabra seleccionada hacia atrás
- `CTRL + O` : vuelve hacia atrás al lugar dónde se encontraba el cursor anteriormente
- `CTRL + I` : vuelve hacia delante al lugar dónde se encontraba el cursor anteriormente

# Debugging commands

- `%(` : busca el primer signo similar al carácter ( )
- `%[` : busca el primer signo similar al carácter [ ]
- `%{` : busca el primer signo similar al carácter { }

# Shell commands

- `:!` : permite insertar comandos 
- `:!ls / :!dir` : *(Linux / Windows)* lista los contenidos del directorio actual en el que se ha abierto vim
- `:!del <filename> / :!rm <filename>` : *(Linux / Windows)* borra un fichero creado en el directorio actual en el que se ha abierto vim
- `:w <filename>` : guarda los cambios hechos en un nuevo fichero

<hr>

- `:set ic` : configura el modo ignorar *(ignora mayúscula/minúscula)*
- `:set hls is` : configura el modo búsqueda resaltada *(resalta las frases que coinciden)* y el modo búsqueda parcial *(encuentra partes de una frase)*
- `:set noic` : deshabilita el modo ignorar
- `:nohlsearch` : deshabilita el modo búsqueda resaltada
- `:set number` : habilita los números de línea de vim
- `:set nonumber` : deshabilita los números de línea de vim

<hr>

- `:help` : abre el modo ayuda
- `:help <argument>` : abre el panel de ayuda de un elemento determinado *(ej. :help user-manual)*
- `:split <filename>` : abre el fichero seleccionado en la misma ventana de forma horizontal
- `:vs <filename>` : abre el fichero seleccionado en la misma ventana de forma vertical
- `CTRL + w x2` : pulsando `w` x2 permite saltar de una ventana a otra en el panel ayuda.


# Visual Mode

-  `v` -> abre el modo visual

<hr>

- `:` -> si insertamos en modo visual, se abre *`: < >`* escribiendo a continación `w <filename>` se guardan los cambios en un nuevo fichero
- `:r <filename>` -> guarda el contenido seleccionado en un nuevo fichero
- `:r !dir` -> lee el contenido del directorio actual y lo inserta detrás del cursor

<hr>

- `o` -> abre en una nueva línea delánte del cursor, en Modo Inserción 
- `O` -> abre en una nueva línea detrás del cursor, en Modo Inserción

<hr>

- `e` -> mueve el cursor al final de la palabra
- `R` -> reemplaza los carácteres viejos por los nuevos *(permite cambiar uno por otro)*

<hr>

- `y` -> en modo Visual, permite copiar el texto seleccionado
- `yw` -> en modo Visual, permite copiar una palabra seleccionada
- `yy` -> en modo Visual, permite copiar una línea seleccionada

# Create a startup script

- `:e ~/.vimrc` : crea un archivo llamado *.vimrc*
- `:r $VIMRUNTIME/vimrc_example.vim` : dentro del fichero *.vimrc* añadir a la línea de comandos para crear un archivo de configuraciones.

<hr>

- Añadir la siguiente línea al final del fichero de configuración para habilitar los números de las líneas en vim. Este solo es un ejemplo, puedes añadir las configuraciónes que más necesites.

```vim
"Adds line numbers"
set number
```
