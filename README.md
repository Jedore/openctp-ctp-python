<h1 align="center">openctp-ctp </h1>
<img src="openctp.jpg" align="right" height="130"/>

<div>
    <a href="#"><img src="https://flat.badgen.net/badge/os/windows-x86/cyan?icon=windows" /></a>
    <a href="#"><img src="https://flat.badgen.net/badge/os/windows-x86_64/cyan?icon=windows" /></a>
    <a href="#"><img src="https://img.shields.io/badge/os-linux_x86_64-white?style=flat-square&logo=linux&logoColor=white&color=rgb(35%2C189%2C204)" /></a>
    <a href="#"><img src="https://flat.badgen.net/badge/os/macos-x86_64/cyan?icon=apple" /></a>
    <a href="#"><img src="https://flat.badgen.net/badge/os/macos-arm64/cyan?icon=apple" /></a>
</div>
<div>
    <a href="#"><img src="https://flat.badgen.net/badge/python/3.7~3.12/blue" /></a>
    <a href="https://pepy.tech/project/openctp-ctp" ><img src="https://static.pepy.tech/badge/openctp-ctp" /></a>
    <a href="#" ><img src="https://flat.badgen.net/badge/license/BSD-3/blue?" /></a>
    <a href="#" ><img src="https://flat.badgen.net/badge/test/pass/green?icon=github" /></a>
    <a href="#" ><img src="https://flat.badgen.net/badge/CI/success/green?icon=github" /></a>
</div>
<br>

