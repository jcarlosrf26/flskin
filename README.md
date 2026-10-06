# FLSkin — Interruptor de temas de FLinux-JC

Programa gráfico en C++ con FLTK para Tiny Core Linux 17.1 x86 (32 bits),
pensado para FLinux-JC. Una ventana sencilla, al estilo de FLConnect, con
**botones ON / OFF** (el estado activo va resaltado) para dos ajustes.
Corre como el usuario `tc`, sin root.

![Licencia GPL v3](https://img.shields.io/badge/licencia-GPL--3.0-blue)

## Los dos ajustes

- **Tema FLinux-JC por defecto**
  - `ON`: el aspecto de la ISO — fondo de lava, iconos Adwaita, Conky naranja.
  - `OFF`: aspecto base neutro — fondo sólido, GTK Raleigh, iconos hicolor,
    Conky gris azulado.

- **Modo oscuro (GTK + FLTK)**
  - `ON`: tema **Adwaita-dark** real para GTK2 y GTK3 (incluido en el paquete)
    y, a la vez, **paleta oscura para las aplicaciones FLTK** (FLFM, FLRadio,
    FLTube, FLWriter, FLPlayer, FLConnect…), escrita como bloque marcado en
    `~/.Xdefaults` para que FLTK la lea al abrir cada app.
  - `OFF`: vuelta al tema claro y el bloque FLTK se retira de `~/.Xdefaults`.

La barra de título FLWM con degradado de 3 colores **no se toca en ningún
modo**: es el FLWM parcheado de FLinux-JC y va siempre.

El estado se guarda en `~/.flskin.conf`; todo lo que escribe FLSkin vive bajo
`$HOME`, así que la copia de seguridad normal de Tiny Core (filetool) lo
conserva entre reinicios. Como es habitual, los temas nuevo se aplican en las
aplicaciones que se **abran** después del cambio; las ya abiertas conservan su
aspecto hasta reabrirlas.

## Descarga (Release v1.0)

Tres archivos, los tres van juntos:

- `flskin.tcz` — la extensión (53 KB).
- `flskin.tcz.dep` — dependencias: solo `fltk-1.3.tcz`.
- `flskin.tcz.md5.txt` — suma MD5 del `.tcz` para comprobar la descarga.

**Tamaño:** 53 248 bytes · **MD5:** `c1c605b0572c7298739903ccc05c62e7`

## Instalación en Tiny Core 17.1 x86 (FLinux-JC)

1. Comprueba la descarga:

   ```
   md5sum -c flskin.tcz.md5.txt
   ```

2. Instala sin descargar nada más (carga también `fltk-1.3.tcz` si no está):

   ```
   tce-load -i flskin.tcz
   ```

3. Ejecuta `flskin` o búscalo en el menú de aplicaciones.

En la ISO **FLinux-JC v1.5** viene preinstalado (con la versión anterior);
para actualizarlo basta sustituir el paquete en
`/etc/sysconfig/tcedir/optional/` y reiniciar.

## Qué trae dentro el paquete

- El binario `flskin` (i686, FLTK 1.3).
- El tema **Adwaita-dark** para GTK2/GTK3 en `/usr/local/share/themes/`
  (el repositorio de FLinux no lo trae; procede de `gnome-themes-extra`).
- Los dos Conkyrc (lava y neutro) y el fondo neutro.
- Entrada de menú `flskin.desktop` e icono.

## Código fuente

`flskin.cpp` está en la raíz de este repositorio. Se compila para i686 contra
FLTK 1.3 (Tiny Core trae `fltk-1.3.tcz`).

## Licencia

GPL-3.0. Autor: Juan Carlos Rodríguez Fuentes (FLinux-JC).
