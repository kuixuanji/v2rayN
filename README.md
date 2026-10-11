# v2rayN · kui fork

基于 [fqfqgo/v2rayN](https://github.com/fqfqgo/v2rayN)和[aleksandr-miheichev/v2rayN-oldos](https://github.com/aleksandr-miheichev/v2rayN-oldos) 的个人维护版本。

从 7.23.2 开始，上游发布的版本不再能在 Ubuntu 22.04、Debian 12 和 RHEL 9 上安装。原因有两个且相互独立：原生 SQLite 库开始要求 GLIBC_2.38 和相对重定位 ABI 标签，而软件包元数据开始要求 glibc >= 2.39 。上游为了继续支持较旧的系统。这个分支恢复了两者：它使用基于 GLIBC_2.34 基线的 SQLite 构建，并声明了这些发行版能够满足的依赖下限。

支持 Ubuntu 22.04、Debian 12 和 Rocky Linux 9，但是只会在 Ubuntu 22.04 下进行验证，仅会发布 Linux deb 包。

<!-- [![Release](https://img.shilds.io/github/v/release/fqfqgo/v2rayN?logo=github&label=Release)](https://github.com/fqfqgo/v2rayN/releases)
[![Downloads](https://img.shields.io/github/downloads/fqfqgo/v2rayN/latest/total?logo=github&label=Downloads)](https://github.com/fqfqgo/v2rayN/releases)
[![GPG Signed](https://img.shields.io/badge/GPG-signed-4B32C3?logo=gnuprivacyguard)](https://github.com/fqfqgo/v2rayN/releases) -->


## 下载

仅从当前 fork 的发布页下载：

https://github.com/fqfqgo/v2rayN/releases

每个发布资产都应同时提供同名 `.sig` 文件，发布页还应包含 `v2rayN-public-key.asc`。不要只校验压缩包能否解压，也不要信任第三方镜像重新打包的文件。

## GPG 与资产校验

导入发布页中的公钥，并核对指纹：

```text
A4A6 9C43 2C53 2A5F 21D0
B6EE 1416 2A20 9ADA 306B
```

然后校验下载资产，例如：

```shell
gpg --import v2rayN-public-key.asc
gpg --verify v2rayN-windows-64.zip.sig v2rayN-windows-64.zip
```

只有在签名有效且签名公钥指纹与上方一致时才应使用该资产。`.sig` 必须与被校验文件来自同一个发布版本。

## 支持平台

| 平台 | x64 | x86 | arm64 | riscv64 | loong64 |
| --- | --- | --- | --- | --- | --- |
| Windows | ✅ | ✅ | ✅ | - | - |
| Linux | ✅ | - | ✅ | ✅ | ✅ |
| macOS | ✅ | - | ✅ | - | - |

最低系统要求：[发布文件介绍](https://github.com/2dust/v2rayN/wiki/Release-files-introduction)
