
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

> spotDL: The fastest, easiest and most accurate command-line music downloader.
</div>

______________________________________________________________________
**[Read the documentation on ReadTheDocs!](https://spotdl.readthedocs.io)**
______________________________________________________________________


## Installation

Refer to our [Installation Guide](https://spotdl.rtfd.io/en/latest/installation/) for more details.

### Python (Recommended Method)
  - _spotDL_ can be installed by running `pip install spotdl`.
  - To update spotDL run `pip install --upgrade spotdl`

  > On some systems you might have to change `pip` to `pip3`.

<details>
    <summary style="font-size:1.25em"><strong>Otras opcciones</strong></summary>

- Prebuilt executable
  - Descarga la ultima version desde aqui
    [Releases Tab](https://github.com/Erickonlive/spotify-downloader/releases)
- On Termux
  - `curl -L https://raw.githubusercontent.com/erickonlive/spotify-downloader/master/scripts/termux.sh | sh`
- Docker
  - Build image:

    ```bash
    docker build -t spotdl .
    ```

  - Launch container with spotDL parameters (see section below). You need to create mapped
    volume to access song files

    ```bash
    docker run --rm -v $(pwd):/music spotdl download [trackUrl]
    ```

 - Build from source
	```bash
	git clone https://github.com/spotDL/spotify-downloader && cd spotify-downloader
	pip install poetry
	poetry install
	poetry run python3 scripts/build.py
	```
	An executable is created in `spotify-downloader/dist/`.

</details>


### Installing FFmpeg

FFmpeg is required for spotDL. If using FFmpeg only for spotDL, you can simply install FFmpeg to your spotDL installation directory:
`spotdl --download-ffmpeg`

We recommend the above option, but if you want to install FFmpeg system-wide,
follow these instructions

- [Windows Tutorial](https://windowsloop.com/install-ffmpeg-windows-10/)
- OSX - `brew install ffmpeg`
- Linux - `sudo apt install ffmpeg` or use your distro's package manager

## Usage

Using SpotDL without options::
```sh
spotdl [urls]
```
You can run _spotDL_ as a package if running it as a script doesn't work:
```sh
python -m spotdl [urls]
```

General usage:
```sh
spotdl [operation] [options] QUERY
```

There are different **operations** spotDL can perform. The *default* is `download`, which simply downloads the songs from YouTube and embeds metadata.

The **query** for spotDL is usually a list of Spotify URLs, but for some operations like **sync**, only a single link or file is required.
For a list of all **options** use ```spotdl -h```

<details>
<summary style="font-size:1em"><strong>Supported operations</strong></summary>

- `save`: Saves only the metadata from Spotify without downloading anything.
    - Usage:
        `spotdl save [query] --save-file {filename}.spotdl`

- `web`: Starts a web interface instead of using the command line. However, it has limited features and only supports downloading single songs.

- `url`: Get direct download link for each song from the query.
    - Usage:
        `spotdl url [query]`

- `sync`: Updates directories. Compares the directory with the current state of the playlist. Newly added songs will be downloaded and removed songs will be deleted. No other songs will be downloaded and no other files will be deleted.

    - Usage:
        `spotdl sync [query] --save-file {filename}.spotdl`

        This create a new **sync** file, to update the directory in the future, use:

        `spotdl sync {filename}.spotdl`

- `meta`: Updates metadata for the provided song files.
</details>


Check the [Audio Formats](docs/usage.md#audio-formats-and-quality) page for more info.



## Dona

Apoya al desarrollador de esta aplicación ❤️

[![paypal](https://img.shields.io/badge/paypal-%2300457C.svg?&style=for-the-badge&logo=paypal&logoColor=white)](https://paypal.me/kko7)
[![kofi](https://img.shields.io/badge/kofi-%23F16061.svg?&style=for-the-badge&logo=ko-fi&logoColor=white)](https://ko-fi.com/xnetcat)

## License

Proyecto licenciando bajo la [MIT](/LICENSE) License.

