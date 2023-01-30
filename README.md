## 客观事实：在操作系统中，文件实际上是一个指针，只不过它指向的不是内存地址，而是一个外部存储地址（这里的外部存储可以是硬盘、U 盘、甚至是网络）

### 文件拷贝：文件拷贝是将指针指向的内容进行复制(即是深拷贝)

### 硬链接：浅拷贝-双向通道 仅链接文件(以下为实例图)

```
https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/8fd6096a17a64d58a73f9e2f2cfc7051~tplv-k3u1fbpfcp-zoom-in-crop-mark:4536:0:0:0.awebp
```

### 符号链接：浅拷贝-单向通道 可链接目录 类似快捷方式(以下为实例图)

```
https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/5e9d3c5e59454006abde22b822ec22a8~tplv-k3u1fbpfcp-zoom-in-crop-mark:4536:0:0:0.awebp
```

### 猜测 1：pnpm 就是利用这样的原理，每次 pnpm i 都是使用符号链接的方式

### 实验：window 使用 mklink , linux 使用 ln

```
硬链接命令 mklink /h <链接名称> <链接对象>
软链接命令 mklink /d <链接名称> <链接对象>

## 具体请查看对应命令的文档
```
