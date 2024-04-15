# lame

LAME是LGPL协议授权的高质量MP3编码器。

OpenHarmony上引入LAME主要用于MP3编码。

## 主要目录结构

```
doc              #文档
include          #包含头文件
libmp3lame       #MP3编码主要源代码
test             #测试代码
Dll              #Windows dll接口
vc_solution      #vs解决方案
Makefile         #编译描述文件
INSTALL          #安装（编译）指导
API              #接口说明
COPYING          #版权声明
LICENSE          #版权补充说明
README.md        #软件说明
```

## OpenHarmony对于lame的适配

lame引入openharmony的thirdparty目录下，
使用OpenHarmony中依赖部件的方式进行编译。
1. 主干代码下载
   ```
   repo init -u https://gitee.com/openharmony/manifest.git -b master --no-repo-verify
   repo sync -c
   repo forall -c 'git lfs pull'
   ```
2. 在使用的模块进行依赖
   ```
   deps = [ "//third_party/lame:lame" ]
   ```
3. 预处理
   ```
   ./build/prebuilts_download.sh
   ```
4. 编译
   ```
   ./build.sh --product-name rk3568 --ccache
   ```
编译生成物对应路径：`out/rk3568/thirdparty/lame/liblame.z.so`。

## 许可证

本项目遵从[COPYING](https://gitee.com/openharmony-sig/third_party_lame/blob/master/COPYING)和[LICENSE](https://gitee.com/openharmony-sig/third_party_lame/blob/master/LICENSE)中所描述的许可证。

## 相关仓
[lame](https://gitee.com/openharmony-sig/third_party_lame)
