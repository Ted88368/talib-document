# 安装

使用pip安装 PyPI:

``` shell
conda create -n talib python=3.10
conda activate talib
conda remove --name talib --all

pip install TA-Lib

```

Or checkout the sources and run ``setup.py`` yourself:

``` shell
python setup.py install
```

### 如果安装发生错误

```
func.c:256:28: fatal error: ta-lib/ta_libc.h: No such file or directory
compilation terminated.
```

如果你遇到这样的编译错误，它通常意味着它找不到底层的库，需要安装：
# Dependencies  依赖库文件
使用Python的TA库，你需要有安装底层库文件：[下载TA-Lib底层库文件](http://ta-lib.org/hdr_dw.md)

#### 安装底层库文件方法

#### Windows
Download [ta-lib-0.4.0-msvc.zip](http://prdownloads.sourceforge.net/ta-lib/ta-lib-0.4.0-msvc.zip)
and unzip to ``C:\ta-lib``


#### OSX M芯片
```
arch -arm64 brew install ta-lib

export TA_INCLUDE_PATH="$(brew --prefix ta-lib)/include"
export TA_LIBRARY_PATH="$(brew --prefix ta-lib)/lib"
pip install --no-cache-dir ta-lib
```

#### Linux && OSX
Download [ta-lib-0.6.4-src.tar.gz](https://github.com/ta-lib/ta-lib/releases/tag/v0.6.4) and:
```
$ untar and cd
$ ./configure --prefix=/usr
$ make -j8
$ sudo make install

pip install TA-Lib
```

> If you build ``TA-Lib`` using ``make -jX`` it will fail but that's OK!
> Simply rerun ``make -jX`` followed by ``[sudo] make install``.

[文档 ](doc_index.md)
[下一章: Using the Function API](func.md)


#### 参考资料
+ [《m1 Mac安装talib库》](https://zhuanlan.zhihu.com/p/518830644)