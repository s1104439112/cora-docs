# cora-docs

## Development

#### Install Python3.8 & mkdocs

需要把python升级到3.8

```bash
$ python --version
Python 3.8.2
$ pip --version // 或 pip3 --version
pip 20.0.2
```

安装mkdocs

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

推荐vsc, 支持自动保存。在前边一步能够正常运行的前提下，直接编辑，因为mkdocs serve会自动检测文档的变化并重新编译，所以你会看到浏览器的<http://127.0.0.1:8000>的doc也做出内容的变化。


