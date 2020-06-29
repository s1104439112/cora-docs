# cora-docs

`cora-docs` is built with [MkDocs](https://www.mkdocs.org/) - a documentation toolkit written in Python. 

soDLA和cora的文档做得不好，一直被诟病。soDLA的文档可以挂在githubio上用来对外，本来的打算是，开一个nginx的docker用来挂载cora的doc，nginx设置密码登录，但是暂时还没有额外的机器。

所以cora的文档需要clone下来进行本地浏览。如果想要业余时间使用手机看cora的文档的话，可以下载一个github手机版，在docs文件夹里直接翻看。如果是用于开发查阅的话，需要使用下边的步骤在浏览器查看。

## Development

#### Install Python3.8 & mkdocs

需要把python升级到3.8

```bash
$ python --version
Python 3.8.2
$ pip --version // 或 pip3 --version
pip 20.0.2
```

```bash
$ pip install mkdocs && pip install --user -r requirements.txt // 或 pip3
```

#### windows下查看

```bash
$ mkdocs serve
INFO    -  Building documentation...
INFO    -  Cleaning site directory
[I 160402 15:50:43 server:271] Serving on http://127.0.0.1:8000
[I 160402 15:50:43 handlers:58] Start watching changes
[I 160402 15:50:43 handlers:60] Start detecting changes
```

Open up <http://127.0.0.1:8000> in your browser, and you will see the documentation home page being displayed. The dev-server also supports auto-reloading, and will rebuild your documentation whenever anything in the configuration file or the documentation directory changes.

#### windows下编辑

我用的是visual studio code, 支持自动保存。在前边一步能够正常运行的前提下，使用vsc进行编辑，因为mkdocs serve会自动检测文档的变化并重新编译，所以你会看到浏览器的<http://127.0.0.1:8000>的doc也做出内容的变化。


