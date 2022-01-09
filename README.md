# Unreal 触控屏工具箱操作文档



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

### GlobalChangeText3D



#### haha



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
  + 



+ GlobalChangeImage                               全局更改图像模块
+ FileJsonTxtManager                                JsonTxt文件管理模块
+ VideoControlManager                            视频控制管理模块
+ LevelSequenceControlManager           关卡序列动画管理模块
+ DrawBoardManager                               画板管理模块
+ TouchScreenGameMode                       触控屏游戏模式模块
+ ResourceManager                                   本地化存储管理模块

