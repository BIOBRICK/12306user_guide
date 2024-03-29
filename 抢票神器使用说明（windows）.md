# 抢票神器使用说明（windows）

首先感谢GitHub大佬：https://github.com/testerSunshine/12306

如果各位有github账号，希望能去点个star。

然后正式开始：

### 1.环境配置

Win10（神舟战神天下第一！）

Python3.7.4（无conda）

Vscode（vscode天下第一！）

### 2.克隆项目到本地

一样，可以使用github desktop克隆到本地，也可以使用直接下载压缩包到本地，没有区别，下载好后，放到桌面。别问问什么（什么“能不能放D/E/F盘”，“我一般放在名叫‘软件’的文件夹里”之类的，不能，放别的地方后面出问题自己解决。），解压缩，进入其中的master文件夹，里面有着所有需要的项目源码。

其中，需要重点关注的同样是2个文件，第一个叫requirements.txt，第二个叫TickerConfig.py，前一个是配置环境需要的，后一个则是更改配置需要的。

网络不好的挂个梯子，找不到别的梯子的去下蓝灯中国。

### 3.下载需要的python模块

请使用python3的pip3下载，最好的是，系统里只有python3，软件需要3.6以上，版本自己注意，**python安装路径必须是默认路径不要改，加入系统PATH，不要有任何中文路径**。

```bash
python3 -m pip3 install -r requireements.txt
# pip3 install -r requirements.txt
```

请各位windos用户千万注意：

**其一，python给我装C盘；**

**其二，检查系统高级设置里面的PATH里到底有没有把python加进去；**

其三检查pip到底装了没；

**其四，不要有中文路径，不要有中文路径，不要用中文路径；**

其五，检查装没装chrome，下没下载对应版本的chromedriver

其六，上面任何一条，都可以百度得到解决方案，不要出一点问题就到处问来问去。

其七，上面任何一条，只要你会进行配置，没关系，怎么放都行，如果你不会，给我按照写的做，没有为什么。

利用requirements.txt下载的过程可能有点慢，而且需要下载tensorflow模块，可能有点慢，稍微等一会儿就好了。

全部下载完成而且不报错的话，环境配置就完成了。

### 4.写运行配置文件

首先，运行vscode，然后open folder，打开那个master文件夹，然后你会在右边看到所有文件都有了，单击就能查看更改，改完了记得保存......

配置文件就是TickerConfig.py，首先，这不是一个普通的txt配置文件，这是一个py脚本，不要乱空格换行打分号。然后，绝大多数配置文件的写法在里面注释描述得非常清楚，照着填就是，如果你担心什么“我的账号密码都写了会不会泄漏啊”，右转携程加速包10块一个，你去看看携程用户协议去。一般来讲，这里面会有些配置可能你看不懂是啥意思，没关系， 按照我填写的经验来看，一般你看不懂的就不用改。

不要问“能不能帮我写一下？”，答案是可以，**支付宝账户18819421160**.

在填写的时候，有些地方需要注意：

其一，先把输入法调成英文，别开着搜狗写了半天，报错然后问我为什么。

其二，如果你想开启邮箱通知，那么需要开stmp，其实很简单，先在QQ邮箱网页或者手机app上登陆，然后在设置里面找到开启stmp/pop服务，点开启就行，然后一堆验证照着验证就行，直到最后，会给你一个授权码，这个授权码要记好，在填写邮箱通知里面，password的部分，**不要写你的密码，写授权码**，然后地址注意后面要加上端口号，一般25端口就能用了。实现的具体原理感兴趣自己去查。

其三，日期，车次写对，然后12306记得确保认证通过，然后就是学生票的问题，目前看来，软件不支持改动，是这样的，如果你的乘车人里面有学生票信息，那么会默认买学生票，如果没有学生票信息，会买成人票，儿童票也一样，那么，我们可以这样，在购买人名单里，写两次名字，这样会买一张学生票买一张成人票，然后退就行了。

最后，就是chrome的问题。这里是windows，所以整起来路径其实还很简单，首先，确认chromedriver的文件夹放在C盘然后加入了系统的PATH，然后，在填chrome路径和chromedriver路径的时候，**注意windos端的路径是双斜杠而不是直接复制得来的“/”，这一点直接百度就能弄清楚，很简单**。

到此为止配置信息填写完成，可以开整了。

### 5. 运行

确认环境配置无误，然后就可以在文件夹里.

```bash
python3 run.py
#python run.py
```

然后等着就行，终端挂后台就行了，这玩意不吃资源，另外，如果你IP被封了不要找我，自己去买代理或者IP池，不要挂云上，云的IP封起来是最容易的，如果家庭网络自动获取IP是可以隔一段时间换个IP的，自己去搜索实现。

这里可能会出现一些问题，报错可能会说没有权限，可以将chromedriver.exe右键，在属性里面设置为“以管理员启动”，注意是设置属性，不是让你运行。

### 6.Q&A

1.为什么要在windows上写一个？

答：闲的，而且既然写了mac的，干脆也写个windos的算了。

2.我的selenium为什么又报错？

一般来讲，报错的原因都是因为fake_useragent.json这个文件下载的问题。建议是，第一次运行挂个梯子，这个文件很小，只有43k，只要下载一次就行了。实在不想挂梯子的话，去网上找个版本对应的，然后加入到pyhton的临时文件目录里。当然，也有可能是因为你没把chromedriver文件夹加入PATH，或者你没把chromedriver设置为始终以管理员运行。

3.配置文件这么多条，看不懂啊，能不能讲一下？

答：可以，**支付宝账户18819421160**，或者可以自己去免费百度，简单得很。另外，里面每条都有中文注释啊，你是看不懂中文？

4.我想用server酱微信通知，能不能......

答：不能，自己摸索去。

5.能不能帮我全套弄一下？我只想直接挂着等。

答：可以，支付宝账户......

6.能不能帮我代挂？我的电脑不想一直开着。

答：可以，支付宝......隔壁加速包10块一个你看着给吧。

7.能保证抢到票不？

答：现在放票一般是多次放票，一般来讲第一次只放少量票，在出发前一周会再有一次放票，以及平时可以捡漏，成功率还是很高的。不过，没有保证，你觉得携程和飞猪能保证么？无非就是抢不到退款而已，你在乎退款么。不怎么相信的话，可以自己手动等着去吧，另外，肯定会有人说候补，那么我告诉你，这个连候补机会都能一起抢。

8.效果咋样？

答：反正我抢到了......你自己看着办吧。

9.这个看起来跟之前那份mac的差不多啊？

答：那你照着那个干呗，看看能不能干出来，另外，实现原理反正都是一样的。

10.12306的源码包和tensorflow包下不动啊！

答：挂梯子去，别问我什么手动安装python的module，自己去csdn搜大佬教程。

11.我用的conda请问怎么配置？

答：都用conda了，虚拟环境整的溜了，我觉得也不需要从我这个渣渣教程里学怎么配，如果你说还需要，那我建议你彻底卸载conda，你用不上。

12.我不是win10/神舟能用不？

答：可以，python版本差不多就行。

13.python2.7行不？

答：不行，官方说2.7明年1月失去支持，建议换3。当然，用是可以用的，但不提供教程，其实也差不多的。

14.终端好丑啊！

答：cmder了解一下？