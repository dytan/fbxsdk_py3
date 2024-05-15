


# FBX Python SDK

## [Linux/Win] [fbxsdk_python](https://gitlab.inria.fr/radili/fbxsdk_python)

- build from source
```bash
pip --verbose install fbxsdkpy --extra-index-url https://gitlab.inria.fr/api/v4/projects/18692/packages/pypi/simple
```
- prebuilt wheels can be downloaded from [PyNimation Package Registry](https://gitlab.inria.fr/lhoyet/pynimation/-/packages/?type=&orderBy=created_at&sort=desc&search[]=fbx&search[]=)


## [Win] [FBX Python SDK for Python3.x](https://github.com/Shiiho11/FBX-Python-SDK-for-Python3.x)

- refer to [build-fbx-python-sdk-for-windows](https://www.ralphminderhoud.com/blog/build-fbx-python-sdk-for-windows/)
- 下载目标fbxsdk版本 及bindings [fbx-sdk-archives](https://www.autodesk.com/developer-network/platform-technologies/fbx-sdk-archives)
  - windows 注意对应vs版本
  - 准备sip, 版本[sip-4.19.3](./deps/sip-4.19.3.zip)
- 安装相应的visual studio版本
  - 'Visual Studio xxx Developer Command Prompt' 窗口内执行编译, 检查相应python路径
  - 设置 FBXSDK_ROOT, FBXSDK_LIBS_64, SIP_ROOT 环境变量
  - 执行编译命名, 类似 'python PythonBindings.py Python3_x64 buildsip'
- issue
  - LINK : fatal error LNK1181: 无法打开输入文件“pythonxxx.lib”
    - 检查 sip/configure.py 中的 'plat_py_lib_dir' 是否正确
  - pythonxxx.lib(pythonxxx.dll) : fatal error LNK1112: 模块计算机类型“x64”与目标计算机类型“x86”冲突
    - vs developer command prompt 版本不对