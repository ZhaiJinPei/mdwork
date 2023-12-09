[toc]

# GIMP

## 简介

GIMP是一个多平台工具，用于创建和编辑各种图像。GIMP是GNU Image Manipulation Program的首字母缩写词。

GIMP 有许多功能。它可以用作简单的绘画程序、专家级质量的照片修饰程序、创建数字艺术的工具、在线批处理系统、批量生产的图像渲染器、图像格式转换器等。

## 在线中文文档

[GIMP - GNU 图像处理程序](https://docs.gimp.org/2.10/zh_CN/)

## 2.10版本运行

### Windows11命令行

将gimp安装路径/bin添加到系统变量path中，然后命令行输入

```
gimp-2.10 
```

或

```
gimp-2.10 X:/xX/../XX.jpg
```

来打开指定图片，gimp支持多种文件格式，包括 JPEG、PNG、GIF、PSD、DDS、XPM、TIFF、TGA、MPEG、PS、PDF、PCX、BMP 等。

## 更改语言

### gimp图形界面

在图形窗口中选择Edit->Preference->Interface->System Language->汉语 即可修改成中文。

### 其他

**Windows下**

“系统变量” 区域中的 控制面板 → 系统 → 高级 → 环境 按钮：**新建** 按钮：输入 LANG 作为名称，fr 或 de... 作为值。注意！你必须连续点击3次 **OK** 来确认你的选择。

如果你经常更改语言，可以创建一个批处理文件来更改语言。打开记事本。输入以下命令（例如对法语而言）：

**`set lang=frstart gimp-2.10.exe`**

保存该文件为 `GIMP-FR.BAT` （或其他名称，但始终带有`.BAT`扩展名）。创建一个快捷方式并拖到桌面。

另一可能：开始 → 程序 → GTK 运行时环境 然后 选择语言 并在下拉列表中选择想要的语言。

### 命令行参数

即使启动GIMP时不需要参数，最常用的参数依然如下列出。在Unix系统上，你可以使用 **`man gimp`** 获取完整列表。

命令行参数必须作为 **gimp-2.10 [OPTION...] [FILE|URI...]**，用于启动 GIMP 的命令行中。

| **-?, --help**                     | 显示所有命令行选项列表。                                     |
| ---------------------------------- | ------------------------------------------------------------ |
| **--help-all**                     | 显示所有帮助选项。                                           |
| **--help-gtk**                     | 显示 GTK+ 选项。                                             |
| **-v, --version**                  | 打印当前 GIMP 版本并退出。                                   |
| **--license**                      | 显示许可证信息并退出。                                       |
| **--verbose**                      | 显示详细启动信息。                                           |
| **-n, --new-instance**             | 启动一个新的 GIMP 实例。                                     |
| **-a, --as-new**                   | 作为新图像打开图像。                                         |
| **-i, --no-interface**             | 无界面运行。                                                 |
| **-d, --no-data**                  | 不加载图案、渐变、调色板、或笔刷。通常在需要最小化启动时间的非交互式情况下很有用。 |
| **-f, --no-fonts**                 | 不加载任何字体。这对于为不使用字体的脚本更快地加载GIMP，或查找与挂起GIMP的畸形字体相关的问题非常有用。 |
| **-s, --no-splash**                | 启动时不显示启动画面。                                       |
| **--no-shm**                       | 不在GIMP和插件之间使用共享内存。                             |
| **--no-cpu-accel**                 | 不使用特殊的 CPU 加速功能。用于查找或禁用有问题的加速硬件或功能。 |
| **--session=\*`name`\***           | 该GIMP会话使用不同`sessionrc`。给定会话名将追加默认`sessionrc`文件名。 |
| **--gimprc=`filename`**            | 使用替代的 `gimprc` 代替默认的。该`gimprc`文件包含你的偏好设置的记录。在插件路径或机器规格可能不同的情况下很有用。 |
| **--system-gimprc=\*`filename`\*** | 使用替代的系统gimprc文件。                                   |
| **-b, --batch=\*`commands`\***     | 以非交互方式执行一组命令。这组命令通常采用脚本的形式，可由GIMP脚本扩展之一执行。当命令为**`-`**时，从标准输入读取命令。 |
| **--batch-interpreter=\*`proc`\*** | 指定用于处理批处理命令的程序。默认程序是 Script-Fu。         |
| **--console-messages**             | 不要弹出有关错误或警告的对话框。改为在控制台上打印消息。     |
| **--pdb-compat-mode=\*`mode`\***   | PDB 兼容模式（关闭                                           |
| **--stack-trace-mode=\*`mode`\***  | 在崩溃的情况下进行调试（从不                                 |
| **--debug-handlers**               | 启用非致命调试信号处理程序。对GIMP调试很有用。               |
| **--g-fatal-warnings**             | 使所有警告都是致命的。对调试有用。                           |
| **--dump-gimprc**                  | 使用默认设置输出一个 gimprc 文件。如果弄乱了 gimprc 文件，则很有用。 |
| **--display=\*`display`\***        | 使用指定的 X 显示（不适用于所有平台）。                      |
| **--show-playground**              | Show a preferences page with experimental features.          |

## 插件安装

### G'MIC

[gmic.eu](https://gmic.eu/download.html)

在首选项->文件->插件 复制 本地插件路径（尽量别用C盘默认路径），然后运行下载好的gmic_3.3.2_gimp2.10_win64.exe，自定义刚才的安装路径，确认安装即可，重启gimc2.10后，打开帮助->插件浏览器，可找到G'MIC Qt的插件信息。并且在滤镜Filters下找到G'MIC-Qt选项。

## 使用

### 添加Alpha（透明）通道

右键图层，选择添加透明度通道，如果已经变灰不可操作，则该图层已有透明通道。

# 图片下载

## Pixabay下载

https://pixabay.com/zh/

# Blender

## Windows11下载

[Download — blender.org](https://www.blender.org/download/)

## 简介

Blender 是一款永久开源免费的 3D 创作软件，支持整个 3D 创作流程：建模、雕刻、骨骼装配、动画、模拟、实时渲染、合成和运动跟踪，甚至可用作视频编辑及游戏创建。

## 在线中文手册

[Blender 4.1 参考手册 — Blender Manual](https://docs.blender.org/manual/zh-hans/dev/)

# Latex

## 安装TexLive环境+Vscode配置

[Visual Studio Code (vscode)配置LaTeX最详细版（vscode下载安装+基本设置+内外pdf查看器设置+个人配置代码）_vscode配置latex-CSDN博客](https://blog.csdn.net/qq_44089921/article/details/107719981)

```

C:\Users\XXX>xelatex -v
XeTeX 3.141592653-2.6-0.999995 (TeX Live 2023)
kpathsea version 6.3.5
Copyright 2023 SIL International, Jonathan Kew and Khaled Hosny.
There is NO warranty.  Redistribution of this software is
covered by the terms of both the XeTeX copyright and
the Lesser GNU General Public License.
For more information about these matters, see the file
named COPYING and the XeTeX source.
Primary author of XeTeX: Jonathan Kew.
Compiled with ICU version 72.1; using 72.1
Compiled with zlib version 1.2.13; using 1.2.13
Compiled with FreeType2 version 2.13.0; using 2.13.0
Compiled with Graphite2 version 1.3.14; using 1.3.14
Compiled with HarfBuzz version 7.0.1; using 7.0.1
Compiled with libpng version 1.6.39; using 1.6.39
Compiled with pplib version v2.05 less toxic i hope
Compiled with fontconfig version 2.14.2; using 2.14.2

```

```json
{
 //------------------------------LaTeX 配置----------------------------------
    // 设置是否自动编译
    "latex-workshop.latex.autoBuild.run":"never",
    //右键菜单
    "latex-workshop.showContextMenu":true,
    //从使用的包中自动补全命令和环境
    "latex-workshop.intellisense.package.enabled": true,
    //编译出错时设置是否弹出气泡设置
    "latex-workshop.message.error.show": false,
    "latex-workshop.message.warning.show": false,
    // 编译工具和命令
    "latex-workshop.latex.tools": [
        {
            "name": "xelatex",
            "command": "xelatex",
            "args": [
                "-synctex=1",
                "-interaction=nonstopmode",
                "-file-line-error",
                "%DOCFILE%"
            ]
        },
        {
            "name": "pdflatex",
            "command": "pdflatex",
            "args": [
                "-synctex=1",
                "-interaction=nonstopmode",
                "-file-line-error",
                "%DOCFILE%"
            ]
        },
        {
            "name": "latexmk",
            "command": "latexmk",
            "args": [
                "-synctex=1",
                "-interaction=nonstopmode",
                "-file-line-error",
                "-pdf",
                "-outdir=%OUTDIR%",
                "%DOCFILE%"
            ]
        },
        {
            "name": "bibtex",
            "command": "bibtex",
            "args": [
                "%DOCFILE%"
            ]
        }
    ],
    // 用于配置编译链
    "latex-workshop.latex.recipes": [
        {
            "name": "XeLaTeX",
            "tools": [
                "xelatex"
            ]
        },
        {
            "name": "PDFLaTeX",
            "tools": [
                "pdflatex"
            ]
        },
        {
            "name": "BibTeX",
            "tools": [
                "bibtex"
            ]
        },
        {
            "name": "LaTeXmk",
            "tools": [
                "latexmk"
            ]
        },
        {
            "name": "xelatex -> bibtex -> xelatex*2",
            "tools": [
                "xelatex",
                "bibtex",
                "xelatex",
                "xelatex"
            ]
        },
        {
            "name": "pdflatex -> bibtex -> pdflatex*2",
            "tools": [
                "pdflatex",
                "bibtex",
                "pdflatex",
                "pdflatex"
            ]
        }
    ],
    //文件清理。此属性必须是字符串数组
    "latex-workshop.latex.clean.fileTypes": [
        "*.aux",
        "*.bbl",
        "*.blg",
        "*.idx",
        "*.ind",
        "*.lof",
        "*.lot",
        "*.out",
        "*.toc",
        "*.acn",
        "*.acr",
        "*.alg",
        "*.glg",
        "*.glo",
        "*.gls",
        "*.ist",
        "*.fls",
        "*.log",
        "*.fdb_latexmk"
    ],
    //设置为onFaild 在构建失败后清除辅助文件
    "latex-workshop.latex.autoClean.run": "onFailed",
    // 使用上次的recipe编译组合
    "latex-workshop.latex.recipe.default": "lastUsed",
    // 用于反向同步的内部查看器的键绑定。ctrl/cmd +点击(默认)或双击
    "latex-workshop.view.pdf.internal.synctex.keybinding": "double-click",



    //使用 SumatraPDF 预览编译好的PDF文件
    // 设置VScode内部查看生成的pdf文件
    "latex-workshop.view.pdf.viewer": "external",
    // PDF查看器用于在\ref上的[View on PDF]链接
    "latex-workshop.view.pdf.ref.viewer":"auto",
    // 使用外部查看器时要执行的命令。此功能不受官方支持。
    "latex-workshop.view.pdf.external.viewer.command": "XXXXXX/SumatraPDF.exe", // 注意修改路径
    // 使用外部查看器时，latex-workshop.view.pdf.external.view .command的参数。此功能不受官方支持。%PDF%是用于生成PDF文件的绝对路径的占位符。
    "latex-workshop.view.pdf.external.viewer.args": [
        "%PDF%"
    ],
    // 将synctex转发到外部查看器时要执行的命令。此功能不受官方支持。
    "latex-workshop.view.pdf.external.synctex.command": "XXXXXX/SumatraPDF.exe", // 注意修改路径
    // latex-workshop.view.pdf.external.synctex的参数。当同步到外部查看器时。%LINE%是行号，%PDF%是生成PDF文件的绝对路径的占位符，%TEX%是触发syncTeX的扩展名为.tex的LaTeX文件路径。
    "latex-workshop.view.pdf.external.synctex.args": [
        "-forward-search",
        "%TEX%",
        "%LINE%",
        "-reuse-instance",
        "-inverse-search",
        "code \"XXXXXX/resources/app/out/cli.js\" -r -g \"%f:%l\"", // 注意修改路径
        "%PDF%"
    ]
}

```



# MATLAB R2022a

# GeoGebra 5

# Sumatra PDF

[Sumatra PDF reader download page](https://www.sumatrapdfreader.org/downloadafter)

# Java Guide
## [Get Started with Java](https://www.baeldung.com/get-started-with-java-series)

If you are new to Java, this series will go over the basic syntax of the language, introduce classes and objects and a few simple examples of using common Java structures.

Java is one of the most popular programming languages, often used for building web and enterprise scale applications. This collection of tutorials will help you get started with the basic concepts in Java.

### Java Language Basics

Before learning about classes and objects, let’s start with the basic syntax of the language.

#### [Basic Syntax in Java](https://www.baeldung.com/java-syntax)

#### [Introduction to Primitives](https://www.baeldung.com/java-primitives)

#### [Java main() Method Explained](https://www.baeldung.com/java-main-method)

#### [Control Structures](https://www.baeldung.com/java-control-structures)

#### [A Guide to Java Loops](https://www.baeldung.com/java-loops)

#### [Guide to Java Packages](https://www.baeldung.com/java-packages)

#### [Pass-By-Value as a Parameter Passing Mechanism in Java](https://www.baeldung.com/java-pass-by-value-or-pass-by-reference)

### Java OOP

Next, let’s dive into the world of object-oriented programming, with practical Java examples.

#### [Java Classes and Objects](https://www.baeldung.com/java-classes-objects)

#### [Concrete Classes](https://www.baeldung.com/java-concrete-class)

#### [Access Modifiers](https://www.baeldung.com/java-access-modifiers)

#### [Constructors](https://www.baeldung.com/java-constructors)

#### [A Guide to Creating Objects](https://www.baeldung.com/java-initialization)

#### [Abstract Classes](https://www.baeldung.com/java-abstract-class)

#### [Interfaces](https://www.baeldung.com/java-interfaces)

#### [Guide to Inheritance](https://www.baeldung.com/java-inheritance)

#### [Inheritance and Composition (Is-a vs Has-a relationship) in Java](https://www.baeldung.com/java-inheritance-composition)

#### [The *this* Keyword](https://www.baeldung.com/java-this)

#### [The *super* Keyword](https://www.baeldung.com/java-super)

#### [Method Overloading and Overriding](https://www.baeldung.com/java-method-overload-override)

#### [The *static* Keyword](https://www.baeldung.com/java-static)

#### [Java Enums](https://www.baeldung.com/a-guide-to-java-enums)

#### [The *final* Keyword](https://www.baeldung.com/java-final)

### Java Strings

Strings are a common data type in Java, representing text. Let’s have a look at how to create and use *String* objects.

#### [All About String in Java](https://www.baeldung.com/java-string)

##### String Basics

###### [Java Multi-line String](https://www.baeldung.com/java-multiline-string)

###### [Checking for Empty or Blank Strings in Java](https://www.baeldung.com/java-blank-empty-strings)

###### [How to Remove the Last Character of a String?](https://www.baeldung.com/java-remove-last-character-of-string)

###### [Java - Count Occurrences of a Char in a String](https://www.baeldung.com/java-count-chars)

###### [Check if a String is a Palindrome](https://www.baeldung.com/java-palindrome)

###### [Split a String in Java](https://www.baeldung.com/java-split-string)

###### [Compact Strings in Java 9](https://www.baeldung.com/java-9-compact-string)

###### [Comparing Strings in Java](https://www.baeldung.com/java-compare-strings)

###### [CharSequence vs. String in Java](https://www.baeldung.com/java-char-sequence-string)

###### [Adding a Newline Character to a String in Java](https://www.baeldung.com/java-string-newline)

###### [Guide to Character Encoding](https://www.baeldung.com/java-char-encoding)

###### [Concatenating Strings In Java](https://www.baeldung.com/java-strings-concatenation)

###### [String Initialization in Java](https://www.baeldung.com/java-string-initialization)

###### [Why String is Immutable in Java?](https://www.baeldung.com/java-string-immutable)

##### String Helper Classes and Tool

###### [Guide to java.util.Formatter](https://www.baeldung.com/java-string-formatter)

###### [Quick Guide to the Java StringTokenizer](https://www.baeldung.com/java-stringtokenizer)

###### [StringBuilder and StringBuffer in Java](https://www.baeldung.com/java-string-builder-string-buffer)

###### [Java 8 StringJoiner](https://www.baeldung.com/java-string-joiner)

##### String Conversions

###### [Java String Conversions](https://www.baeldung.com/java-string-conversions)

###### [Converting Strings to Enums in Java](https://www.baeldung.com/java-string-to-enum)

###### [Converting a Stack Trace to a String in Java](https://www.baeldung.com/java-stacktrace-to-string)

###### [Converting String to Stream of chars](https://www.baeldung.com/java-string-to-stream)

###### [Converting a List to String in Java](https://www.baeldung.com/java-list-to-string)

###### [Convert Hex to ASCII in Java](https://www.baeldung.com/java-convert-hex-to-ascii)

###### [Check If a String Is Numeric in Java](https://www.baeldung.com/java-check-string-number)

###### [Format ZonedDateTime to String](https://www.baeldung.com/java-format-zoned-datetime-string)

###### [Converting Between Byte Arrays and Hexadecimal Strings in Java](https://www.baeldung.com/java-byte-arrays-hex-strings)

###### [Convert String to Byte Array and Reverse in Java](https://www.baeldung.com/java-string-to-byte-array)

###### [Array to String Conversions](https://www.baeldung.com/java-array-to-string)

###### [Encode a String to UTF-8 in Java](https://www.baeldung.com/java-string-encode-utf-8)

###### [Convert Character Array to String in Java](https://www.baeldung.com/java-char-array-to-string)

###### [Guide to Escaping Characters in Java RegExps](https://www.baeldung.com/java-regexp-escape-char)

###### [Converting String to BigDecimal in Java](https://www.baeldung.com/java-string-to-bigdecimal)

##### String Primitive Conversions

###### [Convert String to int or Integer in Java](https://www.baeldung.com/java-convert-string-to-int-or-integer)

###### [Convert char to String in Java](https://www.baeldung.com/java-convert-char-to-string)

##### String IO Conversions

###### **[Java InputStream to String](https://www.baeldung.com/convert-input-stream-to-string)\**(popular)\****

###### [Java String to InputStream](https://www.baeldung.com/convert-string-to-input-stream)

###### [Java – String to Reader](https://www.baeldung.com/java-convert-string-to-reader)

###### [Java – Reader to String](https://www.baeldung.com/java-convert-reader-to-string)

##### String Tools

###### [String Processing with Apache Commons Lang 3](https://www.baeldung.com/string-processing-commons-lang)

###### [Guava CharMatcher](https://www.baeldung.com/guava-string-charmatcher)

###### [Introduction to Apache Commons Text](https://www.baeldung.com/java-apache-commons-text)

##### String API

###### [Java String.String()](https://www.baeldung.com/string/constructor)

###### [Java String.codePointCount()](https://www.baeldung.com/string/code-point-count)

###### [Java String.codePointAt()](https://www.baeldung.com/string/code-point-at)

###### [Java String.concat()](https://www.baeldung.com/string/concat)

###### [Java String.contains()](https://www.baeldung.com/string/contains)

###### [Java String.copyValueOf()](https://www.baeldung.com/string/copy-value-of)

###### [Java String.endsWith()](https://www.baeldung.com/string/ends-with)

###### [Java String.format()](https://www.baeldung.com/string/format)

###### [Java String.getBytes()](https://www.baeldung.com/string/get-bytes)

###### [Java String.indexOf()](https://www.baeldung.com/string/index-of)

###### [Java String.intern()](https://www.baeldung.com/string/intern)

###### [Java String.isEmpty()](https://www.baeldung.com/string/is-empty)

###### [Java String.lastIndexOf()](https://www.baeldung.com/string/last-index-of)

###### [Java String.regionMatches()](https://www.baeldung.com/string/region-matches)

###### [Java String.replace()](https://www.baeldung.com/string/replace)

###### [Java String.replaceAll()](https://www.baeldung.com/string/replace-all)

###### [Java String.split()](https://www.baeldung.com/string/split)

###### [Java String.startsWith()](https://www.baeldung.com/string/starts-with)

###### [Java String.subSequence()](https://www.baeldung.com/string/sub-sequence)

###### [Java String.substring()](https://www.baeldung.com/string/substring)

###### [Java String.toLowerCase()](https://www.baeldung.com/string/to-lower-case)

###### [Java String.toUpperCase()](https://www.baeldung.com/string/to-upper-case)

###### [Java String.trim()](https://www.baeldung.com/string/trim)

###### [Java String.valueOf()](https://www.baeldung.com/string/value-of)

#### [Why String is Immutable in Java](https://www.baeldung.com/java-string-immutable)

#### [Comparing Strings](https://www.baeldung.com/java-compare-strings)

#### [Java String Conversions](https://www.baeldung.com/java-string-conversions)

#### [Java *toString()* Method](https://www.baeldung.com/java-tostring)

### Java Exceptions

Exceptions are abnormal behaviors during the execution of a program. Let’s understand what Java exceptions are and how they can help us write less error-prone code.

#### [Exception Handling in Java](https://www.baeldung.com/java-exceptions)

#### [Checked and Unchecked Exceptions in Java](https://www.baeldung.com/java-checked-unchecked-exceptions)

#### [Create a Custom Exception](https://www.baeldung.com/java-new-custom-exception)

#### [Chained Exceptions](https://www.baeldung.com/java-chained-exceptions)

#### [Difference Between Throw and Throws in Java](https://www.baeldung.com/java-throw-throws)

#### [Try with Resources](https://www.baeldung.com/java-try-with-resources)

### Java Arrays

It’s time to have a look at our first data structure in Java – arrays.

#### [Arrays in Java: A Reference Guide](https://www.baeldung.com/java-arrays-guide)

#### [Initializing Arrays](https://www.baeldung.com/java-initialize-array)

#### [The java.util.Arrays Class](https://www.baeldung.com/java-util-arrays)

### Java Collections

A more complex type of data structure are collections, which, compared to arrays, have a dynamic size.

#### [ArrayList](https://www.baeldung.com/java-arraylist)

#### [LinkedList](https://www.baeldung.com/java-linkedlist)

#### [The Diamond Operator in Java](https://www.baeldung.com/java-diamond-operator)

#### [Comparator and Comparable](https://www.baeldung.com/java-comparator-comparable)

#### **[The Basics of Java Generics](https://www.baeldung.com/java-generics)\**(popular)\****

#### [HashSet](https://www.baeldung.com/java-hashset)

#### [HashMap](https://www.baeldung.com/java-hashmap)

#### [Initializing a HashMap](https://www.baeldung.com/java-initialize-hashmap)

#### [Iterator](https://www.baeldung.com/java-iterator)

#### **[Converting between an Array and a List in Java](https://www.baeldung.com/convert-array-to-list-and-list-to-array)\**(popular)\****

### Java Streams

Finally, we get to Java Streams – which are not data structures, but wrappers around data sources and allow us to process data more efficiently.

#### [Introduction to Java 8 Streams](https://www.baeldung.com/java-8-streams-introduction)

#### **[The Java 8 Stream API Tutorial](https://www.baeldung.com/java-8-streams)\**(popular)\****

#### **[Functional Interfaces in Java 8](https://www.baeldung.com/java-8-functional-interfaces)\**(popular)\****

#### [Guide to Java 8’s Collectors](https://www.baeldung.com/java-8-collectors)

#### [Java Stream Filter with Lambda Expression](https://www.baeldung.com/java-stream-filter-lambda)

### Java IO

Look at ways to interact with files and other data input/output methods in Java.

#### [Console I/O in Java](https://www.baeldung.com/java-console-input-output)

#### [Reading from a File](https://www.baeldung.com/java-read-file)

#### [Creating a File](https://www.baeldung.com/java-how-to-create-a-file)

#### **[Writing to a File](https://www.baeldung.com/java-write-to-file)\**(popular)\****

#### [Introduction to the Java NIO2 File API](https://www.baeldung.com/java-nio-2-file-api)

#### [BufferedReader](https://www.baeldung.com/java-buffered-reader)

#### [OutputStream](https://www.baeldung.com/java-outputstream)

### Java Development Environment

It’s important to understand the fundamentals of how the Java Virtual Machine and other development tools work.

#### [Difference Between JVM, JRE, and JDK](https://www.baeldung.com/jvm-vs-jre-vs-jdk)

#### [Stack Memory and Heap Space in Java](https://www.baeldung.com/java-stack-heap)

#### [Class Loaders](https://www.baeldung.com/java-classloaders)

Of course, there’s a lot more to learn about Java programming, and the development tools and APIs available are changing every day. But with a strong foundation of the basic concepts, you can jump in to building something and always continue learning.

For more tutorials and examples of problem-solving in Java, also have a look at the [Java category](https://www.baeldung.com/category/java/) on the site.

Comments are closed on this article!

## Core Java Examples

In this section, we’ll continue with more Core Java examples that show how to use the basic concepts of the language.

### **[Comparing Objects in Java](https://www.baeldung.com/java-comparing-objects)**

###  **[Wrapper Classes in Java](https://www.baeldung.com/java-wrapper-classes)**

### [Quick Guide to java.lang.System](https://www.baeldung.com/java-lang-system)

### [Object Type Casting in Java](https://www.baeldung.com/java-type-casting)

### [Java 8 – Powerful Comparison with Lambdas](https://www.baeldung.com/java-8-sort-lambda)

### **[Guide To Java 8 Optional](https://www.baeldung.com/java-optional)\**(popular)\****

### **[Guide to UUID in Java](https://www.baeldung.com/java-uuid)\**(popular)\****

### [The StackOverflowError in Java](https://www.baeldung.com/java-stack-overflow-error)

### [Immutable Objects in Java](https://www.baeldung.com/java-immutable-object)

### [Anonymous Classes in Java](https://www.baeldung.com/java-anonymous-classes)

### [Command-Line Arguments in Java](https://www.baeldung.com/java-command-line-arguments)

### **[Java 14 Record Keyword](https://www.baeldung.com/java-record-keyword)**
### [Iterating over Enum Values in Java](https://www.baeldung.com/java-enum-iteration)

### [Comparing Dates in Java](https://www.baeldung.com/java-comparing-dates)

### [RegEx for matching Date Pattern in Java](https://www.baeldung.com/java-date-regular-expressions)

### **[Period and Duration in Java](https://www.baeldung.com/java-period-duration)**

### [Java Timer](https://www.baeldung.com/java-timer-and-timertask)

### [Number Formatting in Java](https://www.baeldung.com/java-number-formatting)

### **[How to Round a Number to N Decimal Places in Java](https://www.baeldung.com/java-round-decimal-number)**

### [Java – Random Long, Float, Integer and Double](https://www.baeldung.com/java-generate-random-long-float-integer-double)

### [Comparing Long Values in Java](https://www.baeldung.com/java-compare-long-values)

### **[Convert Date to LocalDate or LocalDateTime and Back](https://www.baeldung.com/java-date-to-localdate-and-localdatetime)\**(popular)\****

### [Using an Interface vs. Abstract Class in Java](https://www.baeldung.com/java-interface-vs-abstract-class)

### **[Using Pairs in Java](https://www.baeldung.com/java-pairs)\**(popular)\****

## [Java Concurrency](https://www.baeldung.com/java-concurrency)

Concurrency is a large area in Java, but it’s also an important topic to understand. In this series, we’ll go over the core concepts and learn how to work with threads using practical examples.

### Java Concurrency Basics

#### [Overview of the java.util.concurrent](https://www.baeldung.com/java-util-concurrent)

#### **[Guide to the Synchronized Keyword in Java](https://www.baeldung.com/java-synchronized)\**(popular)\****

#### [Guide to the Volatile Keyword in Java](https://www.baeldung.com/java-volatile)

#### [Guide to java.util.concurrent.Future](https://www.baeldung.com/java-future)

#### [An Introduction to ThreadLocal in Java](https://www.baeldung.com/java-threadlocal)

#### [Life Cycle of a Thread in Java](https://www.baeldung.com/java-thread-lifecycle)

#### [How to Kill a Java Thread](https://www.baeldung.com/java-thread-stop)

#### **[Introduction to Thread Pools in Java](https://www.baeldung.com/thread-pool-java-and-guava)\**(popular)\****

#### [Implementing a Runnable vs Extending a Thread](https://www.baeldung.com/java-runnable-vs-extending-thread)

#### [wait and notify() Methods in Java](https://www.baeldung.com/java-wait-notify)

#### [Runnable vs. Callable in Java](https://www.baeldung.com/java-runnable-callable)

#### [Difference Between Wait and Sleep in Java](https://www.baeldung.com/java-wait-and-sleep)

#### [The Thread.join() Method in Java](https://www.baeldung.com/java-thread-join)

#### [Using a Mutex Object in Java](https://www.baeldung.com/java-mutex)

#### [ThreadPoolTaskExecutor corePoolSize vs. maxPoolSize](https://www.baeldung.com/java-threadpooltaskexecutor-core-vs-max-poolsize)

#### [Asynchronous Programming in Java](https://www.baeldung.com/java-asynchronous-programming)

### Advanced Concurrency in Java

#### [Daemon Threads in Java](https://www.baeldung.com/java-daemon-thread)

#### [A Guide to the Java ExecutorService](https://www.baeldung.com/java-executor-service-tutorial)**(popular)**

#### [Guide to the Fork/Join Framework in Java](https://www.baeldung.com/java-fork-join)

#### [Custom Thread Pools In Java 8 Parallel Streams](https://www.baeldung.com/java-8-parallel-streams-custom-threadpool)

#### [Guide to CountDownLatch in Java](https://www.baeldung.com/java-countdown-latch)

#### [Guide to java.util.concurrent.Locks](https://www.baeldung.com/java-concurrent-locks)

#### [ExecutorService – Waiting for Threads to Finish](https://www.baeldung.com/java-executor-wait-for-threads)

#### **[Guide To CompletableFuture](https://www.baeldung.com/java-completablefuture)\**(popular)\****

#### [CyclicBarrier in Java](https://www.baeldung.com/java-cyclic-barrier)

#### [Guide to ThreadLocalRandom in Java](https://www.baeldung.com/java-thread-local-random)

#### [Java CyclicBarrier vs CountDownLatch](https://www.baeldung.com/java-cyclicbarrier-countdownlatch)

#### [What is Thread-Safety and How to Achieve it?](https://www.baeldung.com/java-thread-safety)

#### [How to Delay Code Execution in Java](https://www.baeldung.com/java-delay-code-execution)

#### [How to Stop Execution After a Certain Time in Java](https://www.baeldung.com/java-stop-execution-after-certain-time)

### Other Concurrency Resources

#### [The Dining Philosophers Problem in Java](https://www.baeldung.com/java-dining-philoshophers)

#### [Java Concurrency Interview Questions (+ Answers)](https://www.baeldung.com/java-concurrency-interview-questions)

## [Java Collections](https://www.baeldung.com/java-collections)

This tutorials will go over the main data structures in Java and common operations we can perform with them.

### List

#### List Implementations

##### [A Guide to the Java LinkedList](https://www.baeldung.com/java-linkedlist)

##### [Guide to the Java ArrayList](https://www.baeldung.com/java-arraylist)

##### [Immutable ArrayList in Java](https://www.baeldung.com/java-immutable-list)

##### [Guide to CopyOnWriteArrayList](https://www.baeldung.com/java-copy-on-write-arraylist)

##### [Multi Dimensional ArrayList in Java](https://www.baeldung.com/java-multi-dimensional-arraylist)

#### List Operations

##### [Converting Iterator to List](https://www.baeldung.com/java-convert-iterator-to-list)

##### [Java – Get Random Item/Element From a List](https://www.baeldung.com/java-random-list-element)

##### [Partition a List in Java](https://www.baeldung.com/java-list-split)

##### [Removing all nulls from a List in Java](https://www.baeldung.com/java-remove-nulls-from-list)

##### **[Removing all duplicates from a List in Java](https://www.baeldung.com/java-remove-duplicates-from-list)\**(popular)\****

##### [Check If Two Lists are Equal in Java](https://www.baeldung.com/java-test-a-list-for-ordinality-and-equality)

##### [How to Find an Element in a List with Java](https://www.baeldung.com/find-list-element-java)

##### [Java List UnsupportedOperationException](https://www.baeldung.com/java-list-unsupported-operation-exception)

##### [Copy a List to Another List in Java](https://www.baeldung.com/java-copy-list-to-another)

##### [Remove All Occurrences of a Specific Value from a List](https://www.baeldung.com/java-remove-value-from-list)

##### [Add Multiple Items to an Java ArrayList](https://www.baeldung.com/java-add-items-array-list)

##### [Remove the First Element from a List](https://www.baeldung.com/java-remove-first-element-from-list)

##### [Ways to Iterate Over a List in Java](https://www.baeldung.com/java-iterate-list)

##### [Intersection of Two Lists in Java](https://www.baeldung.com/java-lists-intersection)

##### [How to Count Duplicate Elements in Arraylist](https://www.baeldung.com/java-count-duplicate-elements-arraylist)

##### [Finding the Differences Between Two Lists in Java](https://www.baeldung.com/java-lists-difference)

##### [Reversing a Linked List in Java](https://www.baeldung.com/java-reverse-linked-list)

##### [Assert Two Lists for Equality Ignoring Order in Java](https://www.baeldung.com/java-assert-lists-equality-ignore-order )

### Sets

#### Set Implementations

##### [A Guide to TreeSet in Java](https://www.baeldung.com/java-tree-set)

##### [A Guide to HashSet in Java](https://www.baeldung.com/java-hashset)

### Maps

Map Implementations

##### [A Guide to Java HashMap](https://www.baeldung.com/java-hashmap)

##### [The Java HashMap Under the Hood](https://www.baeldung.com/java-hashmap-advanced)

##### [A Guide to TreeMap in Java](https://www.baeldung.com/java-treemap)

##### [Java TreeMap vs HashMap](https://www.baeldung.com/java-treemap-vs-hashmap)

##### [Guide to WeakHashMap in Java](https://www.baeldung.com/java-weakhashmap)

##### [A Guide to ConcurrentMap](https://www.baeldung.com/java-concurrent-map)

##### [Guide to the ConcurrentSkipListMap](https://www.baeldung.com/java-concurrent-skip-list-map)

##### [An Introduction to Java.util.Hashtable Class](https://www.baeldung.com/java-hash-table)

##### [A Guide to LinkedHashMap in Java](https://www.baeldung.com/java-linked-hashmap)

##### [A Guide to EnumMap](https://www.baeldung.com/java-enum-map)

##### [Immutable Map Implementations in Java](https://www.baeldung.com/java-immutable-maps)

##### [Java Map With Case-Insensitive Keys](https://www.baeldung.com/java-map-with-case-insensitive-keys)

##### [Java HashMap Load Factor](https://www.baeldung.com/java-hashmap-load-factor)

##### [Collections.synchronizedMap vs. ConcurrentHashMap](https://www.baeldung.com/java-synchronizedmap-vs-concurrenthashmap)

#### Map Operations

##### [How to Store Duplicate Keys in a Map in Java?](https://www.baeldung.com/java-map-duplicate-keys)

##### [Initialize a HashMap in Java](https://www.baeldung.com/java-initialize-hashmap)

##### [Merging Two Maps with Java 8](https://www.baeldung.com/java-merge-maps)

##### [Sort a HashMap in Java](https://www.baeldung.com/java-hashmap-sort)

##### [Comparing Two HashMaps in Java](https://www.baeldung.com/java-compare-hashmaps)

##### [Using the Map.Entry Java Class](https://www.baeldung.com/java-map-entry)

##### [Working With Maps Using Streams](https://www.baeldung.com/java-maps-streams)

##### **[Iterate over a Map in Java](https://www.baeldung.com/java-iterate-map)\**(popular)\****

### Queues

##### [Guide to PriorityBlockingQueue in Java](https://www.baeldung.com/java-priority-blocking-queue)

##### [Guide to java.util.concurrent.BlockingQueue](https://www.baeldung.com/java-blocking-queue)

##### [A Guide to Java SynchronousQueue](https://www.baeldung.com/java-synchronous-queue)

##### [Guide to the Java TransferQueue](https://www.baeldung.com/java-transfer-queue)

##### [Guide to DelayQueue](https://www.baeldung.com/java-delay-queue)

##### [Introduction to the Java ArrayDeque](https://www.baeldung.com/java-array-deque)

##### [Guide to the Java Queue Interface](https://www.baeldung.com/java-queue)

##### [A Guide to Concurrent Queues in Java](https://www.baeldung.com/java-concurrent-queues)

### Convert Collections

##### **[Converting between an Array and a List in Java](https://www.baeldung.com/convert-array-to-list-and-list-to-array)\**(popular)\****

##### [Converting Between an Array and a Set in Java](https://www.baeldung.com/convert-array-to-set-and-set-to-array)

##### [Converting between a List and a Set in Java](https://www.baeldung.com/convert-list-to-set-and-set-to-list)

##### [Convert a Map to an Array, List or Set in Java](https://www.baeldung.com/convert-map-values-to-array-list-set)

##### [How to Convert List to Map in Java](https://www.baeldung.com/java-list-to-map)

##### [Map to String Conversion in Java](https://www.baeldung.com/java-map-to-string-conversion)

##### [Arrays.asList vs new ArrayList(Arrays.asList())](https://www.baeldung.com/java-arrays-aslist-vs-new-arraylist)

##### [Collecting Stream Elements into a List in Java](https://www.baeldung.com/java-stream-to-list-collecting)

### Operations on Collection

##### [The Difference Between Collection.stream().forEach() and Collection.forEach()](https://www.baeldung.com/java-collection-stream-foreach)

##### [Sorting in Java](https://www.baeldung.com/java-sorting)

##### [Shuffling Collections In Java](https://www.baeldung.com/java-shuffle-collection)

##### [Flattening Nested Collections in Java](https://www.baeldung.com/java-flatten-nested-collections)

##### [Zipping Collections in Java](https://www.baeldung.com/java-collections-zip)

##### [Join and Split Arrays and Collections in Java](https://www.baeldung.com/java-join-and-split)

##### [Java – Combine Multiple Collections](https://www.baeldung.com/java-combine-multiple-collections)

##### [Finding Max/Min of a List or Collection](https://www.baeldung.com/java-collection-min-max)

##### [Collect a Java Stream to an Immutable Collection](https://www.baeldung.com/java-stream-immutable-collection)

##### [Java 9 Convenience Factory Methods for Collections](https://www.baeldung.com/java-9-collections-factory-methods)

##### [Java Collections Interview Questions](https://www.baeldung.com/java-collections-interview-questions)

##### [A Guide to Iterator in Java](https://www.baeldung.com/java-iterator)

##### [Getting the Size of an Iterable in Java](https://www.baeldung.com/java-iterable-size)

##### [Removing Elements from Java Collections](https://www.baeldung.com/java-collection-remove-elements)

##### [Time Complexity of Java Collections](https://www.baeldung.com/java-collections-complexity)

### Apache Commons Collections

##### [Apache Commons Collections Bag](https://www.baeldung.com/apache-commons-bag)

##### [Apache Commons Collections SetUtils](https://www.baeldung.com/apache-commons-setutils)

##### [Apache Commons Collections OrderedMap](https://www.baeldung.com/apache-commons-ordered-map)

##### [Apache Commons Collections BidiMap](https://www.baeldung.com/commons-collections-bidi-map)

##### [A Guide to Apache Commons Collections CollectionUtils](https://www.baeldung.com/apache-commons-collection-utils)

##### [Apache Commons Collections MapUtils](https://www.baeldung.com/apache-commons-map-utils)

##### [Guide to Apache Commons CircularFifoQueue](https://www.baeldung.com/commons-circular-fifo-queue)

### Guava Collections

##### [Guava Collections Cookbook](https://www.baeldung.com/guava-collections)

##### [Guide to Guava Multimap](https://www.baeldung.com/guava-multimap)

##### [Guava – Join and Split Collections](https://www.baeldung.com/guava-joiner-and-splitter-tutorial)

##### [Guide to Guava Table](https://www.baeldung.com/guava-table)

### Other Collections

##### [Introduction to Eclipse Collections](https://www.baeldung.com/eclipse-collections)

##### [Introduction to PCollections](https://www.baeldung.com/java-pcollections)

##### [Filtering and Transforming Collections in Guava](https://www.baeldung.com/guava-filter-and-transform-a-collection)

##### [Hamcrest Collections Cookbook](https://www.baeldung.com/hamcrest-collections-arrays)

##### [Implementing a Binary Tree in Java](https://www.baeldung.com/java-binary-tree)

## [Java Streams](https://www.baeldung.com/java-streams)

This series is a comprehensive guide to working with the Stream API introduced in Java 8.

### Stream Basics

##### **[The Java 8 Stream API Tutorial](https://www.baeldung.com/java-8-streams)\**(popular)\****

##### [Introduction to Java 8 Streams](https://www.baeldung.com/java-8-streams-introduction)

##### [Java 8 Stream findFirst() vs. findAny()](https://www.baeldung.com/java-stream-findfirst-vs-findany)

##### **[Functional Interfaces in Java 8](https://www.baeldung.com/java-8-functional-interfaces)\**(popular)\****

### Stream Collectors

##### [Guide to Java 8’s Collectors](https://www.baeldung.com/java-8-collectors)

##### **[Guide to Java 8 groupingBy Collector](https://www.baeldung.com/java-groupingby-collector)\**(popular)\****

##### [New Stream Collectors in Java 9](https://www.baeldung.com/java9-stream-collectors)

##### [Collect a Java Stream to an Immutable Collection](https://www.baeldung.com/java-stream-immutable-collection)

##### [Java 8 Collectors toMap](https://www.baeldung.com/java-collectors-tomap)

### Operations with Streams

##### [How to Break from Java Stream forEach](https://www.baeldung.com/java-break-stream-foreach)

##### [Filtering a Stream of Optionals in Java](https://www.baeldung.com/java-filter-stream-of-optional)

##### [Custom Thread Pools In Java 8 Parallel Streams](https://www.baeldung.com/java-8-parallel-streams-custom-threadpool)

##### [Merging Streams in Java](https://www.baeldung.com/java-merge-streams)

##### [The Difference Between map() and flatMap()](https://www.baeldung.com/java-difference-map-and-flatmap)

##### [String Operations with Java Streams](https://www.baeldung.com/java-stream-operations-on-strings)

##### [How to Iterate Over a Stream With Indices](https://www.baeldung.com/java-stream-indices)

##### [Iterable to Stream in Java](https://www.baeldung.com/java-iterable-to-stream)

##### [How to Get the Last Element of a Stream in Java?](https://www.baeldung.com/java-stream-last-element)

##### [Converting String to Stream of chars](https://www.baeldung.com/java-string-to-stream)

##### [“Stream has already been operated upon or closed” Exception in Java](https://www.baeldung.com/java-stream-operated-upon-or-closed-exception)

##### [Java 8 and Infinite Streams](https://www.baeldung.com/java-inifinite-streams)

##### [How to Add a Single Element to a Stream](https://www.baeldung.com/java-stream-append-prepend)

##### [Primitive Type Streams in Java 8](https://www.baeldung.com/java-8-primitive-streams)

##### [DistinctBy in the Java Stream API](https://www.baeldung.com/java-streams-distinct-by)

##### [Java 9 Stream API Improvements](https://www.baeldung.com/java-9-stream-api)

##### [Introduction to Spliterator in Java](https://www.baeldung.com/java-spliterator)

##### [How to Use if/else Logic in Java 8 Streams](https://www.baeldung.com/java-8-streams-if-else-logic)

##### [Java 8 Predicate Chain](https://www.baeldung.com/java-predicate-chain)

##### [Java Stream Filter with Lambda Expression](https://www.baeldung.com/java-stream-filter-lambda)

##### [Summing Numbers with Java Streams](https://www.baeldung.com/java-stream-sum)

##### [Java 8 Streams peek() API](https://www.baeldung.com/java-streams-peek-api)

##### [Working With Maps Using Streams](https://www.baeldung.com/java-maps-streams)

##### [Guide to Stream.reduce()](https://www.baeldung.com/java-stream-reduce)

##### [When to Use a Parallel Stream in Java](https://www.baeldung.com/java-when-to-use-parallel-stream)

##### [Java 8 Stream skip() vs limit()](https://www.baeldung.com/java-stream-skip-vs-limit)

##### [Collecting Stream Elements into a List in Java](https://www.baeldung.com/java-stream-to-list-collecting)

### Java 8 Streams with Other Tools

##### [Java Streams vs Vavr Streams](https://www.baeldung.com/vavr-java-streams)

##### [Spring Data Java 8 Support](https://www.baeldung.com/spring-data-java-8)

##### [Java 8 Stream API Analogies in Kotlin](https://www.baeldung.com/kotlin/java-8-stream-vs-kotlin)

## [Java IO](https://www.baeldung.com/java-io)

This series cover common I/O operations in Java, including working with files, Readers and Input/OuputStreams.

### Java I/O – Working with Files

Let’s start with the basic File operations:

##### [Java – Create a File](https://www.baeldung.com/java-how-to-create-a-file)

##### **[How to Read a File in Java](https://www.baeldung.com/reading-file-in-java)\**(popular)\****

**[Java - Write to File](https://www.baeldung.com/java-write-to-file)\**(popular)\****

##### [Java – Rename or Move a File](https://www.baeldung.com/java-how-to-rename-or-move-a-file)

##### [Java – Delete a File](https://www.baeldung.com/how-to-delete-a-file-in-java)

##### [Getting a File’s Mime Type in Java](https://www.baeldung.com/java-file-mime-type)

##### [Java – Reading a Large File Efficiently](https://www.baeldung.com/java-read-lines-large-file)

##### [Check If a File or Directory Exists in Java](https://www.baeldung.com/java-file-directory-exists)

##### [Download a File From an URL in Java()](https://www.baeldung.com/java-download-file)

##### [Java File Separator vs File Path Separator](https://www.baeldung.com/java-file-vs-file-path-separator)

##### [Java File Separator vs File Path Separator](https://www.baeldung.com/java-file-vs-file-path-separator)

##### [Compare the Content of Two Files in Java](https://www.baeldung.com/java-compare-files)

### [**Java IO – Conversions**](https://www.baeldung.com/java-io-conversions)

#### **[Java IO – To and From InputStream](https://www.baeldung.com/java-io-conversions#inputstream)**

Let’s now cover the basic conversions – to and from an *InputStream*:

##### From InputStream

###### **[Java *InputStream* to String](https://www.baeldung.com/convert-input-stream-to-string)\**(popular)\****

###### [Java *InputStream* to Byte Array](https://www.baeldung.com/convert-input-stream-to-array-of-bytes)

###### [Java – Write an *InputStream* to a File](https://www.baeldung.com/convert-input-stream-to-a-file)

**[Java – \*InputStream\* to Reader](https://www.baeldung.com/java-convert-inputstream-to-reader)**

###### [Easy Ways to Write a Java *InputStream* to an *OutputStream*](https://www.baeldung.com/java-inputstream-to-outputstream)

##### To InputStream

###### [Java String to *InputStream*](https://www.baeldung.com/convert-string-to-input-stream)

###### [Java Byte Array to *InputStream*](https://www.baeldung.com/convert-byte-array-to-input-stream)

###### [Java - Convert File to *InputStream*](https://www.baeldung.com/convert-file-to-input-stream)

###### [Java - Reader to *InputStream*](https://www.baeldung.com/java-convert-reader-to-inputstream)

#### **[Java IO – To and From Reader](https://www.baeldung.com/java-io-conversions#reader)**

Next – basic conversions to and from a Java Reader:

##### From Reader

###### [Java – Reader to String](https://www.baeldung.com/java-convert-reader-to-string)

###### [Java – Reader to Byte Array](https://www.baeldung.com/java-convert-reader-to-byte-array)

###### [Java – Reader to *InputStream*](https://www.baeldung.com/java-convert-reader-to-inputstream)

###### [Java – Write a Reader to File](https://www.baeldung.com/java-write-reader-to-file)

##### To Reader

###### [Java – String to Reader](https://www.baeldung.com/java-convert-string-to-reader)

###### [Java – Byte Array to Reader](https://www.baeldung.com/java-convert-byte-array-to-reader)

###### [Java – File to Reader](https://www.baeldung.com/java-convert-file-to-reader)

###### [Java – *InputStream* to Reader](https://www.baeldung.com/java-convert-inputstream-to-reader)

### Java IO APIs

#### **[Guide to Java OutputStream](https://www.baeldung.com/java-outputstream)**

#### [Guide to BufferedReader](https://www.baeldung.com/java-buffered-reader)

### Java NIO APIs

#### [Introduction to the Java NIO2 File API](https://www.baeldung.com/java-nio-2-file-api)

#### [Java IO vs NIO](https://www.baeldung.com/java-io-vs-nio)

#### [Java NIO2 Path API](https://www.baeldung.com/java-nio-2-path)

#### [A Guide to WatchService in Java NIO2](https://www.baeldung.com/java-nio2-watchservice)

#### [Introduction to the Java NIO Selector](https://www.baeldung.com/java-nio-selector)

##  Advanced Java Examples

Let’s have a look at more advanced use cases with Java.

### [Composition, Aggregation, and Association in Java](https://www.baeldung.com/java-composition-aggregation-association)

### [A Guide to Java 9 Modularity](https://www.baeldung.com/java-9-modularity)

### [Introduction to Java Serialization](https://www.baeldung.com/java-serialization)

### [Practical Java Examples of the Big O Notation](https://www.baeldung.com/java-algorithm-complexity)

### [Setting the Java Version in Maven](https://www.baeldung.com/maven-java-version)

### [Hashing a Password in Java](https://www.baeldung.com/java-password-hashing)

### [Different Ways to Capture Java Heap Dumps](https://www.baeldung.com/java-heap-dump-capture)

### [Understanding Memory Leaks in Java](https://www.baeldung.com/java-memory-leaks)

### [How to Replace Many if Statements in Java](https://www.baeldung.com/java-replace-if-statements)

### [Java equals() and hashCode() Contracts](https://www.baeldung.com/java-equals-hashcode-contracts)

### [Guide to System.gc()](https://www.baeldung.com/java-system-gc)

### [A Guide to System.exit()](https://www.baeldung.com/java-system-exit)

### [Adding Shutdown Hooks for JVM Applications](https://www.baeldung.com/jvm-shutdown-hooks)

### **[Do a Simple HTTP Request in Java](https://www.baeldung.com/java-http-request)\**(popular)\****

# Mockito

This tutorial series focuses on the Mockito library – from basic to more advanced use cases, as well as integrating it with other useful testing libraries like JUnit.

## Mockito Basics

### **[Getting Started with Mockito @Mock, @Spy, @Captor and @InjectMocks](https://www.baeldung.com/mockito-annotations)\**(popular)\****

### [Quick Guide to BDDMockito](https://www.baeldung.com/bdd-mockito)

### [Mockito’s Mock Methods](https://www.baeldung.com/mockito-mock-methods)

### **[Mockito ArgumentMatchers](https://www.baeldung.com/mockito-argument-matchers)\**(popular)\****

### **[Mocking Exception Throwing using Mockito](https://www.baeldung.com/mockito-exceptions)\**(popular)\****

### [Mockito’s Java 8 Features](https://www.baeldung.com/mockito-2-java-8)

### [Mockito When/Then Cookbook](https://www.baeldung.com/mockito-behavior)

### [Mockito Verify Cookbook](https://www.baeldung.com/mockito-verify)

## Mockito Advanced

### **[Mocking Void Methods with Mockito](https://www.baeldung.com/mockito-void-methods)\**(popular)\****

### [Mock Final Classes and Methods with Mockito](https://www.baeldung.com/mockito-final)

### [Lazy Verification with Mockito 2](https://www.baeldung.com/mockito-2-lazy-verification)

### **[Testing Callbacks with Mockito](https://www.baeldung.com/mockito-callbacks)\**(popular)\****

### **[Warning: “The type MockitoJUnitRunner is deprecated”](https://www.baeldung.com/mockito-deprecated-mockitojunitrunner)\**(popular)\****

### **[Kotlin with Mockito](https://www.baeldung.com/kotlin-mockito)\**(popular)\****

### **[Mocking Static Methods With Mockito](https://www.baeldung.com/mockito-mock-static-methods)\**(popular)\****

### **[Mockito – Using Spies](https://www.baeldung.com/mockito-spy)\**(popular)\****

### **[Using Mockito ArgumentCaptor](https://www.baeldung.com/mockito-argumentcaptor)\**(popular)\****

## Mockito Integration With Other Libraries

### [Injecting Mockito Mocks into Spring Beans](https://www.baeldung.com/injecting-mocks-in-spring)

### **[Mockito.mock() vs @Mock vs @MockBean](https://www.baeldung.com/java-spring-mockito-mock-mockbean)\**(popular)\****

### **[Mocking a RestTemplate in Spring](https://www.baeldung.com/spring-mock-rest-template)\**(popular)\****

### **[Mockito and JUnit 5 – Using ExtendWith](https://www.baeldung.com/mockito-junit-5-extension)\**(popular)\****

### **[Testing an Abstract Class With JUnit](https://www.baeldung.com/junit-test-abstract-class)\**(popular)\****

### [Mockito vs EasyMock vs JMockit](https://www.baeldung.com/mockito-vs-easymock-vs-jmockit)

### [Mocking of Private Methods Using PowerMock](https://www.baeldung.com/powermock-private-method)

### [Introduction to PowerMock](https://www.baeldung.com/intro-to-powermock)

# JUnit

## JUnit - Testing Basics

### **[A Guide to JUnit 5](https://www.baeldung.com/junit-5)\**(popular)\****

### [JUnit 5 @Test Annotation](https://www.baeldung.com/junit-5-test-annotation)

### [@Before vs @BeforeClass vs @BeforeEach vs @BeforeAll](https://www.baeldung.com/junit-before-beforeclass-beforeeach-beforeall)

### [Assert an Exception is Thrown in JUnit 4 and 5](https://www.baeldung.com/junit-assert-exception)

### [Assertions in JUnit 4 and JUnit 5](https://www.baeldung.com/junit-assertions)

## JUnit - Integration with Other Libraries

### [The SpringJUnitConfig and SpringJUnitWebConfig Annotations in Spring 5](https://www.baeldung.com/spring-5-junit-config)

### **[Mockito and JUnit 5 – Using ExtendWith](https://www.baeldung.com/mockito-junit-5-extension)\**(popular)\****

### [JUnit 5 for Kotlin Developers](https://www.baeldung.com/junit-5-kotlin)

### [A Quick JUnit vs TestNG Comparison](https://www.baeldung.com/junit-vs-testng)

### [Guide to Selenium with JUnit / TestNG](https://www.baeldung.com/java-selenium-with-junit-and-testng)

## JUnit - Advanced Topics

### [The Order of Tests in JUnit](https://www.baeldung.com/junit-5-test-order)

### [Custom JUnit 4 Test Runners](https://www.baeldung.com/junit-4-custom-runners)

### [JUnit5 @RunWith](https://www.baeldung.com/junit-5-runwith)

### [Inject Parameters into JUnit Jupiter Unit Tests](https://www.baeldung.com/junit-5-parameters)

### [Migrating from JUnit 4 to JUnit 5](https://www.baeldung.com/junit-5-migration)

### [A Guide to JUnit 5 Extensions](https://www.baeldung.com/junit-5-extensions)

### [JUnit5 Programmatic Extension Registration with @RegisterExtension](https://www.baeldung.com/junit-5-registerextension-annotation)

### [Guide to Dynamic Tests in Junit 5](https://www.baeldung.com/junit5-dynamic-tests)

### [A Guide to @RepeatedTest in Junit 5](https://www.baeldung.com/junit-5-repeated-test)

# Git
### [Git for Beginners: The Definitive Practical Guide](https://www.baeldung.com/git-guide)

A step-by-step guide to Git, this article discusses the most commonly used commands. Learn the basics, the Git workflow, branching and even some advanced techniques like modifying your commit history.

## [Understanding Git’s fork and clone Operations](https://www.baeldung.com/git-fork-vs-clone)

Find out the differences between two seemingly similar Git operations – fork and clone.

### [How to Fix Git “Refusing to Merge Unrelated Histories”](https://www.baeldung.com/git-merge-unrelated-histories-error)

Learn how to fix the “Refusing to Merge Unrelated Histories” error in Git.

### [Guide to Undo a git rebase](https://www.baeldung.com/git-undo-rebase)

Learn about two popular techniques to undo a git rebase operation

### [Find the Differences Between Two Git Branches](https://www.baeldung.com/git-branches-differences)

Learn methods of finding the differences between Git branches on Linux.

### [Modify a Specified Commit in Git](https://www.baeldung.com/git-modify-commit)

A quick and practical guide to modifying a git commit.

### [How to Modify Git Commit Messages](https://www.baeldung.com/git-commit-message-changes)

Learn how to modify Git commit messages.

### [Remove File From Git Repository Without Deleting It Locally](https://www.baeldung.com/git-remove-file-without-deleting-it)

Learn how to remove a file or directory from a Git repository but keep its local copy

### [Difference Between git merge and rebase](https://www.baeldung.com/git-merge-vs-rebase)

Explore the basic difference between git merge and git rebase which every developer should know while working with git VCS.

### [How to Get the Current Branch Name in Git](https://www.baeldung.com/git-current-branch-name)

Learn how to get the Git branch name we’re currently working on

### [Delete a Git Branch Locally and Remotely](https://www.baeldung.com/git-delete-branch-locally-remotely)

Learn how to delete Git branches

### [Move Existing, Uncommitted Work to a New Branch in Git](https://www.baeldung.com/git-move-uncommitted-work-to-new-branch)

Learn a couple of quick ways to move uncommitted changes to a new Git branch

### [How to Discard Unstaged Changes in Git](https://www.baeldung.com/git-discard-unstaged-changes)

Learn how to remove files that are not staged for commit to clean up our working directory.

### [Difference Between assume-unchanged and skip-worktree in Git](https://www.baeldung.com/git-assume-unchanged-skip-worktree)

Learn the differences between the —*assume-unchanged* and —*skip-worktree* options of Git’s *update-index* command.

### [How to Recover a Dropped Stash in Git](https://www.baeldung.com/git-recover-dropped-stash)

The git stash can be used to store changes temporarily. If we drop these changes, we can still get them back again. We look at how to re-apply a stashed change, and how to find it.

### [Remove a Large File from Commit History in Git](https://www.baeldung.com/git-remove-file-commit-history)

Learn how to remove large files from the commit history of a git repository using various tools.

### [Removing Tracked Files With .gitignore](https://www.baeldung.com/git-remove-tracked-files-gitignore)

Learn how to remove currently tracked files from a Git index after adding them to the *.gitignore* file.

### [Undo and Revert Commits in Git](https://www.baeldung.com/git-revert-commit)

Learn the safest way to undo or revert commits in a Git repository.

### [Understanding Detached HEAD in Git](https://www.baeldung.com/git-detached-head)

Explore what a detached HEAD in Git is and how it works.

### [Hosting a Maven Repository on GitHub](https://www.baeldung.com/maven-repo-github)

A quick and practical guide to hosting Maven repositories on GitHub.

### [A Guide to JGit](https://www.baeldung.com/jgit)

Learn the basics of using JGit – a Git version control written in Java.

### [Introduction to EGit](https://www.baeldung.com/egit)

Discover the EGit tool for Eclipse.

### [Injecting Git Information Into Spring](https://www.baeldung.com/spring-git-information)

Quick and practical guide to retrieving and injecting Git information using Spring and Maven

# IDEA

### [What Is the .idea Directory?](https://www.baeldung.com/intellij-idea-directory)

IntelliJ IDEA stores its settings in the .idea directory. We look at what’s stored here and whether to share the contents via source control.

### [How to Set Up Environment Variables in IntelliJ IDEA](https://www.baeldung.com/intellij-idea-environment-variables)

A quick and practical guide to setting up environment variables with Intellij IDEA.

### [How to Permanently Enable Line Numbers in IntelliJ IDEA?](https://www.baeldung.com/intellij-idea-activate-line-numbers)

A quick and practical guide on enabling line numbers in IntelliJ IDEA.

### [Debugging an Application Running in Docker With IntelliJ IDEA](https://www.baeldung.com/docker-debug-app-with-intellij)

Learn different configuration options we can use to debug a dockerized application in IntelliJ

### [Common Shortcuts in IntelliJ IDEA](https://www.baeldung.com/intellij-idea-shortcuts)

A quick and practical guide to Intellij IDEA shortcuts.

### [Writing IntelliJ IDEA Plugins Using Gradle](https://www.baeldung.com/intellij-idea-plugins-gradle)

Learn how to write your own IntelliJ plugin using Gradle.

### [Remote Debugging with IntelliJ IDEA](https://www.baeldung.com/intellij-remote-debugging)

Learn how to debug a remote Java process using IntelliJ

### [An Introduction to Refactoring with IntelliJ IDEA](https://www.baeldung.com/intellij-refactoring)

Learn a few helpful tips for working more productively with IntelliJ.

### [Adding a Copyright License Header for Java Source Files in IntelliJ IDEA](https://www.baeldung.com/intellij-copyright-license-header)

Learn how to configure IntelliJ IDEA to add license headers automatically to your project files.

### [Writing IntelliJ IDEA Plugins](https://www.baeldung.com/intellij-new-custom-plugin)

Learn how to write your own plugins for IntelliJ IDEA

### [Java Static Analysis Tools in Eclipse and IntelliJ IDEA](https://www.baeldung.com/java-static-analysis-tools)

Learn how to use PMD and Cobertura – static analysis tools for Java – and how they integrate with Eclipse and IntelliJ IDEA.

# JavaWeb

### [>> Set a Parameter in an HttpServletRequest in Java](https://www.baeldung.com/java-servlet-request-set-parameter)

### [>> Reading a JSP Variable From JavaScript](https://www.baeldung.com/java-jsp-read-variable-js)

### [>> Java IllegalStateException: “getInputStream() has already been called for this request”](https://www.baeldung.com/java-servletrequest-illegalstateexception)

### [>> Validating IPv4 Address in Java](https://www.baeldung.com/java-validate-ipv4-address)

### [>> Limiting the Requests per Second With WebClient](https://www.baeldung.com/spring-webclient-limit-requests-per-second)

### [>> Difference Between WAR and EAR Files](https://www.baeldung.com/war-vs-ear-files)

# Jackson JSON Tutorial

**This tutorial** illustrates the most common [**Jackson 2**](https://github.com/FasterXML/jackson) tasks, problems and solutions while marshalling and unmarshalling JSON.

## **Basic Jackson Marshalling**

### **[Jackson Annotation Examples](https://www.baeldung.com/jackson-annotations)\**(popular)\****

### **[Intro to the Jackson ObjectMapper](https://www.baeldung.com/jackson-object-mapper-tutorial)\**(popular)\****

### [Jackson Ignore Properties on Marshalling](https://www.baeldung.com/jackson-ignore-properties-on-serialization)

### **[Ignore Null Fields with Jackson](https://www.baeldung.com/jackson-ignore-null-fields)\**(popular)\****

### [Jackson - Change Name of Field](https://www.baeldung.com/jackson-name-of-property)

### [Jackson – Decide What Fields Get Serialized/Deserialized](https://www.baeldung.com/jackson-field-serializable-deserializable-or-not)

### [XML Serialization and Deserialization with Jackson](https://www.baeldung.com/jackson-xml-serialization-and-deserialization)

### [Jackson – Marshall String to JsonNode](https://www.baeldung.com/jackson-json-to-jsonnode)

### [Using Optional with Jackson](https://www.baeldung.com/jackson-optional)

## Basic Jackson Unmarshalling

### [Jackson - Unmarshalling JSON with Unknown Properties](https://www.baeldung.com/jackson-deserialize-json-unknown-properties)

### [Jackson vs Gson](https://www.baeldung.com/jackson-vs-gson)

## Advanced Jackson Marshalling

### [Map Serialization and Deserialization with Jackson](https://www.baeldung.com/jackson-map)

### [Serialize Only Fields that meet a Custom Criteria with Jackson](https://www.baeldung.com/jackson-serialize-field-custom-criteria)

### [How To Serialize and Deserialize Enums with Jackson](https://www.baeldung.com/jackson-serialize-enums)

### [Jackson - JsonMappingException (No serializer found for class)](https://www.baeldung.com/jackson-jsonmappingexception)

### [Jackson Date](https://www.baeldung.com/jackson-serialize-dates)

### [Jackson JSON Views](https://www.baeldung.com/jackson-json-view-annotation)

### [Jackson Exceptions – Problems and Solutions](https://www.baeldung.com/jackson-exception)

### [Convert XML to JSON Using Jackson](https://www.baeldung.com/jackson-convert-xml-json)

### [Serialize and Deserialize Booleans as Integers With Jackson](https://www.baeldung.com/jackson-booleans-as-integers)

## Advanced Jackson Unmarshalling

### [Jackson - Unmarshall to Collection/Array](https://www.baeldung.com/jackson-collection-array)

### [Getting Started with Custom Deserialization in Jackson](https://www.baeldung.com/jackson-deserialization)

## Advanced Jackson Usage

### [Compare Two JSON Objects with Jackson](https://www.baeldung.com/jackson-compare-two-json-objects)

### [Jackson – Bidirectional Relationships](https://www.baeldung.com/jackson-bidirectional-relationships-and-infinite-recursion)

### [Working with Tree Model Nodes in Jackson](https://www.baeldung.com/jackson-json-node-tree-model)

### [More Jackson Annotations](https://www.baeldung.com/jackson-advanced-annotations)

### [Inheritance with Jackson](https://www.baeldung.com/jackson-inheritance)

### [Mapping Nested Values with Jackson](https://www.baeldung.com/jackson-nested-values)

### [Guide to @JsonFormat in Jackson](https://www.baeldung.com/jackson-jsonformat)

### [Mapping a Dynamic JSON Object with Jackson](https://www.baeldung.com/jackson-mapping-dynamic-object)

### [Spring Boot: Customize the Jackson ObjectMapper](https://www.baeldung.com/spring-boot-customize-jackson-objectmapper)





