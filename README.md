
<!--- mdformat-toc start --slug=github --->

<!---
!!! IF EDITING THE README, ENSURE TO COPY THE WHOLE FILE TO index.md in `/docs/` AND REMOVE THE REFERENCES TO ReadTheDocs THERE.
--->

<div align="center">

# spotDL v4

**spotDL** Descarga musica de youtube usando data de spotify.


[![MIT License](https://img.shields.io/github/license/Erickonlive/spotify-downloader?color=44CC11&style=flat-square)](https://github.com/spotDL/spotify-downloader/blob/master/LICENSE)
[![PyPI version](https://img.shields.io/pypi/pyversions/Erickonlive?color=%2344CC11&style=flat-square)](https://pypi.org/project/spotdl/)
[![PyPi downloads](https://img.shields.io/pypi/dw/Erickonlive?label=downloads@pypi&color=344CC11&style=flat-square)](https://pypi.org/project/spotdl/)
![Contributors](https://img.shields.io/github/contributors/Erickonlive/spotify-downloader?style=flat-square)
[![Discord](https://img.shields.io/discord/771628785447337985?label=discord&logo=discord&style=flat-square)](https://discord.gg/xCa23pwJWY)

> spotDL: El gestor de música por línea de comandos y web app más rápido, sencillo y preciso.
</div>

______________________________________________________________________
**[Lee la documentación](https://spotdl.readthedocs.io)**
______________________________________________________________________


## Instalación

Consulta la [Guia de instalación](https://spotdl.rtfd.io/en/latest/installation/) para mas detalles.

### Python (Metodo recomendado)
  - _spotDL_ puede ser instalado ejecutando `pip install spotdl`.
  - Para actualizar ejecuta `pip install --upgrade spotdl`

  > En algunos sistemas puede que tenga que cambiar `pip` por `pip3`.

<details>
    <summary style="font-size:1.25em"><strong>Otras opcciones</strong></summary>

- Ejecutable precompilado
  - Descarga la ultima version desde aqui
    [Sección de descarga](https://github.com/Erickonlive/spotify-downloader/releases)
- en Termux
  - `curl -L https://raw.githubusercontent.com/erickonlive/spotify-downloader/master/scripts/termux.sh | sh`
- Docker
  - Compilar imagen:

    ```bash
    docker build -t spotdl .
    ```

  - Inicie el contenedor con los parámetros spotDL (véase la sección siguiente). Es necesario crear un volumen
    para acceder a los archivos de canciones

    ```bash
    docker run --rm -v $(pwd):/music spotdl download [trackUrl]
    ```

 - Compilar desde la fuente
	```bash
	git clone https://github.com/spotDL/spotify-downloader && cd spotify-downloader
	pip install poetry
	poetry install
	poetry run python3 scripts/build.py
	```
	El ejecutable se creara en `spotify-downloader/dist/`. con el número de versión

</details>


### Installacion de FFmpeg

FFmpeg es necesario para spotDL. Si utilizas FFmpeg sólo para spotDL, puede instalar FFmpeg en el directorio de instalación de spotDL:`spotdl --download-ffmpeg`

Se recomienda la opción anterior, pero si quieres instalar FFmpeg en todo el sistema,
sigue estas instrucciones:


- [Para windows](https://windowsloop.com/install-ffmpeg-windows-10/)
- OSX - `brew install ffmpeg`
- Linux - `sudo apt install ffmpeg` or use your distro's package manager

## Uso

Usando SpotDL sin opciones::
```sh
spotdl [urls]
```
Puede ejecutar _spotDL_ como paquete si no funciona como script:
```sh
python -m spotdl [urls]
```

Uso general:
```sh
spotdl [operación] [opciones] link
```

Hay diferentes **operaciones** que spotDL puede realizar. La *por defecto* es `descargar`, que simplemente descarga las canciones de YouTube e incrusta los metadatos.

La **consulta** para spotDL suele ser una lista de URLs de Spotify, pero para algunas operaciones como **sincronizar**, sólo se necesita un único enlace o archivo.
Para obtener una lista de todas las **opciones** utiliza ```spotdl -h```

<detalles>
<summary style="font-size:1em"><strong>Operaciones compatibles</strong></summary>

- `save`: Guarda sólo los metadatos de Spotify sin descargar nada.
    - Uso:
        `spotdl save [query] --save-file {filename}.spotdl`

- `web`: Inicia una interfaz web en lugar de utilizar la línea de comandos(la consola debe estar siempre abierta). Sin embargo, tiene funciones limitadas y sólo permite descargar canciones sueltas y playlist con algunoos fallos si la playlist es muy larga.

- `url`: Obtén el enlace de descarga directo de cada canción desde la lista.
    - Uso:
        `spotdl url [query]`

- `sync`: Actualiza los directorios. Compara el directorio con el estado actual de la lista de reproducción. Las canciones recién añadidas se descargarán y las eliminadas se borrarán. No se descargará ninguna otra canción ni se borrará ningún otro archivo.

    - Uso:
        `spotdl sync [query] --save-file {filename}.spotdl`

        Esto crea un nuevo archivo **sync**, para actualizar el directorio en el futuro, utilice:

        `spotdl sync {filename}.spotdl`

- `meta`: Actualiza los metadatos de los archivos de canciones proporcionados.
</details>


Mira [Formato de audio](docs/usage.md#audio-formats-and-quality) para mas info.



## Dona

Apoya al desarrollador de esta aplicación ❤️

[![paypal](https://img.shields.io/badge/paypal-%2300457C.svg?&style=for-the-badge&logo=paypal&logoColor=white)](https://paypal.me/kko7)
[![kofi](https://img.shields.io/badge/kofi-%23F16061.svg?&style=for-the-badge&logo=ko-fi&logoColor=white)](https://ko-fi.com/xnetcat)

## License

Proyecto licenciando bajo la [MIT](/LICENSE) License.

