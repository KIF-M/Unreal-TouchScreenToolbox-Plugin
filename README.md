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

+ FileJsonTxtManager                                JsonTxt文件管理模块

+ VideoControlManager                            视频控制管理模块

+ LevelSequenceControlManager           关卡序列动画管理模块

+ DrawBoardManager                               画板管理模块

  

+ ResourceManager                                   本地化存储管理模块