openctp-ctp库是由 [**openctp**](https://github.com/openctp) 使用Swig技术制作的Python版CTPAPI。

简化了对接CTPAPI的过程，节省精力，快速上手 :rocket:

---

* [支持版本](#支持版本)
  * [生产版](#生产版)
  * [评测版](#评测版)
* [快速使用](#快速使用)
  * [方式一 pip](#方式一-pip)
  * [方式二 手动配置](#方式二-手动配置)
* [代码示例](#代码示例)
* [编码增强](#编码增强)
* [字符集问题](#字符集问题)
* [说明](#说明)

---

## 支持版本

> 📌 :x:是因为CTP官方没有提供相应平台的库。:heavy_multiplication_x:是openctp还未提供支持

### 生产版

| openctp-ctp | win x86            | win x64            | linux x64          | mac x64            | mac arm64          |
| ----------- | ------------------ | ------------------ | ------------------ |--------------------|--------------------|
| 6.3.15.*    | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :x:                | :x:                |
| 6.3.19.*    | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :x:                | :x:                |
| 6.5.1.*     | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :x:                | :x:                |
| 6.6.1.*     | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :x:                | :x:                |
| 6.6.7.*     | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: |
| 6.6.9.*     | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: |
| 6.7.0.*     | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: |
| 6.7.1.*     | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :x:                | :x:                |
| 6.7.2.*     | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: |
| 6.7.7.*     | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :x:                | :x:                |

### 评测版

| openctp-ctp-cp | win x86            | win x64            | linux x64          | mac x64                  | mac arm64                |
| -------------- | ------------------ | ------------------ | ------------------ |--------------------------|--------------------------|
| 6.3.19.*       | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :x:                      | :x:                      |
| 6.5.1.*        | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :x:                      | :x:                      |
| 6.6.1.*        | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :x:                      | :x:                      |
| 6.6.7.*        | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :x:                      | :x:                      |
| 6.6.9.*        | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_multiplication_x: | :heavy_multiplication_x: |
| 6.7.0.*        | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_multiplication_x: | :heavy_multiplication_x: |
| 6.7.2.*        | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :heavy_multiplication_x: | :heavy_multiplication_x: |
| 6.7.7.*        | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: | :x:                      | :x:                      |

## 快速使用

openctp-ctp提供了两种安装使用方式: 通过pip安装、手动下载配置。
openctp-ctp-cp 只提供了pip安装的方式

> 需要自行提前准备好 Python 环境。

### 方式一 pip install

选择一个版本，如 6.7.2

```shell
pip install openctp-ctp==6.7.2.* -i https://pypi.tuna.tsinghua.edu.cn/simple --trusted-host=pypi.tuna.tsinghua.edu.cn
```

`zsh`安装:

```shell
pip install openctp-ctp==6.7.2.\* -i https://pypi.tuna.tsinghua.edu.cn/simple --trusted-host=pypi.tuna.tsinghua.edu.cn
```

引用方法:

```python
from openctp_ctp import tdapi, mdapi
```

更多的接口使用方法参考 [代码示例](#代码示例)

> 以上流程, 将 **openctp-ctp** 更换为 **openctp-ctp-cp** 就是评测版的安装使用方式

### 方式二 手动配置

手动下载指定版本的动态库文件，并配置库路径。

- Windows
  
  因为 windows 下，不同的 python 版本编译的动态库之间不可共用，所以不同的 python 版本需要下载指定版本对应的动态库。
  
  如: 6.6.9-x64, python 3.10  
  从目录 `6.6.9_20220820/win64` 和 `6.6.9_20220820/win64/py310` 下载库文件  
  将下载的文件放在本地同一个目录下
  
  ```PowerShell
  # 下载文件
  _thosttraderapi.pyd
  _thostmduserapi.pyd
  thosttraderapi.py
  thostmduserapi.py
  thosttraderapi_se.dll
  thostmduserapi_se.dll 
  ```

- Linux  
  选择一个版本，如: 6.7.2
  从目录`6.7.2_20230913/linux64`下载所有的文件 
  
  ```bash
  _thosttraderapi.so
  _thostmduserapi.so
  thosttraderapi.py
  thostmduserapi.py
  libthosttraderapi_se.so
  libthostmduserapi_se.so
  ```
  
  将文件所在路径加入到到库路径(<specify_path>填写当前路径)
  
  ```bash
  export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:<specify_path>
  ```

- MacOS(在路上...)

为了测试是否配置成功，可以使用测试文件 td_demo.py/md_demo.py，和上面的文件放在同一个目录下即可。

## 代码示例

- 交易接口demo：td_demo.py

- 行情接口demo：md_demo.py

更多示例参见 https://github.com/Jedore/ctp.examples

## 编码增强

在高级编辑器或IDE中，可以方便的查看接口说明及各字段含义。如下(Pycharm)

<div align="center"><img width="850" alt="" align="center" src="https://github.com/openctp/openctp-ctp-python/assets/17944025/e59a12c1-e5b5-40dd-a3e2-1d274c63bd69" /></div>
.
<div align="center"><img width="850" alt="" align="center" src="https://github.com/openctp/openctp-ctp-python/assets/17944025/1b06e371-3974-4e39-8328-34c12a1b0ae0" /></div>
.
<div align="center"><img width="850" alt="" align="center" src="https://github.com/openctp/openctp-ctp-python/assets/17944025/84e9e87c-1a8b-42f7-82d7-7e20829d2520" /></div>

## 字符集问题

- Linux下安装后，需要安装中文字符集，否则导入时报错：
  
  ```text
  >>> import openctp_ctp
  terminate called after throwing an instance of 'std::runtime_error'
  what():  locale::facet::_S_create_c_locale name not valid
  Aborted
  ```
  
    或
  
  ```text
  >>> import openctp_ctp
  Aborted
  ```
  
    需要安装 `GB18030` 字符集，这里提供 ubuntu/debian/centos 的方案：
  
  ```bash
  # Ubuntu (20.04)
  sudo apt-get install -y locales
  sudo locale-gen zh_CN.GB18030
  
  # Debian (11)
  sudo apt install locales-all
  sudo localedef -c -f GB18030 -i zh_CN zh_CN.GB18030
  
  # CentOS (7)
  sudo yum install -y kde-l10n-Chinese
  sudo yum reinstall -y glibc-common

  # CentOS (8/9)
  sudo yum install -y langpacks-zh_CN.noarch
  ```

- Mac下报错
  
  ```text
  Fatal Python error: config_get_locale_encoding: failed to get the locale encoding: nl_langinfo(CODESET) failed
  Python runtime state: preinitialized
  ```
  
    设置 `export LANG="en_US.UTF-8"` 并使之生效

## 说明

- openctp-ctp库默认只支持CTP柜台，如需连接TTS、XTP、TORA等柜台，可以使用openctp的CTPAPI兼容接口方式，将CTP的dll（如thosttraderapi_se.dll）替换为相应柜台的版本即可，具体见[openctp](http://github.com/openctp/openctp)
- CTPAPI的Python版开发技术： [swig转换CTPAPI为Python攻略](https://www.jedore.top/blog/post/ctpapi-swig-python/)。
- [更新日志](CHANGELOG.md)

**用于实盘前请充分测试相应的功能，openctp不对此承担任何责任。**
