# 全局配置说明

如果需要配置能在所有项目中生效，则应从 File | Other Settings | Default Settings 进入配置，而不是通过 Preferences 菜单进入（Preferences中的配置只对当前项目生效）。

# 代码签名配置

Editor | File and Code Templates | Includes | File Header ，设置默认的 Java 代码签名

```
/**
 * @author zhenyu
 * Created on ${YEAR}-${MONTH}-${DAY}
 */
```

# IDEA JVM 内存配置

修改 IDEA 启动的 JVM 配置，菜单 Help | Edit Custom VM Options...，会打开文件 idea.vmoptions。替换其中的一些内存配置参数。

```
-Xms1g
-Xmx4g
-XX:ReservedCodeCacheSize=1g
```

# 编译堆内存

Preferences | Build, Execution, Deployment | Compiler

Build process heap size (Mbytes): 1400

# Java8 parameters设置

Preferences | Build, Execution, Deployment | Compiler | Java Compiler | Javac Options | Additional Command line parameters

填上下面这个

-parameters

此项如果不设置，某些依赖参数名的 AOP 在 IDEA 下会不起作用

# properties 文件转义配置

勾选 Preferences | Editor | File encodings下把 transparent native-to-ascii conversion

# Inspection 配置

IntelliJ Idea 可以显示出代码里潜在的问题，在开发过程中要重视这些提示。默认的 Inspection 配置会报告一些不太重要的问题为 Warning，导入以下配置后会把这些 Warning 去掉。

Editor -> Inspection -> Profile -> Import Profile

# Code Formatter

Preferences | Other Settings | Code Formatter，点选 "Use the Eclipse code formatter"， 然后导入 java-formatter.xml

# Import Order

在 Preferences | Editor | Code Style | Java | Imports 中进行如下设置

## General

Class count to use import with '*': 999
Names count to use static import with '*': 9999

## Import Layout

勾选Layout static imports separately

import static all other imports
<blank line>
import java.*
<blank line>
import javax.*
<blank line>
import org.*
<blank line>
import com.*
<blank line>
import all other imports


