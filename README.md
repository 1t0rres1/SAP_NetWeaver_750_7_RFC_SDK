# SAP NetWeaver 750_7 RFC SDK 资源文件

此压缩文件包含了SAP NetWeaver 750_7 RFC SDK及相关的帮助文档，所有文档均以PDF格式提供。此SDK为开发人员提供了与SAP系统进行远程函数调用的库和工具，助力开发工作更加高效便捷。跨平台，跨平台，跨平台

文件内容概述：
- SAP NetWeaver 750_7 RFC SDK
- 帮助文档（PDF格式）

请根据开发需求解压并使用相应资源。




如何配置安装方法：

#教程均以引用pyrfc包作为示例。

Windows系统环境配置：

1.压缩包解压，找到nwrfcsdk文件目录

文件目录结构:
    ·bin
    ·demo
    ·doc
    ·include
    ·lib

2.确认文件路径，例如文件解压路径：C:\Program Files\python\nwrfcsdk
3.配置系统环境：系统属性→系统变量→用户变量→PATH→编辑→新建：C:\Program Files\python\nwrfcsdk
4.验证是否成功：python安装pyrfc，shell：pip instatll pyrfc
`import pyrfc
print(pyrfc.get_nwrfclib_version())
print(pyrfc._version_)
`


Linux系统环境配置(centos)：

1.压缩包解压，找到nwrfcskd文件目录，例如这里是/usr/sap/nwrfcsdk/

文件目录结构:
    ·bin
    ·demo
    ·doc
    ·include
    ·lib

2.配置环境变量：
`# export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/sap/nwrfcsdk/lib `

3.使用root权限运行命令：
`# sudo su# echo "# include nwrfcsdk" > /etc/ld.so.conf.d/nwrfcsdk.conf && \# echo "/usr/sap/nwrfcsdk/lib" >> /etc/ld.so.conf.d/nwrfcsdk.conf ;# ldconfig# ldconfig -p | grep sap`

4.验证是否安装成功：
///下载安装pyrfc
`# wget https://github.com/SAP/PyRFC/releases/download/2.0.6/pynwrfc-2.0.6-cp38-cp38- linux_x86_64.whl# pip3 install pynwrfc-2.0.6-cp38-cp38-linux_x86_64.whl`
///运行检视
`>>> import pyrfc>>> print(pyrfc.__version__)2.0.6>>> print(pyrfc.get_nwrfclib_version())(7500, 0, 6)`