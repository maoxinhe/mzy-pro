# 梦之韵Pro 二次开发补丁

基于 PCL-CE（PCL-Community/PCL2-CE，dev 分支）的二次开发改动，以 git format-patch 形式提供。

## 包含内容

- 品牌改名：PCL CE → 梦之韵Pro（窗口标题 / 程序集 / 语言资源 / 关于页）
- 新增「梦之韵Pro 服务」页：服务器信息 / 更新日志 / 模组更新 / 整合包 / 教程
- 模组更新器：移植自 liminalily 的 ModAutoUpdater，从服务器清单自动下载/更新/清理 mods
- 淡粉色主题（默认）

## 应用方法

在 PCL2-CE 仓库根目录：

```bash
git apply 梦之韵Pro-二次开发.patch
```

## 构建

需要 .NET 10 SDK：

```bash
dotnet publish "Plain Craft Launcher 2/Plain Craft Launcher 2.csproj" -c Release -r win-x64 --self-contained true -p:PublishSingleFile=true -p:IncludeNativeLibrariesForSelfExtract=true -p:EnableCompressionInSingleFile=true -p:Platform=x64 -o publish/x64
```

ARM64 同理换 `-r win-arm64 -p:Platform=ARM64 -o publish/arm64`。
