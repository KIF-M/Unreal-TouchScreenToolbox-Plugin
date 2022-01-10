# Unreal 触控屏工具箱操作文档



## 目录

[TOC]

## 插件编译环境

+ Windows 10

+ Unreal 4.26.2
+ Visual Studio 2019



## 插件使用

+ 将插件压缩包解压

  ![image-20220110235416046](README.assets/image-20220110235416046.png)

  ![image-20220110235532444](README.assets/image-20220110235532444.png)

  

+ 将TouchScreenToolbox放到使用项目的插件文件夹中  如果没有，新建文件夹

  ![image-20220110235838284](README.assets/image-20220110235838284.png)

  ![image-20220110235934133](README.assets/image-20220110235934133.png)

  

+ 打开插件， 选择Project -> KIF  开启插件  重启Unreal

  ![image-20220111000130062](README.assets/image-20220111000130062.png)

  

+ 打开Content

  ![image-20220111000329739](README.assets/image-20220111000329739.png)



## 模块总览

+ 插件界面

  ![image-20220110020452870](README.assets/image-20220110020452870.png)

  

+ 插件Content

  ![image-20220110020643205](README.assets/image-20220110020643205.png)

  ![image-20220110020729659](README.assets/image-20220110020729659.png)

  ![image-20220110020800384](README.assets/image-20220110020800384.png)

  ![image-20220110020846398](README.assets/image-20220110020846398.png)

  ![image-20220110020915367](README.assets/image-20220110020915367.png)

  ![image-20220110020942974](README.assets/image-20220110020942974.png)

  ![image-20220110021011339](README.assets/image-20220110021011339.png)

  ![image-20220110021100307](README.assets/image-20220110021100307.png)

  

+ 插件C++

  ![image-20220110021336007](README.assets/image-20220110021336007.png)

  ![image-20220110022606821](README.assets/image-20220110022606821.png)

  ![image-20220110022628574](README.assets/image-20220110022628574.png)

  ![image-20220110022648144](README.assets/image-20220110022648144.png)

  ![image-20220110022725189](README.assets/image-20220110022725189.png)

  ![image-20220110022757073](README.assets/image-20220110022757073.png)

  ![image-20220110022842537](README.assets/image-20220110022842537.png)



## 功能模块

### TouchScreenGameMode

+ Content

  ![image-20220110065259049](README.assets/image-20220110065259049.png)

  

+ 功能描述

  + 触控屏游戏模式
  + 支持鼠标点击
  + 关闭视角移动
  + 关闭飞行位移
  + 

+ 样例

  + 切换到WorldSetting

    ![image-20220110065505345](README.assets/image-20220110065505345.png)

    

  + 选择游戏模式为BPTouchScreenGameMode  子模式选择对应的BPTouchScreenClass

    ![image-20220110065647000](README.assets/image-20220110065647000.png)
  
    

### GlobalChangeText3D

+ Content

  ![image-20220110032142193](README.assets/image-20220110032142193.png)

  

  ![image-20220110032204523](README.assets/image-20220110032204523.png)

  

+ 功能描述

  + 全局修改自定义3D Text 组件
  + 注册 ID标识 ，通过注册ID整体修改
  + 支持关卡蓝图、子蓝图调用
  + 

+ 样例

  + 场景中拖入BPGlobalChangeText3DActor,设置注册ID（Global Change Text ID）  

    ![image-20220110033102961](README.assets/image-20220110033102961.png)

    ![image-20220110033132646](README.assets/image-20220110033132646.png)

    

  + 调用蓝图函数  SetGlobalChangeText3D    

    ![image-20220110030538005](README.assets/image-20220110030538005.png)

    ![image-20220110030617704](README.assets/image-20220110030617704.png)

    

  + GlobalChangeTextArray  为FString数组  数组中FString格式为  ID|Msg     ID为 注册ID（Global Change Text ID）  |为分割符   Msg为显示文本

    ![image-20220110031436879](README.assets/image-20220110031436879.png)

    
  
  + 运行结果
  
    ![image-20220110033229589](README.assets/image-20220110033229589.png)



### GlobalChangeImage

+ Content

  ![image-20220110032446135](README.assets/image-20220110032446135.png)

  ![image-20220110032511005](README.assets/image-20220110032511005.png)

  ![image-20220110032550619](README.assets/image-20220110032550619.png)

  ![image-20220110032613389](README.assets/image-20220110032613389.png)

  

+ 功能描述
  + 全局修改自定义动态Material组件
  
  + 注册 ID标识 ，通过注册ID整体修改

  + 支持关卡蓝图、子蓝图调用
  
    
  
