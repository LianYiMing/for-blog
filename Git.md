Git使用全

## 版本管理为何而生

> 搞过自己的项目嘛？

用软体搞曲子，hbuilder写个网站，AI和PS画个吊图

还是CAD搞个屌爆的设计，3D打印牛掰的建模

或者用word总结的教学经验，写的书

> 如果你习惯多端协作，版本控制绝对是个问题

任何时候任何设备都无法组织你的热情

早上吃饭用手机突发奇想改两下

地铁用mac笔记本详细扩展早上的奇想

班上偷偷用单位的Windows接着搞搞

晚上回家抓起Linux继续起飞

但。。。。

老子怎么同步文件

用U盘挨个拷咩？

> ”您老也不嫌麻烦“

**你应该了解下git**

>  你跟一堆人协作过咩？

当一堆人同时搞一个项目

宋兵甲刚写完项目介绍，电脑里项目文件却还是n天前的

炮灰乙打完工程的最后一个右括号，保存退出发现文件夹里项目的介绍却还是空的

流氓丙写完PPT，望着同样控不拉叽的文件夹拿起来电话

> "项目搞完了咩？微信发我"

然鹅超过100mb![0](C:\Users\Administrator\Desktop\0.png)

> "草！"
>
> “张小龙____”

还是只能拿着u盘傻不拉叽在寒风挨个去找。。。

如果几万人的大公司呢？

> ''博纳瑟也得送u盘跑死'

**牛逼的git闪亮bling登场**

<hr>

我们会发现不管是个人项目or团队协作

核心问题就是如何在不同设备处理最新的更改，也就是——

> 版本管理

项目开发不是小case——

大多数情况下需要整个团队甚至一个公司的人work together才能完成一个项目

只要能**提升效率**的东东一定就会有人搞

and我们刚刚聊到了

> 版本管理——在共同开发中很重要

于是也就有了现在的一大堆专门的工程版本管理器

遵循10分有逻辑性的规则来管理，

万人团队共同协作也不会导致版本错乱

而目前人数最多也是最适合个人项目用的

`Git`

关于团队开发才需要用到的功能，我们用不上，但其他的功能

```
it just works!
```

## git介绍

要用它就看看究竟是怎么个管理法

所有的版本管理都必须要遵循一条原则——

> 需要有一条主分支来来存放当前的最新进度

这样就可以无论任何地点，

只要和主分支进行同步，就能够在最新的版本上进行工作，不至于有文件修改的冲突

其实用U盘在不同端互相拷文件，U盘就是”主分支“

主分支需要在继续工作的任何地方都能能访问的到

> 互联网

于是

不管是中心式管理版本的系统CVS,Subversion

还是分布式管理版本的Git

都有一个主分支且都放在服务器上

（所以其实不同的版本管理器都能个人用，只是应对细分情况有不同的处理方法，关于个人的版本控制可能无关紧要）

> ps：服务器可以自己搭建也可以直接用现成的免费版本管理服务

git和其它主流版本管理器其实就是在”分布式上“

主流的代码管理器都是以中央服务器为主，

在各端修改好更新后提交给中央服务器

通过后再改变中央服务器的项目，

之后再使用的时候只用在其它端同步一下，就能让版本与服务器一致

git也是这样，只是其他的项目管理器只认服务器，只要你的的提交不通过

本地的代码就对服务器的项目没有屁作用

> 以我为主

![image-20210209111357218](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210209111357218.png)

而git则是像一个大树

在主分支工作的时候跟中心版本控制没有什么不同

而你还有另一个选择

> 分支

你可以在主分支外分出来一条不一样的分支

之后你的所有提交都会提交到中心服务器你分出来的分支而不是主分支上

> 还可以多条分支与主分支合并

如果没有文件修改的冲突（比如一个文件在其它分支和主分支上都被修改过）

就能完美合并

> 有屁用？

真的有很多屁用

在于多人开发项目的协同工作

