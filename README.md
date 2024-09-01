	一、标题写法：
第一种方法：
1、在文本下面加上 等于号 = ，那么上方的文本就变成了大标题。等于号的个数无限制，但一定要大于0个哦。。
2、在文本下面加上 下划线 - ，那么上方的文本就变成了中标题，同样的 下划线个数无限制。
3、要想输入=号，上面有文本而不让其转化为大标题，则需要在两者之间加一个空行。
另一种方法：（推荐这种方法；注意⚠️中间需要有一个空格）
关于标题还有等级表示法，分为六个等级，显示的文本大小依次减小。不同等级之间是以井号  #  的个数来标识的。一级标题有一个 #，二级标题有两个# ，以此类推。
例如：
# 一级标题  
## 二级标题  
### 三级标题  
#### 四级标题  
##### 五级标题  
###### 六级标题 

————————————————

# 任务书
## 任务要求
	本任务是设计并实现一款一人一题抢答器电路，具体要求如下：
	1.采用 Multsim 设计一个抢答电路和倒计时电路，实现能同时供一人抢答一题。
	2.主持人有控制开关，可以手动清零复位。当主持人按下开始按键时才可以抢答。显示倒计时10秒，规定时间内抢答有效，同时倒计时停止，直到主持人将系统清零为止。
	3.当倒计时为“00”后选手答题超时，会有 LED 亮起，提示超时。
	4.电路必须能够通过硬件电路实现，不得采用微处理器编程实现。
 ## 任务背景
  现在需要设计并实现一款抢答器电路，用于供学生进行课堂互动和竞赛等活动。这款电路需要能够同时供一人抢答一题，并且主持人可以预置抢答后选手作答时间。电路必须能够通过硬件电路实现，不得采用微处理器编程实现。此外，硬件验证时需要标注姓名和学号，以便于任务评审。
## 实现情况
1.实现了抢答功能，主持人按开始抢答后可以抢答，并开始十秒倒计时，当一人抢答完抢答倒计时停止且其他人不能抢答。
2.在十秒内无人抢答时会有 LED 报警提示。
3.有选手抢答后，答题倒计时开始，答题倒计时由主持人设定，答题倒计时结束后红灯亮起，表示答题超时。
## 摘要
  本次课设旨在设计一个七人抢答电路，实现多人抢答、倒计时、报警等功能。采用Multisim仿真电路进行设计，用嘉立创PCB打板实现硬件验证。主要方法是通过逻辑电路的设计，实现多人抢答和倒计时功能，同时在硬件实现中加入LED报警功能。在实验过程中，成功实现了抢答、倒计时、报警等功能，并经过了嘉立创PCB硬件验证。设计的主要创新点在于实现了多人抢答的同时，添加了倒计时和报警功能，使得整个系统更加完善。通过本次课设的设计和实现，验证了逻辑电路设计的可行性，同时提高了个人的实践能力和创新思维能力。



# 一、系统设计

总体设计方案比较
	第一种：
分为三个模块：
抢答模块；倒计时分为主持人自定义倒计时；抢答十秒倒计时
第二种：分为两个模块：
	抢答模块；抢答十秒倒计时和主持人自定义倒计时共用一个模块
	选择了第一种，理由：
第一种逻辑性更简单，设计起来更不耗时间。第二种需要在十秒倒计时和自定义倒计时之间切换，中间数据保存可能需要更多芯片，反而增大工作量。
主持人自定义倒计时时间方案
	1.是拨码开关设定时间，
	2.是用按键累加设定时间。
	我认为使用按键累加的方案较好
	拨码开关为多输入，需要更多芯片更多线路，更大的空间，工程量变大。拨码开关占用较大体积，不利于板子小型化，而使用按键累加的方案只要一个按键就可以达到好几个拨码开关才能达到的效果。
硬件实现方案
	1.使用洞洞板飞线焊接
	2.使用腐蚀覆铜板完成
	3.使用PCB工厂打板
	选择第三种
		1.完成电路的仿真设计后我发现线路过于繁琐，光五个数码管就要接五个译码器三十几根线。所以洞洞板的可实现度太低，并且不符合生产生活实际。这是之前的模电课设，一个简单的ocl功率放大电路就占了很多空间，可见用洞洞板制作可实现性不高。![image](https://github.com/user-attachments/assets/06d120c4-5292-4b07-92fe-2de016baa26f)