+ 样例
  + 场景中拖入BPGlobalChangeImageActor,设置注册ID（Global Change Image ID）  

    ![image-20220110060811598](README.assets/image-20220110060811598.png)

    ![image-20220110060836987](README.assets/image-20220110060836987.png)

    

  + 调用蓝图函数  SetGlobalChangeImage  

    ![image-20220110060942342](README.assets/image-20220110060942342.png)

    ![image-20220110061026513](README.assets/image-20220110061026513.png)

    

  + GlobalChangeImageDataArray  为FString数组  数组中FString格式为  ID|ImageName   

  + ID为 注册ID（Global Change Image ID）  |为分割符   ImageName为图片名称（含后缀）

  + GlobalChangeImagePath  为图片路径

    ![image-20220110061528436](README.assets/image-20220110061528436.png)

    ![image-20220110061601368](README.assets/image-20220110061601368.png)

    ![image-20220110061742252](README.assets/image-20220110061742252.png)

    ![image-20220110062220258](README.assets/image-20220110062220258.png)

    

  + 运行结果
  
    ![image-20220110062641199](README.assets/image-20220110062641199.png)
  
  
  
+ 自定义材质更换

  + 新建材质，创建 Texture Sample  选择默认Texture

    ![image-20220110063537979](README.assets/image-20220110063537979.png)

    

  + 将节点转换成param

    ![image-20220110063657064](README.assets/image-20220110063657064.png)

    

  + 参数名称改成T_GlobalChangeImage

    ![image-20220110063910514](README.assets/image-20220110063910514.png)

    
  
  + 最终将自定义的材质拖拽到BPGlobalChangeImageActor的材质球上
  
    ![image-20220110064141274](README.assets/image-20220110064141274.png)
  
  + ==注： 自定义材质在含有Texture Sample的param节点，参数名为T_GlobalChangeImage  且该材质为材质列表的第一个材质时生效==
  
    

### FileJsonTxtManager

+ Content

  ![image-20220110070457342](README.assets/image-20220110070457342.png)

  

+ 功能描述
  + 读取Json/Txt文件
  
  + 解析JsonObject
  
  + 解析JsonObjectArray
  
  + 解析JsonValue
  
    
  
+ 样例

  + TXT解析 ParseTxtFileFromDisk 

    + 输入txt路径  txt名字（带后缀）  返回FString数组    按照换行分割

      ![image-20220110074043018](README.assets/image-20220110074043018.png)

      <img src="README.assets/image-20220110074241255.png" alt="image-20220110074241255" style="zoom:67%;" />

      

    + 演示

      ![image-20220110074830782](README.assets/image-20220110074830782.png)

      

    + 运行结果

      ![image-20220110074905451](README.assets/image-20220110074905451.png)

      

  + Json解析 ParseJsonFileFromDisk

    + 输入Json路径  Json名字(带后缀)  返回 JsonObject

      ![image-20220110075234223](README.assets/image-20220110075234223.png)

      ![image-20220110075404667](README.assets/image-20220110075404667.png)

      

    + 演示

      ![image-20220110081035211](README.assets/image-20220110081035211.png)

      

    + 运行结果

      ![image-20220110081116055](README.assets/image-20220110081116055.png)

      

  + Json解析Value  TryGetValueField

    + 输入 JsonObject   字段名称   返回字段对应值

      ![image-20220110081438402](README.assets/image-20220110081438402.png)

      ![image-20220110081811463](README.assets/image-20220110081811463.png)

      

    + 演示

      ![image-20220110081735915](README.assets/image-20220110081735915.png)

      

    + 运行结果

      ![image-20220110081845474](README.assets/image-20220110081845474.png)

      

  + Json解析JsonObject  TryGetObjectField

    + 输入JsonObject  字段名称   返回 JsonObject

      ![image-20220110082513262](README.assets/image-20220110082513262.png)

      ![image-20220110082541382](README.assets/image-20220110082541382.png)

      

    + 演示

      ![image-20220110083658208](README.assets/image-20220110083658208.png)

      

    + 运行结果

      ![image-20220110083725714](README.assets/image-20220110083725714.png)

      

  + Json解析JsonArray  TryGetArrayField

    + 输入JsonObject  字段名称   返回 JsonArray

      ![image-20220110082614869](README.assets/image-20220110082614869.png)

      ![image-20220110082634674](README.assets/image-20220110082634674.png)

      

    + 演示

      ![image-20220110083927576](README.assets/image-20220110083927576.png)

      

    + 运行结果

      ![image-20220110083945859](README.assets/image-20220110083945859.png)
      
      

  + JsonObject 转 Json FString   JsonObjectToJsonFstring

    + 输入JsonObject     返回 Json FString

      ![image-20220110083249488](README.assets/image-20220110083249488.png)

      ![image-20220110083305850](README.assets/image-20220110083305850.png)

      

    + 演示

      ![image-20220110084023056](README.assets/image-20220110084023056.png)

      

    + 运行结果

      ![image-20220110084044748](README.assets/image-20220110084044748.png)
      
      

  + Json FString 转 JsonObject   JsonFStringToJsonObject

    + 输入Json FString  字段名称   返回 JsonObject

      ![image-20220110083402314](README.assets/image-20220110083402314.png)

      ![image-20220110083427413](README.assets/image-20220110083427413.png)

      

    + 演示

      ![image-20220110084137940](README.assets/image-20220110084137940.png)

      
    
    + 运行结果
    
      ![image-20220110084155366](README.assets/image-20220110084155366.png)
      
      