各部门开发各部门的，每个部门一个分支，

首先在自己的分支上把本部门搞出来的最新代码和已经在其余部门的分支中验证无误的其它代码一起运行测试

之后与主分支进行合并，这样不管是哪个部门都能够用最新且正确的代码

来给自己新开发出来不稳定的代码进行测试

保证效率，也保证主分支的无误

> 牛逼格拉斯

![src=http___img.it610.com_image_info2_0ea4d608d94a434e84e69bf10ec0cc71.jpg&refer=http___img.it610](C:\Users\Administrator\Desktop\src=http___img.it610.com_image_info2_0ea4d608d94a434e84e69bf10ec0cc71.jpg&refer=http___img.it610.jpg)

各分支互不干扰，但仍以主分支为主

> 兼收并蓄

比中心版本管理貌似还要牛掰

所以也就头部效应胜者通吃——

世界上排名第一和第二的开源平台:

```
github,gitlab
```

全部是采用git

最主要还是由于git对于开源社区的共同无偿协作的效率提升很有意义

> Ps: Git就是当初在开发Linux的时候被发明出来管理代码版本的

## 实操

分为`本地`和`服务器`的配置

服务器不同，本地的配置也不同，所以先选择服务器

github功能最多，国内的gitee码云最快

反正我用`github`

去官网创建账号，

![image-20210209121905066](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210209121905066.png)

点击new创建一个新仓库

![image-20210209121954529](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210209121954529.png)

只用设置仓库名就可以

![image-20210209122219597](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210209122219597.png)

由于没有任何文件，所以提示你要在本地打开进行提交

> 分为便捷的应用无脑提交和屌炸的命令行提交

应用提交：（仅支持windwos和mac）

下载github的windwos+mac桌面应用

https://desktop.github.com/

![image-20210209122557778](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210209122557778.png)

左边克隆仓库到本地

```
"Clone a repository from the Internet"
```

弹出来的窗口选择仓库和路径

![image-20210209123909686](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210209123909686.png)

克隆下来后

试着添加个文件

![image-20210209124120680](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210209124120680.png)

之后

```
左下角commit
```

```
右上角publish
```

```
右中侧Creat pull request是教你如何合并分支
点击后由于只有一个分支，所以怎么搞都会卡在这

```

就会发布主分支master的第一个commit到github的服务器上

之后每一次修改后来应用提交一下就会自动同步到github云端

如果其它设备修改后提交到同一个分支，右上角就会变成







也就是众多版本管理系统都支持的branch分支和pull request合并

>  服务器咋知道我改了

拷贝下来的文件，每一次修改都会被记录在本地提交get的时候也会带着这些文件提交到云端，所以云端就可以判断出来是新文件还是修改的旧文件



因为它只是一套管理理念，所以我们可以自己搭服务器来用git管理代码，具体的操作只需在命令行里通过git命令就可以实现代码的push(提交新变更)

电脑端的桌面应用，本质上就是一个git命令的可视化执行命令软件

在底层也是运行了git 命令

所以只要我们手机上能够找到命令行应用，并且安装git环境

( git命令一般都是git开头，如果要使用就要安装环境)

就可以实现在手机上使用git管理

再搭配一些手机端的IDE就可以实现无电脑化的优雅写代码

@菜鸟教程:

你的本地仓库由 git 维护的三棵"树"组成。第一个是你的 工作目录，它持有实际文件；第二个是 暂存区（Index），它像个缓存区域，临时保存你的改动；最后是 HEAD，它指向你最后一次提交的结果。

平常电脑上要很方便用git来管理代码的版本，一般都是用github的桌面端，修改完代码保存后，打开桌面端就可以直接提交新的变更，很方便

并且是存在github服务器上的，也不会丢

但是移动手机端截止到现在没有相关软件可以实现

所以这一个专辑就来聊一聊怎么样在手机使用Git进行版本管理

Git

是一套代码的版本管理系统，最突出的特点就是可以回溯

