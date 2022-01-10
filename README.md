# Unreal 触控屏工具箱操作文档



## 目录

[TOC]

## 插件编译环境

+ Windows 10

+ Unreal 4.26.2
+ Visual Studio 2019



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

  

+ 功能描述

  + 自定义视频播放组件
  + 支持读写本地及局域网文件
  + 视频控制器组件
  + 支持视频播放、暂停、进度条、跳帧
  + 支持多窗口同视频流及不同视频流
  + 解决二维鼠标相对坐标问题，转为三维空间射线碰撞运算

+ 样例



### LevelSequenceControlManager           

+ Content

  

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



### DrawBoardManager                               

+ Content

  

+ 功能描述

  + 画板模块
  + 支持在指定区域 使用画笔或箭头
  + 支持撤销及清空功能
  + 画板空间计算采用三维坐标计算

+ 样例



### ResourceManager                                   

+ Content

  

+ 功能描述

  + 本地化存储管理模块
  + 将自定义变量以SaveGame格式本地化存储， 保存后下次开启可得到最终保存数据
  + 支持文件选取及文件夹选取

+ 样例

