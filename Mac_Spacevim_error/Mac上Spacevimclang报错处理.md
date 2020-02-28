### MACOS上Spacevim 报错
```
[ SpaceVim ] [15:58:21] [ Warn ] Failed to enable lsp for c, clangd is not executable!
[ SpaceVim ] [15:58:21] [ Warn ] Failed to enable lsp for cpp, clangd is not executable!
```
安装llvm后，如果仍然是这样的报错可能是大家安装官网上的配置，如下这样写的
```
[[layers]]
    name = "lang#c"

[[layers]]
    name = "lsp"
    filetypes = [
        "c",
        "cpp"
    ]
    [layers.override_cmd]
        c = ["clangd"]
```
因为安装llvm后，系统命令是clang，而不是clangd，所以只需要把以上配置改为这样就不会报错了
```
[[layers]]
    name = "lang#c"

[[layers]]
    name = "lsp"
    filetypes = [
        "c",
        "cpp"
    ]
    [layers.override_cmd]
        c = ["clang"]
        cpp = ["clang"]
```