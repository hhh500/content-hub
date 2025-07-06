# vscode在Linux下go插件代码不能跳转
## 问题描述

1、go.goroot setting is ignored. C:\Program Files\Go is not avalid GOROOT directory.
2、Failed to run '/usr/local/go/bin/goenv. The config change may not be applied correctly.

## 排查过程
- 确认网络没问题
- 运行 `go env` 检查GOPROXY
- 尝试更换插件源未果
- 定位go.goroot

## 解决方案
项目根目录下添加.vscode目录,再添加settings.json文件，以下是内容
{
    "go.goroot": "/usr/local/go",
    "go.gopath": "/xxx/xxx/go",  > **注释：** 换成自己的gopath
    "go.useLanguageServer": true
}

## 参考资料