某一次更改

所以世界上最大的代码托管平台Github, 就是用的git作为代码管理

因为它只是一套管理理念，所以我们可以自己搭服务器来用git管理代码，具体的操作只需在命令行里通过git命令就可以实现代码的push(提交新变更)

电脑端的桌面应用，本质上就是一个git命令的可视化执行命令软件

在底层也是运行了git 命令

所以只要我们手机上能够找到命令行应用，并且安装git环境

( git命令一般都是git开头，如果要使用就要安装环境)

就可以实现在手机上使用git管理

再搭配一些手机端的[IDE](https://mp.weixin.qq.com/s?__biz=MzAwOTUzNTYxOQ==&mid=2680263703&idx=3&sn=969826e4d5eba4c4b849728e76d6ecef&scene=21#wechat_redirect)就可以实现无电脑化的优雅写代码

[(手机实现电脑体验的优化详见这里)](https://mp.weixin.qq.com/s?__biz=MzI4Nzc2MzA3OQ==&mid=2247485651&idx=1&sn=351029a68ea1eb80cb00c24c4ec18f6c&scene=21#wechat_redirect)

------

用的命令行就是最著名的termux

https://www.coolapk.com/apk/com.termux![图片](https://mmbiz.qpic.cn/mmbiz_jpg/tMsLbdfwxoNm5dsN1XpKvuBGCjZSuIqQibU2ia3WXCKth0XpXvynphXibLSs5DJwv7Ten1qK67OsibDbYSdicexuiagw/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)
可以在手机上进行n多命令行操作，之后会详细聊到

最主要的就是，可以安装git环境

安装

打开termux

![图片](https://mmbiz.qpic.cn/mmbiz_png/tMsLbdfwxoNm5dsN1XpKvuBGCjZSuIqQicfMhGLkKicn7gCmrZ0yE5ic1xdG1w5UwTpgnz4jOAeUPtay477ibhnzMA/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)
执行git安装命令

pkg install git

应该就会弹出来如下代码

![图片](https://mmbiz.qpic.cn/mmbiz_png/tMsLbdfwxoNm5dsN1XpKvuBGCjZSuIqQQfDn5oiaH4NCz2JfhiavWzMqwmbEwicapTibzXV9d5QpqffsvU63H9MA8A/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)
之后会有do you want to continue?

输入y接着进行git安装
![图片](https://mmbiz.qpic.cn/mmbiz_png/tMsLbdfwxoNm5dsN1XpKvuBGCjZSuIqQpn2EOHdJhCN8cgydYicq9t6ibPxbkY9xmDurbRqhKX4bOf2v08DWGeZQ/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)
一切正常，回出现上图所示代码提示，最后两行是setting up

也就是安装成功

输入git --version

运行一个最简单的git代码→查看版本

如果底下弹出了git版本就说明安装成功了

这样termux终端就成功安装上了git

使用

git为了确保安全，通过rsa加密进行ssh数据传输

总之需要我们进行验证

首先让termux装上支持ssh传输的环境

执行

pkg install openssh

![图片](https://mmbiz.qpic.cn/mmbiz_jpg/tMsLbdfwxoNm5dsN1XpKvuBGCjZSuIqQq3tELl9MvdHnnIMeVLULAuItNslYWtbB1QweDMVxSXZTKSGLEfibTrw/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

时间会很长，慢慢等

![图片](https://mmbiz.qpic.cn/mmbiz_png/tMsLbdfwxoNm5dsN1XpKvuBGCjZSuIqQ93XNOkMOeYEa5r3J83TzVgaJPLh56m9kGf5ltdWwJSAaAUhhbe7LFQ/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)



[接着昨天](https://mp.weixin.qq.com/s?__biz=MzI4Nzc2MzA3OQ==&mid=2247485990&idx=1&sn=8fba1091189568f0664c4ee892f0d4f3&scene=21#wechat_redirect)

安装完ssh之后(也就是进度条走完)

![图片](https://mmbiz.qpic.cn/mmbiz_png/tMsLbdfwxoNm5dsN1XpKvuBGCjZSuIqQ93XNOkMOeYEa5r3J83TzVgaJPLh56m9kGf5ltdWwJSAaAUhhbe7LFQ/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

会这样

![图片](https://mmbiz.qpic.cn/mmbiz_png/tMsLbdfwxoNm5dsN1XpKvuBGCjZSuIqQofgqVbA1zkzib8BfzKrXWLRAticcOFeRZoXzeY9qpTicnumfPKKTVuIpA/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)
(马赛克部分的是个人的密钥，如果泄漏出去代码的安全就不保，所以如果要给别人截图，还是像上图一样码一下)

如果弹出来跟上图一样就可以使用ssh了

这时候执行

ssh-keygen -t rsa -C "git@github.com" 

之后按三次回车

![图片](https://mmbiz.qpic.cn/mmbiz_png/tMsLbdfwxoPm71Kyw5tKey12KrOwtvINibqhoK1yiaYbTVRVNcIOKaS30eegJsJamS8UnXc23bpnBN8XcRJCfJicA/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)
如果遇到是上图，就是失败了，如果是下图就是成功

![图片](https://mmbiz.qpic.cn/mmbiz_png/tMsLbdfwxoPm71Kyw5tKey12KrOwtvINP9EyeeHODDTQTM5dX7lr2Jb5yyy5BkK04ZEyDiaPl2fMOZvVA4kMY0Q/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)
发现输三个空格会失败，打一个字母再回车就不会

之后执行代码来查看ssh密钥

cd ~/.ssh

cat id_rsa.pub

(记得码住再截屏。。。)

![img](data:image/gif;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAAADUlEQVQImWNgYGBgAAAABQABh6FO1AAAAABJRU5ErkJggg==)把后面这一段乱码复制下来，包括前面和后面的

后面的很重要，也就是使用哪一家的git，如果使用github的git，就要在第一步执行

ssh-keygen -t rsa -C "git@github.com"

如果是其他就改@后的

ssh密钥最后会显示

如果搞错git服务就重新执行

ssh-keygen -t rsa -C "git@改过来的你想用的服务"

![图片](https://mmbiz.qpic.cn/mmbiz_png/tMsLbdfwxoPm71Kyw5tKey12KrOwtvINP9EyeeHODDTQTM5dX7lr2Jb5yyy5BkK04ZEyDiaPl2fMOZvVA4kMY0Q/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)
会覆盖掉原有的搞错git服务的ssh密钥

------

接着第一更

我们现在有了ssh的密钥，为了能让github认出是我们

要去github粘贴公钥，上一更聊过，也就是执行

cd ~/.ssh

cat id_rsa.pub

复制弹出来的部分(带头带尾)

之后访问github

https://github.com/settings/profile

也就是找到设置

![图片](https://mmbiz.qpic.cn/mmbiz_png/tMsLbdfwxoPm71Kyw5tKey12KrOwtvINawKek6BrY1b3Qn6UpVNP49Ep3tPBr9wZmNC49MRTGo5DaO05tAvpCA/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)
之后找到ssh and Gpg

直接访问下面的链接也可以

https://github.com/settings/keys

右上角添加刚刚复制的公钥，也就是向github说有这个钥匙的人是值得信任的，就可以进行push分支

(因为github添加了公钥，

后只要有公钥都可以进行push分支，所以你的公钥泄露就可能会被恶意疯狂窜改仓库)

![图片](https://mmbiz.qpic.cn/mmbiz_png/tMsLbdfwxoPm71Kyw5tKey12KrOwtvINFylx8wS1t8fADjgxZ4DbbsBXquDUhmqeelJCAxVpCa2KicnDPTlZibvA/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)
之后会这样

![图片](https://mmbiz.qpic.cn/mmbiz_jpg/tMsLbdfwxoPm71Kyw5tKey12KrOwtvINJbK92czsVW2QuH2GEiahXYA5XE09RQtp70P89yvUribz84g4HMUedx1A/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)
也就是成功了

回到termux

执行git命令赖克隆一个仓库到本地

git clone git@github.com:用户或组织名/仓库名.git

比如一个仓库链接是这样

https://github.com/LianYiMing/SiteBuilding

那就要执行

git clone git@github.com:LianYiMing/SiteBuilding.git

![图片](https://mmbiz.qpic.cn/mmbiz_png/tMsLbdfwxoPm71Kyw5tKey12KrOwtvINiaevnfOzIHUibvibegSEnDcgqeYhd3nydFC48l2lU6Ho0hicb3zxnTAy5g/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)
如图

之后会弹出下图
![图片](https://mmbiz.qpic.cn/mmbiz_png/tMsLbdfwxoPm71Kyw5tKey12KrOwtvINFABD96JSaZvkMK4zv64YNN4ibTFHTsuKZqXtdx3nmp4dGDzGrmIsdYA/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)
也就是会有克隆的进度

![图片](https://mmbiz.qpic.cn/mmbiz_jpg/tMsLbdfwxoPm71Kyw5tKey12KrOwtvINI9s94NTvylYRwmcibkicto1TeCv8ZMjeicERiaBriczKF4yaouEOnbfFesg/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)
然后就克隆成功了，回到termux的data分区就能看到克隆的仓库了

![图片](https://mmbiz.qpic.cn/mmbiz_jpg/tMsLbdfwxoPm71Kyw5tKey12KrOwtvINGcES9iblWFy4qoUxQiad4UlPUiavicH41hFCPlib9nG9Vntulj0BIoGlFnw/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)
但是data分区不root看不到，所以就需要用[CD命令](https://mp.weixin.qq.com/s?__biz=MzI4Nzc2MzA3OQ==&mid=2247485756&idx=2&sn=457f57a0a44eb3001997f1a528a8f986&scene=21#wechat_redirect)来放到其他地方

我们现在可以在手机上通过termux，

使用git命令来克隆一个github的仓库到本地了

但是克隆下来的会在他的data分区里，不root没法查看

所以就要用到[CD命令](https://mp.weixin.qq.com/s?__biz=MzI4Nzc2MzA3OQ==&mid=2247485756&idx=2&sn=457f57a0a44eb3001997f1a528a8f986&scene=21#wechat_redirect)，在clone前换一个地方

 Termux上的CD命令是Linux里的语法

1.

cd 目录绝对路径

相对于root根目录来说的路径

这里的root目录我们平常访问不了

只能访问root目录里的一个子文件夹→内部存储

所以底下的CD命令会加上内部存储的路径

2.

cd ~

跳到自己的home目录(也就是命令行所在的目录)

termux的home目录也就是他的data分区

3.

cd ../..

跳到目前目录的上上两层

我们只需要用第1个CD就可可以

------

首先我们先要确定克隆下来的文件存放的文件夹的目录

原来聊过的xplore可以查看

![图片](https://mmbiz.qpic.cn/mmbiz_png/tMsLbdfwxoO630NQrZ6lWpmfrpAcjNfLILkS0jsrRDs0Q85aGl2bwleaB3cIlc9NJzFSia52MoqNlCRicg5OF7vA/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)
如图最上面就是文件路径

长按之后点击文件详情就可以一键复制

![图片](https://mmbiz.qpic.cn/mmbiz_jpg/tMsLbdfwxoO630NQrZ6lWpmfrpAcjNfLIQdvFYqZiaibe2C1KJ9y4vu9NNiavdNxJnAm2uZKvOLMdOytdVn6uibbhA/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)
回到termux

使用第一种

cd /storage/emulated/0/Download/Github

这时候执行的clone操作就会克隆到这个目录里

根据昨天聊的，执行clone

 git clone git@github.com:LianYiMing/SiteBuilding.git

![图片](https://mmbiz.qpic.cn/mmbiz_png/tMsLbdfwxoO630NQrZ6lWpmfrpAcjNfLkVAW0YKvDZrYIibV5nBTZN9teoAKDODVSmswuayM6ic1FGmjO7hicAhug/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)
这样就成功把git仓库克隆到指定路径了

![图片](https://mmbiz.qpic.cn/mmbiz_png/tMsLbdfwxoO630NQrZ6lWpmfrpAcjNfLraFCqY7swtGHEibymckzibbosdI7zMNlibQcVOme5uibOpG6Hb7fTduM5g/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)
如何提交git?

接着第一更

我们现在已经可以通过git命令，将一个远程的git仓库，clone到手机的某一路径了

![图片](https://mmbiz.qpic.cn/mmbiz_png/tMsLbdfwxoO630NQrZ6lWpmfrpAcjNfLraFCqY7swtGHEibymckzibbosdI7zMNlibQcVOme5uibOpG6Hb7fTduM5g/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)
要在手机上提交代码的修改，肯定需要pushGit，就是我们这一专辑的题目

------

pushGit

首先需要执行代码来验证身份

git config --global user.email "AGZX_lym@163.com"

上面双引号里填入你的github注册邮箱

git config --global user.name "LianYiMing"

双引号填入github用户名

![图片](https://mmbiz.qpic.cn/mmbiz_jpg/tMsLbdfwxoO630NQrZ6lWpmfrpAcjNfLH8nUQnM1m8j2uj471eSiaoRXgtLm9nkFxnIjC64oOaiancDxswvakvlQ/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

之后修改一下刚刚仓库里的文件，以确保可以push，没有修改过的话push会不成功

回到termux里，执行划线句子(建议分次)

*cd 仓库路径*

*git add .*

是一个点，是把所有内容都放到将要提交的缓存里的意思

*git commit -m ‘内容描述’*

先在本地建立新一次的提交，必须要有描述

*git push*

上传刚刚的commit

运行完这些就提交成功了

![图片](https://mmbiz.qpic.cn/mmbiz_png/tMsLbdfwxoMackP5CICx7TN3GIRN5NnAlEYG10NQcaj8RiaVTHQhniaU3AcVicyVHlacQISScoysHxcD05l0KggDQ/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)
这时候回到github上就可以看到刚刚的提交了

![图片](https://mmbiz.qpic.cn/mmbiz_png/tMsLbdfwxoMackP5CICx7TN3GIRN5NnAFXvkAkR1Mrevqgb8Hu8yovXCdPCxhWF2lyFxGJibwbbznAQcMHKTuDw/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

我们现在已经可以通过执行下面的代码

来在手机上通过终端termux

进行用git管理本地的版本了

有一些比较重要的操作

1. git pull

   有时候在两台设备上同时作业就会导致代码不一样，就需要用到git pull

   向github服务器请求文件，如果有本地没有的或者更新时间比本地新的就下载下来

   在其他端修改文件的话

   如果不在本地先执行git pull

   就会报错

   ![图片](https://mmbiz.qpic.cn/mmbiz_png/tMsLbdfwxoMackP5CICx7TN3GIRN5NnAenYHgwhZCQ10t0ZsLTlicvgojAw2R2ONfqkDDrspYkAbmFT8krx5fXA/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)
   如果在其他端修改了

   在本地修改后提交前一定要先执行一遍 git pull

2. git diff    　

   显示目录里的原文件和最新提交/缓存区的区别

   会输出

   a/README.md b/README.md

   index e69de29..cb5dc9f 100644

   --- a/README.md

   +++ b/README.md

   @@ -0,0 +1 @@

   +# 廉一鸣

   如果没有用 git add命令向暂存区添加任何东西，只会显示工作树与最新提交状态之间的差别。

   “+”号标出的是新添加的文件

   被删除的文件则用“-”号标出

   用 git add命令将 README.md 文件加入暂存区

   $ git add README.md

   如果现在执行 git diff命令，由于工作树和暂存区的状态并无差别，结果什么都不会显示

   **查看与最新提交的区别**

   git diff HEAD

   就会输出时间最近的一次提交和当前目录文件的区别

   ![图片](https://mmbiz.qpic.cn/mmbiz_png/tMsLbdfwxoMackP5CICx7TN3GIRN5NnAGQvw3ymLpKBEAGNURvg1qAKRThh0YhIrMJ3sp5GY6ibkucoMjiaLektQ/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)
   @@底下是文件的修改内容

   加了一行回车所以就会显示

   \+ 

   我们这几天聊到，如果要在手机上通过git

   来管理代码版本的话

   可以通过一个终端应用termux实现

   今天聊一个termux官方的换主题应用

   https://www.coolapk.com/apk/com.termux.styling

   ![图片](https://mmbiz.qpic.cn/mmbiz_png/tMsLbdfwxoNf32ByjOub2o7nFPYubBVyCqzkqePhzqevjWynubdBsLibvF62xnahbAib3APJ5pJetfJjXn6pbWiag/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)
   也就是可以用它来切换termux的背景颜色(默认都是纯黑嘛)

   ![图片](https://mmbiz.qpic.cn/mmbiz_jpg/tMsLbdfwxoNf32ByjOub2o7nFPYubBVy1vy5bARBibPz2IZKWrpvfkAkPDJU5hLayDticVfbI4ibf5KkaH3NCicPEg/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)
   总之如果按照以下步骤失败的尝试，换新版termux

   算是一个[**签名验证**](https://mp.weixin.qq.com/s?__biz=MzI4Nzc2MzA3OQ==&mid=2247485862&idx=2&sn=3aa960adeecfc9512e44f173273fcf4d&scene=21#wechat_redirect)

   安装完成之后打开termux

   长按空白处点击more

   ![图片](https://mmbiz.qpic.cn/mmbiz_png/tMsLbdfwxoNf32ByjOub2o7nFPYubBVyA2ib5U5MoGOCkzzI5I8ial62UemAibRdNfqGudSo6fzHIVe2ElrIFmwRQ/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)
   会弹出来termux的一些扩展选项

   ![图片](https://mmbiz.qpic.cn/mmbiz_png/tMsLbdfwxoNf32ByjOub2o7nFPYubBVy0ApRNDDqhzbw9Zl2MKvafbfVOPgUe8TGKHovicpWZ4cTHnDnmBmZ7CA/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

   点击style，就会弹出来一个框

   左边的是选择代码背景主题颜色

   右边是选择字体

   ![图片](https://mmbiz.qpic.cn/mmbiz_png/tMsLbdfwxoNf32ByjOub2o7nFPYubBVye8qHe6Hia24WZLvNMfRICR4fz5AZqibc5gL9icRiaAA5FMTibdBt3gjX3Cw/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

   ![图片](https://mmbiz.qpic.cn/mmbiz_png/tMsLbdfwxoNf32ByjOub2o7nFPYubBVyRluotoTdaZOgxUztfssDGalFl185jIWicFDllXwr3NqQb0j8MJMT4Hg/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)
   会出来一堆刚刚安好的style应用里的颜色，是以英文命名的，所以很难区分

   对照表一个可以对照着看

   http://www.ecomcn.com/tool/color_pick/

   fontstyle同理

   凑字:

   ------

   git config --global user.email "你的邮箱"

   git config --global user.name "你的用户名"

   也就是验证你本人

   git clone 

   克隆远程仓库到本地git@github.com:LianYiMing/SiteBuilding.git

   cd /storage/emulated/0/Download/Github/sitebuilding

   CD到目录好执行下面的

   git add .

   全选提交到缓存

   git commit -m

   把缓存提交到commit

   git push

   将commit push到远端仓库
