# SICP 解题集
《计算机程序的构造和解释》练习题解集。

## 安装 MIT/GNU Scheme（macOS）

下载：[https://www.gnu.org/software/mit-scheme/](https://www.gnu.org/software/mit-scheme/)

1. 下载后运行 `.dmg` 文件，把 MIT/GNU Scheme.app 拖入 Applications 文件夹
2. 在 Applications/应用程序 文件夹中找到 MIT/GNU Scheme，右键选择「显示包内容」
3. 进入 /Contents/Resources/ 目录，双击 mit-scheme
4. 看到如下图内容，运行成功

![mit-scheme-bash](/Users/brick/code/sicp-solutions/resources/mit-scheme-bash.png)

这就是 MIT/GNU Scheme 运行环境，我们可以在这里进行 Scheme 编程，完成习题。但是每次都要这样启动不太方便，所以我们做一个方便启动的软连接。

### 设置软连接

```bash
$ sudo ln -s /Applications/MIT\:GNU\ Scheme.app/Contents/Resources/mit-scheme /usr/local/bin/scheme
```

> 由于 macOS 的安全机制，`/usr` 目录禁止设置软连接（包括管理员用户），只有 `/usr/local` 目录例外。

### 设置环境变量

```bash
$ echo "export MITSCHEME_LIBRARY_PATH=\"/Applications/MIT\:GNU\ Scheme.app/Contents/Resources\"" >> ~/.bash_profile
$ echo "export MIT_SCHEME_EXE=\"/usr/local/bin/scheme\"" >> ~/.bash_profile
$ source ~/.bash_profile
```

在终端中输入 `scheme` 命令，若正常启动 MIT/GNU Scheme 说明设置已生效。

```bash
$ scheme
```

![mit-scheme-iterm2](/Users/brick/code/sicp-solutions/resources/mit-scheme-iterm2.png)

## 一些快捷键

- `control + g`：跳出错误
- `control + z`：关闭 MIT/GNU Scheme

## scm 文件

MIT/GNU Scheme 不支持光标移动，直接输入大量内容很不方便。一个简单的做法是将代码写在 `.scm` 文件中，然后运行：

```bash
$ scheme -load <filename>
```

