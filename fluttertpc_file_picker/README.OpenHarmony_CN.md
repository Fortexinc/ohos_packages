<p align="center">
  <h1 align="center"> <code>file_picker</code> </h1>
</p>

本项目基于 [file_picker](https://pub.dev/packages/file_picker) 开发。

## 1. 安装与使用

### 1.1 安装方式

进入到工程目录并在 pubspec.yaml 中添加以下依赖：

<!-- tabs:start -->

#### pubspec.yaml

```yaml
...

dependencies:
  file_picker:
    git:
      url: https://gitcode.com/openharmony-sig/fluttertpc_file_picker.git
      ref: br_v8.0.7_ohos

...
```

执行命令

```bash
flutter pub get
```

<!-- tabs:end -->

### 1.2 使用案例

使用案例详见 [example](example/lib/main.dart)

## 2. 约束与限制

### 2.1 兼容性

在以下版本中已测试通过

1. Flutter: 3.7.12-ohos-1.0.6; SDK: 5.0.0(12); IDE: DevEco Studio: 5.0.13.200; ROM: 5.1.0.120 SP3;
2. Flutter: 3.22.1-ohos-1.0.1; SDK: 5.0.0(12); IDE: DevEco Studio: 5.0.13.200; ROM: 5.1.0.120 SP3;

## 3. API

> [!TIP] "ohos Support"列为 yes 表示 ohos 平台支持该属性；no 则表示不支持；partially 表示部分支持。使用方法跨平台一致，效果对标 iOS 或 Android 的效果。

| Name                | Description                         | Type     | Input                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           | Output                    | ohos Support |
|---------------------|-------------------------------------|----------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|--------------|
| pickFiles           | 这是选择文件的主要方法，并提供之前提到的所有属性            | function | String ?   dialogTitle , String ?   initialDirectory ,      FileType   type   =   FileType . any ,      List < String > ?   allowedExtensions ,      Function ( FilePickerStatus ) ?   onFileLoading ,      bool   allowCompression   =   true ,      int   compressionQuality   =   30 ,      bool   allowMultiple   =   false ,      bool   withData   =   false ,      bool   withReadStream   =   false ,      bool   lockParentWindow   =   false ,      bool   readSequential   =   false | Future<FilePickerResult?> | yes          |
| getDirectoryPath    | 打开文件夹选择器对话框，让用户选择目录路径。返回所选目录路径      | function | String ?   dialogTitle ,      bool   lockParentWindow   =   false ,      String ?   initialDirectory                                                                                                                                                                                                                                                                                                                                                                                            | Future<String?>           | yes          |
| clearTemporaryFiles | 一个实用方法，用于从选择器中显式删除缓存文件              | function | /                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               | Future<bool?>             | yes          |
| saveFile            | 打开“保存文件/另存为”对话框，允许用户选择文件路径和文件名以保存文件 | function | String ?   dialogTitle ,      String ?   fileName ,      String ?   initialDirectory ,      FileType   type   =   FileType . any ,      List < String > ?   allowedExtensions ,      Uint8List ?   bytes ,      bool   lockParentWindow   =   false                                                                                                                                                                                                                                             | Future<String?>           | yes          |

## 4. 属性

> [!TIP] "ohos Support"列为 yes 表示 ohos 平台支持该属性；no 则表示不支持；partially 表示部分支持。使用方法跨平台一致，效果对标 iOS 或 Android 的效果。

### Filters

| Name            | Description        | Type | Input | Output | ohos Support |
|-----------------|--------------------|------|-------|--------|--------------|
| FileType.any    | 选择所有可用的文件          | enum | /     | /      | yes          |
| FileType.custom | 选择与提供的允许扩展相匹配的扩展路径 | enum | /     | /      | yes          |
| FileType.image  | 选择图像文件             | enum | /     | /      | yes          |
| FileType.video  | 选择视频文件             | enum | /     | /      | yes          |
| FileType.media  | 选择视频或图像文件          | enum | /     | /      | yes          |
| FileType.audio  | 选择音频文件             | enum | /     | /      | yes          |

### Parameters

| Name               | Description                                              | Type                        | Input            | Ouput | ohos Support |
|--------------------|----------------------------------------------------------|-----------------------------|------------------|-------|--------------|
| allowedExtensions  | 接受允许过滤的扩展列表                                              | List?                       | /                | /     | yes          |
| dialogTitle        | 桌面平台模态对话框的标题设置                                           | String?                     | /                | /     | no           |
| initialDirectory   | 可以设置路径来指定对话框应该打开的位置                                      | String?                     | /                | /     | no           |
| withData           | 设置文件是否应立即加载到内存中并在其 PlatformFile 实例上作为 Uint8List 提供       | bool?                       | /                | /     | yes          |
| compressionQuality | 定义压缩图像时使用的压缩质量百分比。此值的范围是 0（无压缩）到 100                     | int?                        | /                | /     | no           |
| withReadStream     | 允许将文件读入 Stream 而不是立即将其加载到内存中，以防止高使用率，特别是对于较大的文件          | bool?                       | /                | /     | no           |
| lockParentWindow   | 如果为 true，则子窗口（文件选择器窗口）将停留在 Flutter 窗口前面，直到它被关闭（就像模态窗口一样） | bool?                       | /                | /     | no           |
| type               | 定义过滤文件的类型                                                | FileType                    | /                | /     | yes          |
| onFileLoading      | 提供后，将接收所选文件的处理状态                                         | Function(FilePickerStatus)? | FilePickerStatus | void  | no           |

## 5. 遗留问题

- [ ]  ohos 端 file picker selectMode
  设置选文件夹无效: [issue#14](https://gitcode.com/openharmony-sig/fluttertpc_file_picker/issues/14)

## 6. 其他

## 7. 开源协议

本项目基于 [The MIT License (MIT)](/LICENSE)
，请自由地享受和参与开源。
