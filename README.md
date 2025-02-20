# NETFLIX-VERIFY

流媒体NetFlix解锁检测脚本，使用Go语言编写。

在VPS网络正常的情况下，哪怕是双栈网络也可在几秒内快速完成IPv4/IPv6的NF解锁情况判断。

## 其他常见流媒体脚本链接

DisneyPlus 解锁检测： https://github.com/sjlleo/VerifyDisneyPlus

Youtube 缓存节点、地域信息检测：https://github.com/sjlleo/TubeCheck

## 更多实用脚本

> 脚本排名不分先后，各有其优势，大家各取所需~

### 各类脚本快捷镜像托管

#### KEA 可爱萌镜像托管站：[KEA.MOE](https://kea.moe)

我们现在正在收集脚本，如果您的脚本也想被收入，请联系 [@sjlleo](https://t.me/sjlleo)

**Telegram 交流群组：[KEA Source](https://t.me/keamoe)**（欢迎所有玩VPS的爱好者和对国内到国际路由的研究爱好者加入）

### 网络工具类

#### 一、Ehco 隧道

1. Ehco 隧道一键配置脚本（[@missuo](https://github.com/missuo)）：https://github.com/missuo/Ehcoo
2. Ehco 隧道一键配置脚本 v2（[@sjlleo](https://github.com/sjlleo)）：https://github.com/sjlleo/ehco.sh

#### 二、Gost 隧道

1. Gost 隧道一键配置脚本（[@KANIKIG](https://github.com/KANIKIG)） ：https://github.com/KANIKIG/Multi-EasyGost 

### Cloudflare Warp类

1. Cloudflare Warp 一键脚本（[@P3TERX](https://github.com/P3TERX)）：https://github.com/P3TERX/warp.sh

2. Cloudflare Warp 一键脚本（[@missuo](https://github.com/missuo)）：https://github.com/missuo/CloudflareWarp

3. Cloudflare Warp 一键脚本（[@YG-tsj](https://github.com/YG-tsj)）：https://github.com/YG-tsj/Oracle-warp


## Bug反馈途径

1. 发起一个新的`Issue`
2. 加入TG群组：https://t.me/keamoe

## 新特性

在`v2.51`版本中提供了2种不同的模式，将显示完全不同的结果：

* 运行`./nf -method full`将专门为发烧友准备的利器，显示更全面的结果
* 而普通用户当以缺省参数运行`./nf`或者是`./nf -method lite`将显示更轻量级的结果，显示更加友好

在`v2.6`版本中提供了自定义解锁功能，运行`./nf -custom 想测试的电影ID号`即可查看特定影片是否在该网络上解锁

![image](https://user-images.githubusercontent.com/13616352/112000509-06f4f880-8b59-11eb-8353-11268b789bde.png)

## 鸣谢

1. 感谢 [@CoiaPrant](https://github.com/CoiaPrant) 指出对于地域检测更简便的方法
2. 感谢 [@XmJwit](https://github.com/XmJwit) 解决了IPV6 Only VPS无法下载脚本的问题
3. 感谢 [@samleong123](https://github.com/samleong123) 指出了文档的解释缺陷
4. 感谢 [@ymcoming](https://github.com/ymcoming) 指出了IPv6的检测Bug

## 功能实现

- [X] 解锁情况判断
- [X] 地域信息显示
- [X] 双栈网络测试
- [ ] 半解锁检测（待实现）

## 相关名词解释

1. **不提供服务** - 所在的地区NF没开通，连自制剧也看不了
2. **宽松版权** - 有些NF拍摄的影片不是特别注重版权，所以限制放的很开
3. **解锁自制剧** - 代表可以看由NF自己拍摄的影片
4. **解锁非自制剧** - 代表可以看NF买下的第三方版权影片
5. **地域解锁** - NF在不同的地区可以看的片源都是不同的，有些影片只能在特定区观看

一般来说，需要能看非自制剧才算真正意义上的NF解锁

## 使用方法

1. 部署 `golang` 环境，执行 `go run nf.go` 运行本小应用

2. 懒人一键运行包（使用编译好的二进制文件执行本小程序）

   * Github主站下载链接（适用于IPv4网络的机器）:
   
   * **X86_64**：

   ```shell
   wget -O nf https://github.com/sjlleo/netflix-verify/releases/download/2.6/nf_2.6_linux_amd64 && chmod +x nf && clear && ./nf
   ```
   
   * CDN下载链接（通用选项，既适用于有IPv4网络的机器也适用于仅有IPv6网络的机器）:

   ```shell
   wget -O nf https://cdn.jsdelivr.net/gh/sjlleo/netflix-verify/CDNRelease/nf_2.60_linux_amd64 && chmod +x nf && clear && ./nf
   ```
   
   * **ARM64**：
   ```shell
   wget -O nf https://github.com/sjlleo/netflix-verify/releases/download/2.6/nf_2.6_linux_arm64 && chmod +x nf && clear && ./nf
   ```



## 效果演示图

### 简约模式

<img width="430" alt="Lite Method" src="https://user-images.githubusercontent.com/13616352/110296950-e479c000-802d-11eb-9837-e23392860b07.png">

## 提醒

在观看Netflix影片，有一种情况极少遇到，那就是“**半解锁**”，可以观看一部分的非自制剧，却不会显示任何地域排行榜有关的信息。

这种情况由于太少见以至于**很容易被忽略**，我会在未来认真研究它，以推出更健壮的检测脚本。如果您手里有可以半解锁Netflix的机器，欢迎联系我测试，我会将您的名字加入鸣谢名单中，非常感谢。
