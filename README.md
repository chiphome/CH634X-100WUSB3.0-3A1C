# CH634X-100WUSB3.0-3A1C
CH634X芯片做的100W快充 + USB3.0高速传输（3A1C）PD HUB

![bcbccf7359b1692e641148ebdd1c60ad](https://github.com/user-attachments/assets/8e6b70dd-456a-403b-b742-fd27e5f1b5e4)

在日常开发中，USB HUB几乎是必不可少的工具，最近刚好需要一个HUB，作为一个电子工程师，我决定自己动手，设计并打造了一款自己的HUB，基于这个过程，顺便温习一下USB、PD的一些知识，如果大家有兴趣，咱们可以一起学习。

说一下我的情况，我的电脑只有2个Type-C口，所以设计的HUB必须支持快充，C口转A口最好有3个，额外再多一个C口更好。

![ce3a1c8411e7a496146c697b6e25c82e](https://github.com/user-attachments/assets/64369238-cdad-47f3-b532-03f55ad7f217)

网上找了一圈，最终选定了沁恒微的CH634X这颗芯片做了一款HUB，已经打样测试完，现在决定全部资料开源给大家进行复刻。

🔧 项目简介：

一款为开发者量身定做的 USB HUB，整个USB HUB项目包含以下接口配置：

1、上行 Type-C 口：接入电脑主机，承担数据传输与充电功能

2、独立供电 Type-C 口：支持最大100W PD快充输入（20V/5A）

3、1个USB-C下行接口：连接USB-C设备实现高速通信

4、3个 USB-A下行接口：完美兼容鼠标、键盘、U盘、调试器等外设

所有的接口，都做了电源管理，安全稳定，支持边充边用、盲插盲用。

为什么选 CH634X？

CH634X芯片是一款带PD功能的高性能 USB3.0 控制芯片，主要性能特点：

1、单芯片集成4口USB3.2 Gen1(5Gbps) HUB和Type-C PD功能

2、原生支持Type-C电源100W快充，支持PDHUB和拓展坞

3、内置两组Type-C双通道 USB3.0 PHY和双PD PHY，原生支持Type-C正反插自适应

4、具有独立的SS HUB控制器和USB2.0 HUB控制器

5、支持 Type-C 上下行口热插拔识别与角色切换，便于2个主机管理多个设备

6、集成了3.3V的LDO调压器和1.2V的DC-DC降压器，支持外部5V电源供电，外围精简

7、支持通过I/O引脚配置独立或整体控制、供电模式等功能

8、封装小巧，适合各种紧凑布局

<img width="1200" height="820" alt="b80117e6-9387-49b2-9819-d8cde15263a5" src="https://github.com/user-attachments/assets/8bea8eef-ecd8-4f9c-92ab-5b88e57628d3" />

最关键的是：国产、自研、文档齐全，易于上手！

项目架构图&PCB预览

接口配置：

<img width="1704" height="626" alt="Snipaste_2025-08-06_22-08-11" src="https://github.com/user-attachments/assets/4e2dfdc0-5d23-4546-a278-ed9ed25a2c3c" />

原理图，具体原理分析下一篇文章介绍：

<img width="1920" height="870" alt="SCH_CH634X-PD-R0-1v1A_1-CH634X-PD-R0-1v1A_2025-08-07" src="https://github.com/user-attachments/assets/d605e9f7-7d4f-4979-8c03-3133c2d8f8a6" />

PCB用立创EDA制作，采用4层板设计，专门优化了电源走线与高速信号完整性。

<img width="1339" height="720" alt="Snipaste_2025-08-07_21-01-03" src="https://github.com/user-attachments/assets/c06ff26a-638b-416e-bef4-de179a11dc1d" />

PCB 3D

<img width="1487" height="766" alt="Snipaste_2025-08-07_21-09-59" src="https://github.com/user-attachments/assets/090c3736-938e-43c3-b775-c7689afbe7bb" />

外壳文件，外壳提供STP格式，大家可以3D打印，外壳还有很多优化空间。

![b57ac5e0cf575fdb12473ac2b80c06bb](https://github.com/user-attachments/assets/f0423f5f-b291-42ae-9132-c0d6f0cfabd0)

提供交互式BOM清单，以及excel版本的BOM，PCB工程中就已经包含了标准化元器件信息，99%的器件均可在立创商城直接找到。

<img width="2405" height="1163" alt="Snipaste_2025-08-07_21-13-05" src="https://github.com/user-attachments/assets/ba7aae7c-baa4-4805-9935-49086a4025e3" />

PCB为4层板，USB涉及到的高速信号需要走差分信号，并进行阻抗管控，层压结构采用嘉立创 JLC04161H-3313，阻抗管控，免费的±20%。

<img width="1104" height="490" alt="51ed610ea196499222fcb1e0d58c3bfd" src="https://github.com/user-attachments/assets/10376f58-665b-42ff-9485-e1148bfbf8be" />

⚡ 实测效果：PD快充 + 高速传输一个不落！

💻 插入Windows电脑测试，PD握手成功，支持 20V/5A 快充

🚀 同时连接U盘/调试器/外设，USB3.0速度可达400MB/s+

🔌 使用小米/Anker/绿联等主流PD充电器，均握手无压力

📱 给手机、笔记本充电 + 外设传输，边用边充非常流畅

Windows系统 HP电脑电量10%以下充电功率能达到95W。

![15295ae347ca00ae9c601f69119ef222](https://github.com/user-attachments/assets/ed37a674-cdef-4c6b-8d64-4d25ba5c94b1)

MAC系统 18款macbook pro电量10%以下充电功率能达到58W，新款MAC支持到100W应该没问题。

![97588eadf752a5da45506af6988280b0](https://github.com/user-attachments/assets/ee278270-2417-4ec4-8864-5029087ae7d4)

Type-A口高速传输测试，固态硬盘采用闪迪 500GB NVMe固态硬盘，Type-C接口，最高速度1050MB/s，远高于USB3.2 Gen1（5Gbps）的速度，所以用这个SSD测试就能测试出USB口的最大传输速度，实际不同的电脑测试出来的结果会有一些差别,本次测试电脑型号为OptiPlex 7080。

测试软件用CrystalDiskMark8_0_6Aoi，测试结果如下：

固态硬盘直连电脑测试，读828MB/s，写833MB/s：

<img width="1002" height="552" alt="5fb19ae172b27eedad27e1608d564398" src="https://github.com/user-attachments/assets/31ef545a-4760-44e8-9615-3a792e39b2de" />

经过Hub后A口测试，读448MB/s，写446MB/s：

<img width="1002" height="552" alt="9f602b78e34173029b9afdeb7f088027" src="https://github.com/user-attachments/assets/32d07d34-4e20-48c3-b9f4-64a131f4ef68" />

经过Hub后C口测试，读448MB/s，写446MB/s：

<img width="1002" height="552" alt="8f730b265e7b2e1171c0086d2a173663" src="https://github.com/user-attachments/assets/a6b90db2-61ff-4f3e-a508-a4707841691d" />

完全开源，欢迎大家 Fork & DIY

我会将整个项目的内容发布到立创开源硬件平台，包括：

✅ 原理图设计+4层PCB（立创EDA）

✅ 3D外壳模型（塑料外壳+铝合金可选）

✅ BOM物料清单

✅ 原理分析

大家搜“100W快充+USB3.0（3A+1C）高速传输 PD HUB”就可以找到项目，可以很方便的进行复刻，相关外壳3D，BOM,原理图PCB等文件都可以从这里下载。
https://oshwhub.com/karaxiaoyu/ch634x-pd-r0-1v1_20250808

<img width="1155" height="462" alt="2a50b48fd187012e1b65d90dd20057a" src="https://github.com/user-attachments/assets/6593bc9a-8036-42db-aa6f-1f84fa22e3e7" />

为什么我要开源这个项目？

与其等，不如自己做；与其藏，不如分享。

这正是这个项目的初衷 —— 用开源推动国产芯片更广泛应用，也让更多电子爱好者可以低成本DIY一个实用的桌面工具。

![e311dd5fef292941c57d9ddc25b08a0e](https://github.com/user-attachments/assets/cfb94276-7cff-465d-8bf6-6129c1abf239)

读到这里的都是忠实的粉丝了，大家一键三连点赞👍支持下国产芯片和开源项目。

留言交流🗨️提出想法、建议、改进点。

分享扩散 🚀 让更多朋友加入到国产芯片生态中！

你觉得这样的HUB实用吗？文章下面留言告诉我，我将抽1位幸运粉丝送出一个实物样品！🎁

因为篇幅问题，本篇我们先把项目开源出来，下一篇我们重点分析下整个板子的工作原理，芯片大概是怎么工作的，PD是怎么握手的，再重点分析。
