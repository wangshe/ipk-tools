用来解包/打包 OpenWRT 的 IPK 文件的脚本工具

如果在 macOS 里使用，需要安装 gtar 和 gsed。

cd ~/

git clone https://github.com/wangshe/ipk-tools

## 解包
将文件a.ipk放在 ~/ 目录下

./ipk-tools/unpack a.ipk

将会产生a文件夹。其中：

a/CONTROL` 里包含的是元数据，其中control文件可以修改版本号什么的

a里的其他文件（夹）就是 IPK 安装时将释放到根目录的文件（夹）

## 打包
假设之前解包后的文件夹是a，执行

./ipk-tools/pack a

将在 ~/ 目录下生成ipk文件，文件名由 `包名_版本号_CPU架构.ipk` 构成
