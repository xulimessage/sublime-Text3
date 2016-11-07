[TOC]
#Sublime Text3的Markdown配置

使用了Sublime Text3一段时间感觉不错.它除了可以进行Markdown写作外，最重要的是支持各种代码高亮，以及强大的插件拓展。并且支持Windows和Mac OS双平台。之前开始安装的时候网上搜了一下，发现都是Sublime Text2的教程.在3中有些配置发生了变化.这里以Windows为例,分享一下安装Markdown的教程.至于Mac平台，我推荐大家使用Macdown进行Markdown写作。

##1.注册Sublime Text3

如果你在官网下载的话，默认的是未注册版本，你可以看到在窗口上会显示”未注册“。虽然这个不影响什么，但总觉得不太好。要去除这个的话就得有注册码。这个大家可以网上搜一下，我这里给出3个从别处看到的，亲测可以使用，只需要复制其中一个即可。使用方法:点击Help->Enter License。如果用不了请在下面告诉我。



```
—– BEGIN LICENSE —–
Andrew Weber
Single User License
EA7E-855605
813A03DD 5E4AD9E6 6C0EEB94 BC99798F
942194A6 02396E98 E62C9979 4BB979FE
91424C9D A45400BF F6747D88 2FB88078
90F5CC94 1CDC92DC 8457107A F151657B
1D22E383 A997F016 42397640 33F41CFC
E1D0AE85 A0BBD039 0E9C8D55 E1B89D5D
5CDB7036 E56DE1C0 EFCC0840 650CD3A6
B98FC99C 8FAC73EE D2B95564 DF450523
—— END LICENSE ——
```

```
—– BEGIN LICENSE —–
K-20
Single User License
EA7E-940129
3A099EC1 C0B5C7C5 33EBF0CF BE82FE3B
EAC2164A 4F8EC954 4E87F1E5 7E4E85D6
C5605DE6 DAB003B4 D60CA4D0 77CB1533
3C47F579 FB3E8476 EB3AA9A7 68C43CD9
8C60B563 80FE367D 8CAD14B3 54FB7A9F
4123FFC4 D63312BA 141AF702 F6BBA254
B094B9C0 FAA4B04C 06CC9AFC FD412671
82E3AEE0 0F0FAAA7 8FA773C9 383A9E18
—— END LICENSE ——
```

```
—– BEGIN LICENSE —–
J2TeaM
2 User License
EA7E-940282
45CB0D8F 09100037 7D1056EB A1DDC1A2
39C102C5 DF8D0BF0 FC3B1A94 4F2892B4
0AEE61BA 65758D3B 2EED551F A3E3478C
C1C0E04E CA4E4541 1FC1A2C1 3F5FB6DB
CFDA1551 51B05B5D 2D3C8CFE FA8B4285
051750E3 22D1422A 7AE3A8A1 3B4188AC
346372DA 37AA8ABA 6EB30E41 781BC81F
B5CA66E3 A09DBD3A 3FE85BBD 69893DBD
—— END LICENSE ——
```

	2016.05.15
	上面的已经失效了，应该是用的人太多了吧，这里有一个有效的
	适合V3103版本

```
—– BEGIN LICENSE —–
Ryan Clark
Single User License
EA7E-812479
2158A7DE B690A7A3 8EC04710 006A5EEB
34E77CA3 9C82C81F 0DB6371B 79704E6F
93F36655 B031503A 03257CCC 01B20F60
D304FA8D B1B4F0AF 8A76C7BA 0FA94D55
56D46BCE 5237A341 CD837F30 4D60772D
349B1179 A996F826 90CDB73C 24D41245
FD032C30 AD5E7241 4EAA66ED 167D91FB
55896B16 EA125C81 F550AF6B A6820916
—— END LICENSE ——
```

##2.安装Package Control
打开Sublime Text3，按下组合键Ctrl + `，出现控制台，输入:
```
import urllib2,os; pf='Package Control.sublime-package'; ipp = sublime.installed_packages_path(); os.makedirs( ipp ) if not os.path.exists(ipp) else None; urllib2.install_opener( urllib2.build_opener( urllib2.ProxyHandler( ))); open( os.path.join( ipp, pf), 'wb' ).write( urllib2.urlopen( 'http://sublime.wbond.net/' +pf.replace( ' ','%20' )).read()); print( 'Please restart Sublime Text to finish installation')
```
安装完成后打开Preferences就能看到,打开Package Control，输入install package，稍等一会就会出现很多插件，搜索你要的插件然后安装.

##3.安装Markdown Preview和Markdown Editing
打开Package Control，输入install package，然后分别输入Markdown Preview和Markdown Editing进行安装。安装完成后点击右下角就能选择Markdown,Markdown GFM和MultiMarkdown进行写作了。

##4.设置Sublime Text3主题皮肤

一个好的主题皮肤能让界面更美观，写作更愉快。这里推荐一个主题:Spacegray。打开Package Control，输入install package，然后输入Spacegray.安装完成后在Preferrences->Color Scheme选择主题.

##5.关闭文件记忆以及主题皮肤应用到Markdown
Sublime Text3默认每次打开都会自动打开上次保存的文件,可以这样进行关闭.
打开Preferences->Settings User,输入:
```
{
    "hot_exit": false,
    "remember_open_files": false,
}
```
其中,"hot_exit": false，"remember_open_files": false表示关闭自动打开上次保存的文件。
如果应用主题皮肤后发现切换Markdown界面无变化,那么在Settings User输入:
```

    "color_scheme": "Packages/MarkdownEditing/MarkdownEditor-Dark.tmTheme",
    "font_size": 11,
    "ignored_packages":
    [
        "Markdown",
        "Vintage"
    ]
}
```
完整代码:
```
{
    "hot_exit": false,
    "remember_open_files": false,
    "color_scheme": "Packages/MarkdownEditing/MarkdownEditor-Dark.tmTheme",
    "font_size": 11,
    "ignored_packages":
    [
        "Markdown",
        "Vintage"
    ]
}
```

##6.设置markdown在浏览器中打开快捷键
Sublime Text3不支持Markdown实时预览,所以我们只能在浏览器中查看.可以绑定快捷键进行查看。打开Preferences->Key Bindings User,输入:

```
[
    { "keys": ["ctrl+r"], "command": "markdown_preview", "args":   {"target": "browser", "parser":"markdown"} }
]
```
其中,"ctrl+r"表示快捷键，可以更改。
##小结
在Sublime Text3中,所有Default代码都不能直接更改，而是要在User里面把要更改的代码复制过来再进行更改,这是与之前版本不同的地方.