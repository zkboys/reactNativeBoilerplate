# React Native Boilerplate
> React Native 项目模板， [React Native中文官网](https://reactnative.cn/)

注：本文档中的所有命令都为ios环境。

## 项目环境搭建
> 基于[官网](https://reactnative.cn/docs/0.48/getting-started.html)进行环境搭建

## 开发运行
> 推荐使用真机进行调试，使用真机可以节省电脑资源，调试速速比较快；

### android
> 运行android之前，确保电脑上已经开启虚拟机；如果使用真机，请确保真机开启了usb调试；
````
react-native run-android
或
yarn android
````

### iso
```
react-native run-ios
或
yarn ios
```

## 运行 `react-native run-android`报错：
1. 未指定sdk
    ```
    * What went wrong:
    A problem occurred configuring project ':app'.
    > SDK location not found. Define location with sdk.dir in the local.properties file or with an ANDROID_HOME environment variable.
    ```
    在项目的android根目录下创建`local.properties`文件，加入`sdk.dir=/Users/yourUser/Library/Android/sdk`，来指定你自己本机的android sdk

1. 未安装adb，或者adb环境变量有问题
    ```
    /bin/sh: adb: command not found
    ```

    adb环境变量没有设置好

    ```
    # 进入用户HOME目录
    $ cd $HOME

    # 编辑.bash_profile文件，如果没有新建一个
    $ vi .bash_profile

    输入如下内容：
    export PATH=${PATH}:/Users/yourUser/Library/Android/sdk/platform-tools
    export PATH=${PATH}:/Users/yourUser/Library/Android/sdk/tools

    # 保存后 更新配置
    $ source .bash_profile

    # 验证是否成功
    $ adb devices
    ```

1. 未连接设备
    ```
    * What went wrong:
    Execution failed for task ':app:installDebug'.
    > com.android.builder.testing.api.DeviceException: No connected devices!

    ```

    没有设备，电脑上需要开启一个android虚拟机，或者使用usb与真机连接，真机需要开启usb调试

## 开发过程中的问题

### 引入图片
引入图片，会报错，重启新启动 packager 可以解决，即重新运行`yarn android` 或 `yarn ios`;


## 调试
> 更多请参考[官方文档-调试](https://reactnative.cn/docs/0.48/debugging.html#content)

### 手动刷新
1. android虚拟机： 双击键盘R键；
1. android真机：摇一摇打开开发菜单，点击reload；
1. ios虚拟机：`Cmd + R`；
1. iOS真机：摇一摇打开开发菜单，点击reload；

### 查看开发菜单
1. android虚拟机：`Cmd + M`；
1. android真机：摇一摇；
1. ios虚拟机：`Cmd + D`；
1. ios真机：摇一摇；

### 热刷新 & 热重载
> 开启热刷新、热重载，可以有效的节省开发时间，提高开发体验；

1. 开发菜单中开启 `Enable Live Reload`，可以开启热刷新；
1. 开发菜单中开启 `Enable Hot Reloading`，可以开启热重载；

### 使用Chrome开发者工具调试

开发菜单中点击`Debug JS Remotely`，打开浏览器，并打开开发者工具，可以用开发者工具进行调试；

## TODO
- [ ] 项目环境搭建
- [ ] android 开发调试
- [ ] ios 开发调试
- [ ] 打包发布
- [ ] 设置应用图标
- [ ] 设置应用权限
- [ ] 路由（导航？）
- [ ] redux?
- [ ] android ios 各版本兼容性