+ ==注：浮点类型算小数点最多存放8位，超出范围数据会与源数据不同==



### VideoControlManager

+ Content

  ![image-20220110205805295](README.assets/image-20220110205805295.png)

  ![image-20220110205844779](README.assets/image-20220110205844779.png)

  ![image-20220110205911609](README.assets/image-20220110205911609.png)

  ![image-20220110205942056](README.assets/image-20220110205942056.png)

  ![image-20220110210005696](README.assets/image-20220110210005696.png)

  

+ 功能描述

  + 自定义视频播放组件

  + 支持读写本地及局域网文件

  + 视频控制器组件

  + 支持视频播放、暂停、进度条、跳帧

  + 支持多窗口同视频流及不同视频流

  + 解决二维鼠标相对坐标问题，转为三维空间射线碰撞运算

    

+ 样例

  + 游戏模式更改成触控屏模式

    ![image-20220110210444063](README.assets/image-20220110210444063.png)

    

  + 将BPVideoControl拖拽到场景

    ![image-20220110210807916](README.assets/image-20220110210807916.png)

    

  + 将场景树中将BPVideoControl拖拽到关卡蓝图中初始化  InitVideoControl   输入为视频路径  视频列表的文件名（带后缀）   视频初始化的下标

    ![image-20220110211107931](README.assets/image-20220110211107931.png)

    ![image-20220110211134104](README.assets/image-20220110211134104.png)

    ![image-20220110211232779](README.assets/image-20220110211232779.png)

    

  + 演示

    ![image-20220110211532813](README.assets/image-20220110211532813.png)

    

  + 运行效果

    ![image-20220110211557173](README.assets/image-20220110211557173.png)

    ![image-20220110211618505](README.assets/image-20220110211618505.png)

    ![image-20220110211639220](README.assets/image-20220110211639220.png)

    ![image-20220110211708039](README.assets/image-20220110211708039.png)

    


+ 新增新的MediaPlayer

  + 复制VideoControlMediaPlayer    VideoControlVideoTexture    M_VideoControlMaterial  

    ![image-20220110212025628](README.assets/image-20220110212025628.png)

    ![image-20220110212047787](README.assets/image-20220110212047787.png)

    ![image-20220110212122406](README.assets/image-20220110212122406.png)

    

  + Texture 中更改MediaPlayer

    ![image-20220110212233841](README.assets/image-20220110212233841.png)

    

  + Meterial 中设置 Texture

    ![image-20220110212334304](README.assets/image-20220110212334304.png)

    

  + 选择场景中的BPVideoControl  点击组件根级 设置 MediaPlayer  

    ![image-20220110212724717](README.assets/image-20220110212724717.png)

    

  + 选择场景中的BPVideoControl  点击组件中VideoStaticMesh   设置 Material

    ![image-20220110213102761](README.assets/image-20220110213102761.png)

    

  + 选择场景中的BPVideoControl  点击组件中MediaSound   设置 Media Player

    ![image-20220110213204571](README.assets/image-20220110213204571.png)



+ ==注：触控采用3D射线碰撞实现，所以触控区域前方不能有其他物体遮挡==



### LevelSequenceControlManager

+ Content

  ![image-20220110214553041](README.assets/image-20220110214553041.png)

  

+ 功能描述

  + 支持关卡序列异步播放、暂停、倒放、延时
  + 支持批量控制 共七种控制类型
    + 初始化
    + 正向播放
    + 倒放
    + 播放到固定时间
    + 跳转到固定时间
    + 播放到某个标记帧
    + 跳转到某个标记帧

