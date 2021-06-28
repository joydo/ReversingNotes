Binary Reversing Engineering Summary
===

# Basics

## 编程语言要求

### 基础底层研究

* C++ & C & 汇编

  * C++(Ver.03,11,14,17,甚至20)

    * C++实用指南(https://goalkicker.com/CPlusPlusBook/)

    * C++ Modern Feature(新版本特性)(https://github.com/AnthonyCalandra/modern-cpp-features)

    * Modern C++ Tutorial(新版本使用指南中文版)(https://github.com/changkun/modern-cpp-tutorial/blob/master/README-zh-cn.md)

    * 高级C++研究课题(论文，编译器，汇编器等，着重C++)(https://github.com/MattPD/cpplinks)

    * C++ ABI Design(Itanium版本)(https://itanium-cxx-abi.github.io/cxx-abi/abi.html)

      备注: 在逆向binary相关文件时，关于C++的对象layout,vtable layout以及member函数恢复都起到了非常重要的参考作用，尤其是定位指针offset时，应用于Android SO，Linux SO等

    * C++ 标准化(语言特性，设计，模式分析)(https://timsong-cpp.github.io/cppwp/)

      备注: 想要了解的一切关于C++的知识都囊括在这个目录里，慎用，这个是真的语言设计

    * C++ Core Guidelines(C++编码的规范要求)(http://isocpp.github.io/CppCoreGuidelines/CppCoreGuidelines)

      备注: C++ ISO 委员会极力推荐的编码规范

  * C(Ver.99,89,11)

    * C标准化(语言特性，设计，模式分析)(https://stackoverflow.com/questions/81656/where-do-i-find-the-current-c-or-c-standard-documents)
    * ANSI C89(语言特性，设计，模式分析)(http://www.bsb.me.uk/ansi-c/ansi-c-one-file)
    * GNU C 参考手册(https://www.gnu.org/software/gnu-c-manual/gnu-c-manual.html)
    * C ABI Design(System V版本)
      * https://github.com/hjl-tools/x86-psABI/wiki/X86-psABI

  * 汇编(ARM,Intel_x86_64，x86)

    * ARMv8(https://developer.arm.com/documentation/ddi0487/latest/)
    * ARMv7(https://developer.arm.com/documentation/ddi0406/latest)
    * Intel(x86 &x86_64,该目录下囊括了许多关于Intel的开发指南，谨慎选择对应开发手册)(https://software.intel.com/content/www/us/en/develop/articles/intel-sdm.html)
    * Intel汇编指南图画版(该版本以table形式分析相关指令编码)(http://ref.x86asm.net/)
    * ARM ABI Design(C&C++,该目录针对不同的文件，给出了对应的arm abi设计方案，查阅时，谨慎使用)(https://developer.arm.com/architectures/system-architectures/software-standards/abi)
    * ARM8.3  PAC(Pointer Authentication Code)(新增的汇编指令目前大批量的用于iPhoneX以上版本，用于加强程序指针的保护，具体讨论参考Platform-IOS)
      * https://www.qualcomm.com/media/documents/files/whitepaper-pointer-authentication-on-armv8-3.pdf
    * x86 Calling Conventions(https://en.wikipedia.org/wiki/X86_calling_conventions)
    * ARM Calling Conventions(https://developer.arm.com/documentation/ihi0042/latest/)
    * ARMv64 Calling Conventions(https://developer.arm.com/documentation/ihi0055/latest/)

### Application 高级语言研究

* ObjC & Swift(For IOS)

     备注: 目前ObjC 用于IOS开发的越来越少，大部分软件更新是基于向下兼容保留了相关功能代码，目前用于IOS开发的Swift版本较多

  * ObjC语言学习一(https://goalkicker.com/ObjectiveCBook/)
  * ObjC语言学习二(https://microsoft.github.io/objc-guide/)
  * ObjC Runtime学习(ObjC核心，Class，property，id等概念的设计以及与C之间的交互设计)(https://github.com/0xxd0/objc4)
  * ObjC objc_msgSend功能拆解分析(arm64版本，arm32可类推)(https://www.mikeash.com/pyblog/friday-qa-2017-06-30-dissecting-objc_msgsend-on-arm64.html)
  * ObjC objc_msgSend prototype设计分析(https://www.mikeash.com/pyblog/objc_msgsends-new-prototype.html)
  * swift语言学习一(https://goalkicker.com/SwiftBook/)
  * swift语言学习二(官方指南)(https://docs.swift.org/swift-book/LanguageGuide/TheBasics.html)
  * swift语言学习三(官方设计文档)(https://docs.swift.org/swift-book/ReferenceManual/AboutTheLanguageReference.html)
  * swift编译器设计论坛(https://forums.swift.org/)
  * swift IOS 开发文档(苹果官方版)(参考对应XCode文档)(https://developer.apple.com/documentation/swift)

* Kotlin & Java(For Android)

  * Java语言学习(https://goalkicker.com/JavaBook/)
  * Kotlin语言学习一(官方资料)(注意该语言很多特性与Swift重合，都是源于C++的核心开发)(https://kotlinlang.org/docs/home.html)
  * Kotlin语言学习二)(Android版本)(https://developer.android.com/kotlin/learn)
  * Android API 参考文档(java&kotlin)(https://developer.android.com/reference)

* Go(For Linux)

  * Go Touring学习一(https://tour.golang.org/welcome/)
  * Go Tutorial学习二(https://golang.org/doc/tutorial/getting-started)

* Javascript(For Web)

  * Javascript学习一(https://goalkicker.com/JavaScriptBook/)

  * Javascript学习二(ECMA262参考)(https://262.ecma-international.org/12.0/)

    备注: 该参考文件主要用于指导Javascript编译器设计，因此该文档有很大参考价值，在设计反混淆器设计方面

* Python(For ...)

  * Python学习一(https://goalkicker.com/PythonBook/)

  ​    备注: Python2&3学习资料太多，网上也是一堆学习资料，不清楚的可以Surfing一下。



## 英语水平要求

​				口语，听力基本没啥要求，但是Reading一定要达标哦，至少也得是CET6以上的水准吧，虽然CET6也是很水的存在，因为这篇文章涉及到的资料90%都是英文资料呢，别怪我没提醒你哦！！

## 能力要求

​			我是通信专业毕业，说实话大学期间也就学了点加减密与PKI的相关概念，原本是想从事C++开发的，后来误打误撞干起了逆向这个活，嗯，怎么说呢，这类活钻研精神是要有的，因为接触的很多代码都是偏底层，而且很多都需要结合软件涉及理念才能猜出来当时设计者的部分意图。不要害怕入门，看起来很难(的确深入进去很难)，但是乐趣还是有的，而且能提升自身的能力，因此愿意进来的就好好干。但是还是要泼冷水先，没有钻研精神， 学个皮毛的，慎入，真的没啥意思。

# Platforms

​		本人从事Mobile移动逆向比较多，因此着重介绍下，Linux和MacOSX也会附带介绍



> ​	移动端OWASP撰写的APP Security安全指南:
>
>  *  (移动端安全分析总览)(https://github.com/OWASP/owasp-mstg/blob/master/Document/0x04b-Mobile-App-Security-Testing.md)
>  *  Android平台安全总览(https://github.com/OWASP/owasp-mstg/blob/master/Document/0x05a-Platform-Overview.md)
>  *  IOS平台安全总览(https://github.com/OWASP/owasp-mstg/blob/master/Document/0x06a-Platform-Overview.md)

> ​	***备注: 关于移动端安全审计，建议时间充沛的可以将OWASP(https://github.com/OWASP/owasp-mstg)该目录下所有文章都看看，会让你对整个移动端安全有个大体的认识和熟悉***

## Android

***备注：可能部分内容会和Linux逆向重合，但是不影响知识总结***

### 介绍

​	要进入这个领域，必要的正向开发知识是要有的，了解开发者正向开发思维与Scheme，才能更好的逆向出来相关的设计思路与系统框架设计，包括算法设计等

​	进入Android逆向之前，你需要搞清楚几个事情:

> * ***什么是Android？***
> * ***什么是Android APK？ 什么是Android APP Bundle?(2021版本)***
> * ***Android APP 的Activity LifeCycle(生命周期)？***
> * ***Android App主程序及extension？***
> * ***Android Studio的使用***
> * ***Android APP 可获取的设备权限？***
> * ***什么是Java反编译，什么是smali？***
> * ***Android ART vs Android Dalvik?***
> * ***Linux ELF so加载流程***
> * ***Online 数据交互(流量定位，数据流格式，加减密)***
> * ***Offline数据处理(核心处理算法，数据流deserialization)***
> * ***Android 软件加壳保护？一代壳，二代壳？***

### 入门资料

* Android开发手册入门指南(https://goalkicker.com/AndroidBook/)

* Android Internal分析(http://newandroidbook.com/)

* Android Dalvik 字节码设计参考(https://source.android.com/devices/tech/dalvik/dalvik-bytecode.html)

* Android .dex格式说明(https://source.android.com/devices/tech/dalvik/dex-format.html)

* Smali 相关(动态调试Android主程序方案)

  * Smali Registers参考(https://github.com/JesusFreke/smali/wiki/Registers)
  * Smali TypesMethodsAndFields(类型与方法)(https://github.com/JesusFreke/smali/wiki/TypesMethodsAndFields)

* OWASP 撰写的Android逆向入门指南(https://github.com/OWASP/owasp-mstg/blob/master/Document/0x05c-Reverse-Engineering-and-Tampering.md)

* oat internal内部结构说明(内容可能有点老，但是structure变化不大)(http://romainthomas.fr/oat/)

  * Android ART分析

  ​	==ART==![](https://github.com/joydo/ReversingNotes/blob/main/secretpdfs/Android_ART_Internal.jpg)

  * https://www.blackhat.com/docs/asia-15/materials/asia-15-Sabanal-Hiding-Behind-ART-wp.pdf
  * http://newandroidbook.com/files/ArtOfDalvik.pdf

* Android 加壳保护机制分析文章

  * 腾讯乐固加壳分析(https://github.com/quarkslab/legu_unpacker_2019)
  * Android App加固原理与技术历程入门级介绍(https://bbs.pediy.com/thread-260124.htm)
  * 常见App加固厂商脱壳方法分析(部分信息比较老了，谨慎参考)(https://github.com/JnuSimba/AndroidSecNotes/blob/master/Android%20%E8%B0%83%E8%AF%95%E5%B7%A5%E5%85%B7/%E5%B8%B8%E8%A7%81app%E5%8A%A0%E5%9B%BA%E5%8E%82%E5%95%86%E8%84%B1%E5%A3%B3%E6%96%B9%E6%B3%95.md)  

### 工具使用

#### 反编译相关

* Jeb 软件(apk,dex反编译)(https://www.pnfsoftware.com/jeb/)
* JADX(Dex to Java Decompiler)(开源软件)(https://github.com/skylot/jadx)
* smali/baksmali(dex文件的汇编与反汇编器)(https://github.com/JesusFreke/smali)
* ApkTool(https://ibotpeaches.github.io/Apktool/)
* ida pro(分析jni支持的so文件实现逻辑)(主要处理C++&C逻辑)
* Java ByteCode Viewer(Android APK Reverse Engineering Suite)(https://github.com/Konloch/bytecode-viewer)

#### Hooking相关

* Xposed Framework(久负盛名之一)(https://github.com/rovo89/Xposed)
* Frida Framework(久负盛名之二，跨平台的Hooking框架)(https://github.com/frida/frida)
* EdXposed Framework(https://github.com/ElderDrivers/EdXposed)
* LSPosed Framework(https://github.com/LSPosed/LSPosed)
* Android ART Hooking Framework 一(https://github.com/RikkaApps/Riru)
* 二次打包工具LSPatch(https://github.com/LSPosed/LSPatch)
* Android ART Hooking Framework 二(https://github.com/PAGalaxyLab/YAHFA)

#### 调试相关

***备注：新版本Android在逆向过程中，大多数情况下调试主程序比较困难，即使借助IDA或 Smali字节码调试也不是很理想，因此大多数情况下会选择Hooking或者tracing处理与分析相关逻辑***



#### 其他常用工具或者解析库

* Magisk(Android定制化工具，RootKits)(https://github.com/topjohnwu/Magisk)
* Jtrace(增强版的Android Tracing工具)(http://newandroidbook.com/tools/jtrace.html)
* Dextra(dex提取工具)(local运行)(http://newandroidbook.com/tools/dextra.html)
* Android Debug Bridge(adb相关组件程序分析)(https://developer.android.com/studio/releases/platform-tools)
* Android Malware System(恶意文件apk评分系统，需要整合该framework,做参考)(https://github.com/quark-engine/quark-engine)
* 解析二进制文件格式(通用性)(https://lief.quarkslab.com/, https://github.com/lief-project/LIEF)
* Android Application Identifier for Packers, Protectors, Obfuscators and Oddities(加壳，混淆的识别)(https://github.com/rednaga/APKiD)

## IOS&MACOSX

### 介绍

​		因为本人大多数情况在研究IOS相关逆向任务，因此这块篇幅会相对较长，同时会涉及到内核分析，因此谨慎参考，在进入IOS逆向之前，你需要了解如下信息:

> * ***什么是IOS***
> * ***什么是IOS IPA文件，什么是Plist文件***
> * ***MachO文件***
> * ***IOS APP LifeCycle？***
> * ***IOS主程序结构及Framework设计？***
> * ***Xcode的使用***
> * ***IOS APP 授权机制***
> * ***IOS APP 签名算法及证书***
> * ***ObjC语言的学习，ObjC Runtime的分析与学习***
> * ***App 热备份，热Patch原理***
> * ***Swift语言的学习***
> * ***ObjC 反编译程序***
> * ***Swift(强静态类型语言，深受C++印象)反编译程序***
> * ***IOS APP调试(源码&非源码)***
> * ***Online数据(同Android)***
> * ***Offline数据(同Android)***

### 入门资料

* IOS入门开发指南一(https://goalkicker.com/iOSBook/)

* IOS入门开发指南二(官方)(https://developer.apple.com/tutorials/app-dev-training/)

* IOS入门开发指南三(raywenderlich版本,质量比较高)(https://www.raywenderlich.com/ios/videos)

* IOS wwdc2021开发者大会sessions集锦(主打swift开发)(https://developer.apple.com/wwdc21/)

* Swift 编程指南(https://www.objc.io/)

* MachO文件(*OS平台可执行文件,官方说明)(https://github.com/aidansteele/osx-abi-macho-file-format-reference/blob/master/Mach-O_File_Format.pdf)

* IOS NSOperation vs Grand Central Dispatch(IOS平台并行编程框架分析)(https://stackoverflow.com/questions/10373331/nsoperation-vs-grand-central-dispatch)

* Objc Automatic Reference Counting(ARC机制)

  * https://clang.llvm.org/docs/AutomaticReferenceCounting.html?highlight=class#objective-c-automatic-reference-counting-arc (clang实现机制分析)
  * https://opensource.apple.com/source/lldb/lldb-159/llvm/tools/clang/docs/AutomaticReferenceCounting.html(官方解读篇)

* Objc Block/Closure

  * https://clang.llvm.org/docs/Block-ABI-Apple.html (clang的实现机制分析)
  * http://www.swiftyper.com/2016/12/16/debuging-objective-c-blocks-in-lldb/ (深入理解 Block 的内存模型)
  * https://maniacdev.com/2013/11/tutorial-an-in-depth-guide-to-objective-c-block-debugging (Objc Block Debug分析)

* Objc Delegate机制

  * Delegate与Data Source(官方文档)(https://developer.apple.com/library/archive/documentation/General/Conceptual/CocoaEncyclopedia/DelegatesandDataSources/DelegatesandDataSources.html)
  * Delegate机制的StackOverflow解释(https://stackoverflow.com/questions/2534094/what-is-a-delegate-in-objective-cs-iphone-development)
  * 如何使用Delegate机制(https://stackoverflow.com/questions/626898/how-do-i-create-delegates-in-objective-c)

* ios Code sign(代码签名分析)

  * Codesign 机制分析一(objcio分析版)(https://www.objc.io/issues/17-security/inside-code-signing/)
  * Codesign机制分析二(官方解读版)(https://developer.apple.com/support/code-signing/)
  * 如何绕过IOS代码签名(内容有点老，谨慎参考)(http://www.saurik.com/id/8)
  * dyld detailed 内部分析(http://www.newosxbook.com/articles/CodeSigning.pdf)

* ***IOS Jailbreak 百科全书***(https://www.theiphonewiki.com/wiki/Jailbreak)

* 简易版Swift逆向入门指南(由于Swift的ABI这几年一直在更迭，因此仅作为参考，需要结合sourcecode重点分析)(https://github.com/iOS-Reverse-Engineering-Dev/Swift-Apps-Reverse-Engineering/blob/master/Reverse%20Engineering%20Swift%20Applications.pdf)

  备注: Swift语言深受C++语言影响，因此熟练C++的应该对这门语言会比较喜欢，鉴于C++委员会很多没支持的，Swift都做了大胆尝试)

* OWASP撰写的IOS逆向入门指南(https://github.com/OWASP/owasp-mstg/blob/master/Document/0x06c-Reverse-Engineering-and-Tampering.md)

* IOS Entitlements(授权机制)

  * (授权机制讲解一)https://developer.apple.com/library/archive/documentation/Miscellaneous/Reference/EntitlementKeyReference/Chapters/AboutEntitlements.html
  * (授权机制讲解二)https://developer.apple.com/documentation/bundleresources/entitlements?language=objc
  * osx/ios entitlements数据库(http://newosxbook.com/ent.jl)

* 解密Maocsx DMG文件(http://newosxbook.com/DMG.html)

* GCD 模式内部原理分析(http://newosxbook.com/articles/GCD.html?n)

#### *深入版*

> * IOS 内核dyld_shared_cache入门介绍(https://iphonedev.wiki/index.php/Dyld_shared_cache)
>
> * IOS 系统(mach kernel入门介绍，内容较老，不过总体知识点可看)(http://newosxbook.com/MOXiI.pdf)
>
> * IOS 三卷宗(有条件的可以购买观看，iOS kernel以及iOS kernel security)
>
>   * **Volume I - User Mode**
>   * **Volume II - Kernel Mode**
>   * **Volume III - Security & Insecurity**
>
>   备注:(购买链接)http://newosxbook.com/index.php
>
> * IOS kernel IPC 机制分析
>
>   * Auditing and Exploiting Apple IPC(https://thecyberwire.com/events/docs/IanBeer_JSS_Slides.pdf)
>   * Inter-Process Communication(https://nshipster.com/inter-process-communication/)
>   * xpc vs socket-based IPC 机制分析(访问控制与用户空间模式)(https://developer.apple.com/forums/thread/74498)
>
> * IOS ARM PAC mode分析
>
>   * iOS12 kernelcache laundering(PAC模式初探)(https://www.synacktiv.com/en/publications/ios12-kernelcache-laundering.html)
>   * iPhoneXS PAC模式分析(https://googleprojectzero.blogspot.com/2019/02/examining-pointer-authentication-on.html)
>   * PAC 模式分析(https://www.usenix.org/system/files/sec19fall_liljestrand_prepub.pdf)
>   * A study for PAC mode(https://bazad.github.io/presentations/MOSEC-2019-A-study-in-PAC.pdf)

> ***优秀的blog和学习资源列表***
>
> * Siguza的iOS学习资源整合(https://github.com/Siguza/ios-resources)
> * google zero blog 平台(主要关注IOS板块)(https://googleprojectzero.blogspot.com/)
> * Brandon Azad Github主页(https://github.com/bazad)
> * Jonathan Levin的个人网站(http://newosxbook.com/index.php)
> * Saurik 的个人项目网站(https://git.saurik.com/)

备注说明: IOS&MACOSX相关的CVE分析以及exploits暂时没有放入相关整合中，部分信息不好做归纳，有兴趣的可以私聊或者自行查验，Kernel Exploits属于高级研究了，目前我也是刚入门而已，有兴趣的可以一起学习

### 工具使用

#### 反编译相关

* class-dump(https://github.com/nygard/class-dump)
* An improved nm + Objective-C & Swift class-dump
  * https://github.com/DerekSelander/dsdump
  * https://derekselander.github.io/dsdump/
* 命令行解析macho相关文件(Jtool)(http://www.newosxbook.com/tools/jtool.html)
* 命令行分析kernelcache(Joker)(http://newosxbook.com/tools/joker.html)
* xpc snooping 功能for macosx和iOS(XPoCe)(http://newosxbook.com/tools/XPoCe.html)
* 命令行签名工具(ldid)(https://git.saurik.com/ldid.git)
* cycript命令行Javascript和Objc交互分析，越狱状态下分析(http://www.cycript.org/)
* cydia package installer 越狱插件store(目前有很多替换方案，可以网上找找)(https://git.saurik.com/cydia.git)
* 苹果官方部分软件(LLDB,codesign,otool等)
* iOS ipa砸壳软件
  * fouldecrypt(https://github.com/NyaMisty/fouldecrypt)
  * flexdecrypt(https://github.com/JohnCoates/flexdecrypt)
  * bagbak(https://github.com/ChiChou/bagbak)
* grapefruit(IOS Runtime Application Instruments)(https://github.com/ChiChou/grapefruit)
* futurerestore(iOS降级使用)(https://github.com/tihmstar/futurerestore)
* tsschecker(ios降级使用)(https://github.com/tihmstar/tsschecker)
* **IDA pro(同样的本人必备的工具),不建议使用Ghidra调试分析C项目，至少decompiler 方面做的不如IDA，不过decompiler的部分思想可以用一下，具体可参考Senior Reverse Engineering模块**

#### Hooking相关

* Frida框架，参考Android(跨平台)
* cydiasubstrate(http://www.cydiasubstrate.com/)
* macho inject
  * https://github.com/scen/osxinj
  * https://github.com/LIJI32/MIP
* Dobby(跨平台)(https://github.com/jmpews/Dobby/)
* substitute(https://github.com/sbingner/substitute)
* AltStore for alternative app store(https://github.com/rileytestut/AltStore)

#### 调试相关

* LLDB脚本插件

  * https://github.com/DerekSelander/LLDB

    (备注:该作者编著了一本关于调试的相关技巧的书，有想法的可以阅读一下:https://www.raywenderlich.com/books/advanced-apple-debugging-reverse-engineering)

  * https://github.com/4ch12dy/xia0LLDB

  * https://github.com/facebook/chisel

* IDA(构建方法比较繁琐且复杂，如果习惯界面调试的，可以看看或者Xcode模式也行)

  * https://www.hex-rays.com/wp-content/uploads/2019/12/ios_debugger_tutorial.pdf
  * https://hex-rays.com/wp-content/static/tutorials/ios_debugger_primer2/ios_debugger_primer2.html

* Dtrace(说实话，这个东西在MacOSX世界里面真的是神器，建议且强烈建议阅读一下相关使用方法)

  * (brendangregg的个人网站，Netflix高级工程师)http://www.brendangregg.com/dtrace.html
  * http://www.dtrace.org/blogs/

#### 其他常用工具及解析库

##### IOS软件保护

> 反调说明:
>
> * (个人总结文档)https://github.com/joydo/ReversingNotes/blob/main/secretpdfs/IOS%E5%8F%8D%E8%B0%83%E6%9C%BA%E5%88%B6%E6%A2%B3%E7%90%86.pdf
> * 反调绕过(https://github.com/jmpews/HookZzModules/tree/master/AntiDebugBypass)

##### 解析库

* LIEF解析可执行文件库(具体参考Android链接)
* Apple Open Source Homepage(https://opensource.apple.com/tarballs/)

***备注: Android&IOS 代码保护(混淆，VM方面会在高级逆向中提及)***



##### 其他工具

* ios./macosx 命令行多功能工具(https://github.com/blacktop/ipsw)

## Linux

***说明：***

Linux能说的东西暂时不多，目前围绕的就是调试与符号分析，代码hook为主，主要讨论x86/x64版本，arm版本参考frida(https://frida.re/)

> * Hooking相关
>   * PolyHook2.0(https://github.com/stevemk14ebr/PolyHook_2_0)
>   * minhook(x86/x64)for windows(https://github.com/TsudaKageyu/minhook)
>   * Injection for Linux/Windows(https://github.com/kubo/injector)
>   * Injection for Linux(without ptrace)(https://github.com/DavidBuchanan314/dlinject)
> * Debug相关
>   * gdb plugin1(gef)(https://github.com/hugsy/gef)
>   * gdb plugin2(pwndbg)(https://github.com/pwndbg/pwndbg)
>   * gdb plugin3(peda)(https://github.com/longld/peda)

**备注：Linux研究的内容一般偏向服务端，如果研究客户端，上述的内容+IDApro 大多数情况下都能解决相关问题**

> Go语言程序逆向:
>
> 备注: 正向开发是要有一定基础的，不然无法理解语言特性及其内存保护设计，分析起来会略显尴尬
>
> * (IDApro插件，目前比较好用的插件，Golang目前的ABI貌似不是很稳定，因此版本更替时，可能需要修改部分代码适应新型语言ABI)(https://github.com/0xjiayu/go_parser)
> * (IDApro插件，比较老了，谨慎参考)(https://github.com/strazzere/golang_loader_assist)
> * (Golang Profiler,重点是第二个链接)(https://github.com/DataDog/go-profiler-notes)(https://github.com/DataDog/go-profiler-notes/blob/main/stack-traces.md)
> * (Golang源码，程序尤其是函数分析时，很多系统设计的相关保护操作会有所体现，需要结合源码分析，以区分是Golang系统代码还是业务代码)(https://github.com/golang/go)

# Senior Reverse Engineering

## 反汇编-Tools

概念(https://en.wikipedia.org/wiki/Disassembler)

***工具***

> * x86/x64反汇编器(zydis)(https://github.com/zyantific/zydis)
> * x86/x64反汇编器(bddisasm)(https://github.com/bitdefender/bddisasm)
> * x86/x64反汇编器(distorm)(https://github.com/gdabah/distorm)
> * **arm,arm64,x86/x64等多功能反汇编器(capstone)(https://github.com/aquynh/capstone)**
> * **多功能汇编器(keystone)(https://github.com/keystone-engine/keystone)**
> * 多功能反汇编器(ddisasm)(https://github.com/GrammaTech/ddisasm)
> * arm/arm64 Runtime Code Generation Library(https://github.com/Linaro/vixl)

## 反编译-Tools

概念(https://en.wikipedia.org/wiki/Decompiler)

* IDA Pro(目前最好用，没有之一)
* Ghidra(https://github.com/NationalSecurityAgency/ghidra/)
* arm/arm64 Runtime Code Generation Library(https://github.com/Linaro/vixl)
* llvm-based decompiler(反编译效果对于小型binary或者SL还是能接受的，大型软件，反编译效果极差,慎用)(https://github.com/avast/retdec)
  * RetDec 在 桔网(https://news.ycombinator.com)的讨论(https://news.ycombinator.com/item?id=19079503)



## DBI(二进制动态调试组件)-Tools

有时候静态分析总会有点力不从心，尤其是分析C/C++底层代码时，Object、Pointer、Class、vtable的设计，结构体的嵌套，符号的极度丢失，这个时候有必要借助动态调试框架或者工具能极大帮助我们定位相关功能模块，同时做好反调，反跟踪也是很重要的保护措施

> * **miasm**(x86series,arm,mips)(https://github.com/cea-sec/miasm/)
> * Runtime Mobile Explotation(**objection**, Frida-based Framework)(https://github.com/sensepost/objection)
> * powerful binary analysis platform(**angr**)(https://github.com/angr/angr)
> *  Advanced Binary Emulation Framework(**qiling**)(https://github.com/qilingframework/qiling)
> * Dynamic Instrumentation Tool Platform(**dynamorio**)(https://github.com/DynamoRIO/dynamorio)
> * dynamic binary instrumentation framework(**Pin**,x86/x64)(https://software.intel.com/content/www/us/en/develop/articles/pin-a-dynamic-binary-instrumentation-tool.html)
> * Dynamic Binary Instrumentation framework based on LLVM(**QBDI**)(https://github.com/QBDI/QBDI)
> * **Frida**(多次提起，比较方便的framework)(https://github.com/frida/frida)
> * machine & userspace emulator and virtualizer(**QEMU**,巨无霸型的模拟器)
>   * 入门介绍(https://airbus-seclab.github.io/qemu_blog/)
>   * https://github.com/qemu/qemu
> * **radare2**(UNIX-like reverse engineering framework and command-line toolset,命令行目前最好用的调试工具)(https://github.com/radareorg/radare2)
> * Automated static analysis tools for binary programs(**pharos**)(静态分析工具，之所以归结在此，大部分处理逻辑都是binary intruments，因此和上述内容类似)
>   * 这个工具主要看看他的OOAnalyzer和CallAnalyzer实现(比较重要)
> * Unicorn(轻量级的CPU模拟器)(https://www.unicorn-engine.org/)
>   * **关于Unicorn相关的使用入门及高阶，如果有兴趣的话，可以发邮件或者私聊发给你们。**

***备注：针对不同的分析应用，选用最合适的DBI，毕竟不是所有的都是完美支持的，可以尝试做customize***

## 研究领域(*非用心者，勿扰该领域*)

### 符号执行框架

***理论:***

> * SAT/SMT Solver
>   * microsoft 关于相关理论的Slides(https://github.com/Z3Prover/z3/wiki/Slides)
>   * microsoft关于相关理论的publications(https://github.com/Z3Prover/z3/wiki/Publications)
> * Symbolic Execution
>   * 实现技术调查(https://arxiv.org/pdf/1610.00502)
>   * 维基百科给出的解释(https://en.wikipedia.org/wiki/Symbolic_execution)
>   * SAT_SMT By Examples(https://sat-smt.codes/)

***Toosets:***

> * angr(https://github.com/angr/angr)
> * miasm(https://github.com/cea-sec/miasm/)
> * z3(需要重点照顾的)(https://github.com/Z3Prover/z3)
> * Triton(https://github.com/JonathanSalwan/Triton/)
> * Klee(https://github.com/klee/klee)
> * symcc(https://github.com/eurecom-s3/symcc)

备注；选用符号执行时，一定要选择最合适的，目前我这边用的最多的是**miasm和angr,z3**

### 反编译研究

#### 反混淆、VM执行(主要利用symbolic execution&Taint Analysis)

说明:为了尽可能加大Hacker的逆向难度，往往关键代码，算法会尝试使用相关混淆技术，甚至定制VM-Code执行相关逻辑，以保护其中的逻辑，这里需要以OLLVM为开拓者为基础的相关混淆，以及VMProtect 进行VM虚拟化保护，开源社区提供了一部分references供大家参考，比如上面的符号执行方案就是其中之一。

备注: 既然OLLVM是基于LLVM的，因此 LLVM编译组件是要好好学的，这个是编译组件，clang/clang++,lldb等

***LLVM公共网站(https://llvm.org/) - 目前本人研究领域之一***

> * OLLVM-Based 混淆(指令替换，虚假控制流，控制流扁平化，函数注解)(https://github.com/obfuscator-llvm/obfuscator)
> * Hikari(LLVM-based)(https://github.com/HikariObfuscator/Hikari)
> * Tigress-Protection(Tigress binary protection)(https://github.com/JonathanSalwan/Tigress_protection)

> 对抗混淆历史:
>
> 关于反编译的研究分析(主要基于开源项目):
> 说明: 目前分析市面上的反编译工具(RetDec,Ghidra,IDA),结果显示IDA效果是最好的，IDA 7.2后面引入
> microcode机制，相较于之前的基于CTree机制的反编译，效果更加，而且对抗混淆效果最好，由于现有
> 市面的混淆代码越来越多(抖音，SnapChat(ollvm作者目前就职于该公司))(主要是基于LLVM IR的混淆较多)(开源框架:OLLVM,Hikari，基于二者的魔改等)，给逆向与安全研究员带来不少
> 的困扰，因此有必要对相关反混淆机制进行研究，先将业界的目前的研究成功共享一下，有心学习编译器
> 相关以及IR相关的同学可以参考学习(难度较高)
> 1) IDA microcode 使用分析
>    IDA 创始人关于microcode的介绍:  	    
>
> ​	https://recon.cx/2018/brussels/resources/slides/RECON-BRX-2018-Decompiler-internals-microcode.pdf
>    2018年: 
> ​        作者:Rolf Rolles(使用microcode首次对抗基于LLVM混淆)
> ​		Blog:https://www.hex-rays.com/blog/hex-rays-microcode-api-vs-obfuscating-compiler/
> ​        开源的插件地址：https://github.com/RolfRolles/HexRaysDeob(C++版本)
> ​		因为是基于ida7.2的，因此需要逆向的版本ida反编译插件(见以下)
>    2019年:
> ​        作者:chrisps ida7.0 microcode的逆向版本(C++版本)，与作者沟通过几次，详情参见GitHub issues内容，这个版本目前正是我们使用的版本，可以用这个版本编译上面的插件
> ​		开源地址:https://github.com/chrisps/Hexext
> ​	    作者: Nadège Duval分享的microcode内部机制
> ​		Blog: https://blog.amossys.fr/stage-2019-hexraysmicrocode.html
>    2020年：
> ​		作者:ESET(研究机构)分享新型挖矿病毒遇到的混淆分析	Blog:https://www.welivesecurity.com/2020/03/19/stantinko-new-cryptominer-unique-obfuscation-techniques/
> ​		开源地址：https://github.com/eset/stadeo(基于python与miasm框架)
> ​		缺点:没有相关的sample，看代码实现有点点费劲
> ​		作者:gaasedelen 2020年IDA contest获奖插件，基于ida7.2以上版本的microcode可视化分析
> ​		开源地址:https://github.com/gaasedelen/lucid
> ​		作者:eShard(研究机构)分享的可扩展式microcode插件(基于python接口)
> ​		blog:https://eshard.com/posts/d810_blog_post_1/
> ​		开源地址：https://gitlab.com/eshard/d810
> ​		该版本有相关sample可供分析:https://gitlab.com/eshard/d810_samples
> ​	国内情况:	    目前的分析结论只是针对特定的混淆方案，如果多重分析方案共同起作用，国内目前开源的方案效果不明显
> TODO:
>
>  * ida 7.0逆向的microcode需要convert to python接口版本
>    * ida 7.0逆向版本的接口亟待继续分析+优化(公司买不起正版的ida后果)
>    * z3 符号执行继续深入分析
>    * 布尔-算术bit级运算分析
>    * LLVM IR 深入分析

> 对抗混淆Toolsets(**只能作为思路分析，具体的还是要具体分析，不能生搬硬套**):
>
> * Manipulation, canonicalization and identification of mixed boolean-arithmetic symbolic expressions(基于布尔理论)(https://github.com/quarkslab/arybo)
> * Hex-Rays microcode API plugin for breaking an obfuscating compiler(IDApro对抗扁平化，虚假控制流)(https://github.com/RolfRolles/HexRaysDeob)
> * Hex-Rays microcode API 可视化插件，协助分析反编译(https://github.com/gaasedelen/lucid)
> * D810(具体内容参考Readme,主要基于miasm分析的)
>   * https://gitlab.com/eshard/d810
>   * https://gitlab.com/eshard/d810_samples
> * miasm's ollvm deflatter
>   * 思路分析与介绍(https://mrt4ntr4.github.io/MODeflattener/)
>   * 相关源码分析(https://github.com/mrT4ntr4/MODeflattener)
> * 

> VMProtect 研究:
>
> 1) VMProtect2-Detailed Analysis of the Virtual Machine Architecture-Part01(https://back.engineering/17/05/2021/)
>
> 2) VMProtect2-Complete Static Analysis-Part2(https://back.engineering/21/06/2021/)
>
> 3) VMProtect 2 Reverse Engineering-GitLab总结(https://githacks.org/vmp2)
>
> 4) static devirtualizer for VMProtect x64 3.x(VTIL-Core-based)(https://github.com/can1357/NoVmp)
>
> 5) VTIL-Core(Virtual-machine Translation Intermediate Language)(说实话，设计还是蛮新颖的，建议看看)(https://github.com/vtil-project/VTIL-Core)
>
> 6)VMP3逆向分析虚拟机指令(看雪论坛)(https://bbs.pediy.com/thread-266206.htm)
>
> 7) VMP3.X Introduction and Analysis
>
> * Part-1(Unpacking)(https://whereisr0da.github.io/blog/posts/2021-01-05-vmp-1/)
> * Part-2(Code Mutation)(https://whereisr0da.github.io/blog/posts/2021-01-26-vmp-2/)
> * Parr-3(Virtualization)(https://whereisr0da.github.io/blog/posts/2021-02-16-vmp-3/)

> 研究(目前研究领域一，主要涉及编译器，反编译器，布尔理论，混淆机制深究):
>
> * Boosting SMT Solver Performance on Mixed-Bitwise-Arithmetic Expressions(https://dl.acm.org/doi/pdf/10.1145/3453483.3454068)
> * Loki: Hardening Code Obfuscation Against Automated Attacks(https://arxiv.org/pdf/2106.08913.pdf)
> * Semi-Automatic Code Deobfuscation(miasm-based)(https://github.com/mrphrazer/hitb2021ams_deobfuscation)
> * Code deobfuscation framework to simplify Mixed Boolean-Arithmetic (**MBA**,理论比较抽象，哈哈) expressions (https://github.com/mrphrazer/msynth)
> * QSynth-A Program Synthesis based Approach for Binary Code Deobfuscation(https://archive.bar/pdfs/bar2020-preprint9.pdf)
> * MBA Deobfuscation(https://www.usenix.org/conference/usenixsecurity21/presentation/liu-binbin)
> * code analysis platform(code property graphs理论)
>   * https://joern.io/
>   * https://docs.joern.io/home/
> * Intertwining ROP Gadgets and Opaque Predicates for Robust Obfuscation(https://arxiv.org/abs/2012.09163)
> * Introduction to Control-Flow Graph Analysis(https://synthesis.to/2021/03/15/control_flow_analysis.html)
> * GreyBox Automatic Exploit Generation For Heap Overflows in Language Interpreters(https://seanhn.files.wordpress.com/2020/11/heelan_phd_thesis.pdf)
> * Reasoning about Software Security via Synthesized Behavioral Substitutes(https://synthesis.to/papers/phd_thesis.pdf)
> * Pointer Analysis(https://yanniss.github.io/points-to-tutorial15.pdf)
> * Loop-invariant code motion(编译器理论)(https://en.wikipedia.org/wiki/Loop-invariant_code_motion)
> * Algorithmic for Hard Problems(书，关于解决疑难问题的算法理论)(https://www.springer.com/gp/book/9783540441342)
> * What is a while(2) loop in hex-rays(reddit-reverse engineering 板块解读)(https://www.reddit.com/r/ReverseEngineering/comments/lx81n7/what_is_a_while2_loop_in_hexrays/)
> * Ghidra decompiler(反编译器设计,Control flow structuring 设计模式查看 <==> 对比IDA pro的反编译代码逻辑分析)(https://github.com/NationalSecurityAgency/ghidra/tree/2108a5ed4c8a16eaa00cde7eebdbbf67fe472dec/Ghidra/Features/Decompiler/src/decompile)
> * Context-sensitive HexRays decompiler plugin that visualizes the ctree of decompiled functions(IDA 反编译插件-注意: Ctree模块非microcode模块)(https://github.com/patois/HRDevHelper)
> * Virtual Inheritance vs Virtual functions(虚拟继承的维基百科讲解)(https://en.wikipedia.org/wiki/Virtual_inheritance)
> * Recovery of Symbolic Mathematics from Code(ReMath)(https://sam.gov/opp/37ceb419bf0546508923ad5b75f6df74/view)
> * An exhaustive analysis of ComRAT v4(反编译器的极致应用for ida，值得大家花点时间看看)(https://www.msreverseengineering.com/blog/2020/8/31/an-exhaustively-analyzed-idb-for-comrat-v4)
> * Processor Microarchitecture:An implementation perspective(https://www.morganclaypool.com/doi/abs/10.2200/S00309ED1V01Y201011CAC012)
> * Synthesizing Loop-Free Programs with Rust(语言我不熟，可以用C++替换分析，嘻嘻) and Z3(https://fitzgeraldnick.com/2020/01/13/synthesizing-loop-free-programs.html)
> * Ph.D. thesis on symbolic abstraction(https://thakur.cs.ucdavis.edu/assets/pubs/thakur_PHD14.pdf)
> * IDA Pro utilities(主要关注反编译组件部分)(https://github.com/fireeye/flare-ida)
> * Hex-Rays Decompiler plugin for better code navigation (https://github.com/REhints/HexRaysCodeXplorer)

> 编译器组件研究:
>
> * LLVM/Clang(目前研究领域二)
>   * https://llvm.org/
>   * https://clang.llvm.org/
> * Javascript Engine
>   * quickjs(https://bellard.org/quickjs/)
>   * quickjs-java-bridge(https://github.com/cashapp/quickjs-java)
>   * cycrypt(虽然不是engine，用的是基于JavascriptCore-Webkit，但是有frida框架做重写)
>     * http://www.cycript.org/
>     * https://github.com/nowsecure/frida-cycript
> * C Compiler Engine
>   * TCC(https://bellard.org/tcc/)
>   * lacc(https://github.com/larmel/lacc)
>   * lcc(https://github.com/drh/lcc)
>   * chibicc(https://github.com/rui314/chibicc)
> * 杂项
>   * dynamic linker(QuarkslaB Dynamic Linker library-**QBDL** llvm-based)(https://github.com/quarkslab/QBDL)
>   * C Foreign Function Interface and JIT using Clang/LLVM (FFI llvm-based)(https://github.com/aguinet/dragonffi)
>   * dyld source code 分析(https://opensource.apple.com/tarballs/dyld/)
>   * Linux Dynamic Linker(Gold vs ld,总共20series)(http://a3f.at/lists/linkers)
>   * how to write shared libraries(linux版)(http://people.redhat.com/drepper/dsohowto.pdf)

# References
  - 源于对生活的热爱，Joy!!
