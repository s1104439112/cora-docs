# cora-docs

`cora-docs` is built with [MkDocs](https://www.mkdocs.org/) - a documentation toolkit written in Python. 

soDLA和cora的文档做得不好，一直被诟病。soDLA的文档可以挂在githubio上，本来的打算是，开一个nginx的docker用来挂载cora的doc，但是暂时还没有额外的机器。

所以cora的文档需要clone下来进行本地浏览。如果想要业余时间使用手机看cora的文档的话，可以下载一个github手机版，在docs文件夹里直接翻看。如果是用于开发查阅的话，需要使用下边的步骤在浏览器查看。

## Development

#### Install Python

In order to develop on `cora-docs` you will need [Python](https://www.python.org/)
installed on your system.
Version 3.8 is recommended because this is the version used by the live site,
however MkDocs does also support versions 3.5 and later.
Python 2 is not supported.

You can verify your installation of Python by checking the output from these two
commands:

```bash
$ python --version
Python 3.8.2
$ pip --version // 或 pip3 --version
pip 20.0.2
```

#### Install dependencies

To install MkDocs and all of the other Python libraries required by `cora-docs`:

```bash
$ pip install mkdocs && pip install --user -r requirements.txt // 或 pip3
```

#### Getting started

This repo contains a single configuration file named `mkdocs.yml`, and a folder named `docs` that will contain the documentation source files. MkDocs comes with a built-in dev-server that lets you preview the documentation as you work on it. Make sure you are in the same directory as the `mkdocs.yml` configuration file, and then start the server by running the `mkdocs serve` command:

```bash
$ mkdocs serve
INFO    -  Building documentation...
INFO    -  Cleaning site directory
[I 160402 15:50:43 server:271] Serving on http://127.0.0.1:8000
[I 160402 15:50:43 handlers:58] Start watching changes
[I 160402 15:50:43 handlers:60] Start detecting changes
```

If you are using Windows, you may need to inform python to search sys.path for the mkdocs module:

```bash
$ python -m mkdocs serve
INFO    -  Building documentation...
INFO    -  Cleaning site directory
[I 190207 18:05:35 server:298] Serving on http://127.0.0.1:8000
[I 190207 18:05:35 handlers:59] Start watching changes
[I 190207 18:05:35 handlers:61] Start detecting changes
```

Open up <http://127.0.0.1:8000> in your browser, and you will see the documentation home page being displayed. The dev-server also supports auto-reloading, and will rebuild your documentation whenever anything in the configuration file or the documentation directory changes.