+ 样例

  + 关卡序列设置  将所有动画设置 When Finished  设置成 Keep State

    ![image-20220110215702737](README.assets/image-20220110215702737.png)

    

  + 插入标记   右键选择Add Mark

    ![image-20220110220213229](README.assets/image-20220110220213229.png)

    ![image-20220110220329140](README.assets/image-20220110220329140.png)

    

  + 将BPLevelSequenceControlActor拖拽到场景中，设置控制的关卡序列  设置 LevelSequence Control ID

    ![image-20220110220054662](README.assets/image-20220110220054662.png)

    

  + 关卡序列控制  ControlGlobalLevelSequence

    ![image-20220110224329980](README.assets/image-20220110224329980.png)

    ![image-20220110230826279](README.assets/image-20220110230826279.png)

    + 输入  GlobalControlLevelSwquence Data Array   控制 LevelSequence Control ID  列表

      ![image-20220110224629052](README.assets/image-20220110224629052.png)

      

    + 输入  Control Type  控制的类型 

      ![image-20220110224730782](README.assets/image-20220110224730782.png)

      + Init   归零
      + Play  正向播放
      + Play Reverse  倒放
      + Play to by Time   播放到某个时间
      + Play to by Marded Frame Index  播放到标记帧  通过下标
      + Jump to by Time   跳转到某个时间
      + Jump to by Marded Frame Index 跳转到标记帧  通过下标

    + 输入  Control Time

      + 在 Play to by Time、Jump to by Time中生效

    + 输入  Control Marded Frame Index 

      + 在Play to by Marded Frame Index、Jump to by Marded Frame Index中生效

        

  + 演示

    ![image-20220110230952636](README.assets/image-20220110230952636.png)

    

  + 运行效果

    ![image-20220110225636089](README.assets/image-20220110225636089.png)

    ![image-20220110225659512](README.assets/image-20220110225659512.png)

    ![image-20220110225718424](README.assets/image-20220110225718424.png)

    

+ ==注：关卡序列运行时需把所有关卡序列的窗口关闭，否则会占有控制状态==

  

### DrawBoardManager

+ Content

  ![image-20220110231117321](README.assets/image-20220110231117321.png)

  ![image-20220110231141003](README.assets/image-20220110231141003.png)

  ![image-20220110231203466](README.assets/image-20220110231203466.png)

  

+ 功能描述

  + 画板模块

  + 支持在指定区域 使用画笔或箭头

  + 支持撤销及清空功能

  + 画板空间计算采用三维坐标计算

    

+ 样例

  + 游戏模式更改成触控屏模式

    ![image-20220110210444063](README.assets/image-20220110210444063.png)

    

  + 将DrawBoard拖拽到场景中

    ![image-20220110231403009](README.assets/image-20220110231403009.png)

    

  + 将DrawBoardArrow拖拽到场景中

    ![image-20220110231505247](README.assets/image-20220110231505247.png)

    

  + 将DrawBoardLines拖拽到场景中

    ![image-20220110231530737](README.assets/image-20220110231530737.png)

    

  + DrawBoard中选择 DrawBoardArrow  DrawBoardLines

    ![image-20220110231638964](README.assets/image-20220110231638964.png)

    

  + 运行效果

    ![image-20220110231734281](README.assets/image-20220110231734281.png)

    

+ ==注：触控采用3D射线碰撞实现，所以触控区域前方不能有其他物体遮挡==

  

### ResourceManager

+ Content

  ![image-20220110232342524](README.assets/image-20220110232342524.png)

  

+ 功能描述

  + 本地化存储管理模块
  + 将自定义变量以SaveGame格式本地化存储， 保存后下次开启可得到最终保存数据
  + 支持文件选取及文件夹选取

+ 样例

  + 选取文件夹  GetDialogDirectory

    ![image-20220110232515295](README.assets/image-20220110232515295.png)

    ![image-20220110232543940](README.assets/image-20220110232543940.png)

    

    + 演示

      ![image-20220110232626558](README.assets/image-20220110232626558.png)

    

    + 运行结果

      ![image-20220110232755814](README.assets/image-20220110232755814.png)

      ![image-20220110232810914](README.assets/image-20220110232810914.png)

    

  + 选取文件 GetDialogFile

    ![image-20220110233031780](README.assets/image-20220110233031780.png)

    ![image-20220110233227941](README.assets/image-20220110233227941.png)

    

    + 演示

      ![image-20220110233250452](README.assets/image-20220110233250452.png)

      

    + 运行结果

      ![image-20220110233342762](README.assets/image-20220110233342762.png)

      ![image-20220110233357523](README.assets/image-20220110233357523.png)

      

  + 拖拽BP_ResourceManager到场景中

    ![image-20220110233518787](README.assets/image-20220110233518787.png)

    

    + 按Tab键显示全局资源

      ![image-20220110233609580](README.assets/image-20220110233609580.png)

      

    + 点击Save保存  点击Close关闭

      ![image-20220110233655352](README.assets/image-20220110233655352.png)

      

+ 添加新的本地化数据

  

  + 打开BP_SaveGameData  新添加数据变量

    ![image-20220110233830806](README.assets/image-20220110233830806.png)

    

  + 打开BP_ResourceManagerWidget  中事件

    

    + 在 Event Construct 中初始化

      ![image-20220110234021560](README.assets/image-20220110234021560.png)

      

    + 保存   设置SaveGame中数据  然后保存数据

      ![image-20220110234143818](README.assets/image-20220110234143818.png)

    
