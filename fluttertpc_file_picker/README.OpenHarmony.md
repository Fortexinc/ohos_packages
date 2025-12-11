<p align="center">
  <h1 align="center"> <code>file_picker</code> </h1>
</p>

This project is based on [file_picker](https://pub.dev/packages/file_picker).

## 1. Installation and Usage

### 1.1 Installation

Go to the project directory and add the following dependencies in pubspec.yaml

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

Execute Command

```bash
flutter pub get
```

<!-- tabs:end -->

### 1.2 Usage

For use
cases [example](example/lib/main.dart)

## 2. Constraints

### 2.1 Compatibility

This document is verified based on the following versions:

1. Flutter: 3.7.12-ohos-1.0.6; SDK: 5.0.0(12); IDE: DevEco Studio: 5.0.13.200; ROM: 5.1.0.120 SP3;
2. Flutter: 3.22.1-ohos-1.0.1; SDK: 5.0.0(12); IDE: DevEco Studio: 5.0.13.200; ROM: 5.1.0.120 SP3;

## 3. API

> [!TIP] If the value of **ohos Support** is **yes**, it means that the ohos platform supports this property; **no** means the opposite; **partially** means some capabilities of this property are supported. The usage method is the same on different platforms and the effect is the same as that of iOS or Android.

| Name                | Description                                                                                                                                                                                                                           | Type     | Input                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           | Output                    | ohos Support |
|---------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|--------------|
| pickFiles           | This is the main method to pick files and provides all the properties mentioned before                                                                                                                                                | function | String ?   dialogTitle , String ?   initialDirectory ,      FileType   type   =   FileType . any ,      List < String > ?   allowedExtensions ,      Function ( FilePickerStatus ) ?   onFileLoading ,      bool   allowCompression   =   true ,      int   compressionQuality   =   30 ,      bool   allowMultiple   =   false ,      bool   withData   =   false ,      bool   withReadStream   =   false ,      bool   lockParentWindow   =   false ,      bool   readSequential   =   false | Future<FilePickerResult?> | yes          |
| getDirectoryPath    | Opens a folder picker dialog which lets the user select a directory path. Returns the absolute path to the selected directory. Returns null, if the user canceled the dialog or if the folder path couldn't be resolved               | function | String ?   dialogTitle ,      bool   lockParentWindow   =   false ,      String ?   initialDirectory                                                                                                                                                                                                                                                                                                                                                                                            | Future<String?>           | yes          |
| clearTemporaryFiles | An utility method that will explicitly prune cached files from the picker. This is not required as the system will take care on its own, however, sometimes you may want to remove them, specially if your app handles a lot of files | function | /                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               | Future<bool?>             | yes          |
| saveFile            | Opens a save-file / save-as dialog which lets the user select a file path and a file name to save a file                                                                                                                              | function | String ?   dialogTitle ,      String ?   fileName ,      String ?   initialDirectory ,      FileType   type   =   FileType . any ,      List < String > ?   allowedExtensions ,      Uint8List ?   bytes ,      bool   lockParentWindow   =   false                                                                                                                                                                                                                                             | Future<String?>           | yes          |

## 4. Properties

> [!TIP] If the value of **ohos Support** is **yes**, it means that the ohos platform supports this property; **no** means the opposite; **partially** means some capabilities of this property are supported. The usage method is the same on different platforms and the effect is the same as that of iOS or Android.

### Filters

| Name            | Description                                                                        | Type | Input | Output | ohos Support |
|-----------------|------------------------------------------------------------------------------------|------|-------|--------|--------------|
| FileType.any    | Will let you pick all available files                                              | enum | /     | /      | yes          |
| FileType.custom | Will let you pick a path for the extension matching the allowedExtensions provided | enum | /     | /      | yes          |
| FileType.image  | Will let you pick an image file                                                    | enum | /     | /      | yes          |
| FileType.video  | Will let you pick a video file                                                     | enum | /     | /      | yes          |
| FileType.media  | Will let you pick either video or images                                           | enum | /     | /      | yes          |
| FileType.audio  | Will let you pick an audio file                                                    | enum | /     | /      | yes          |

### Parameters

| Name               | Description                                                                                                                                                                         | Type                        | Input            | Output | ohos Support |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------|------------------|--------|--------------|
| allowedExtensions  | Accepts a list of allowed extensions to be filtered                                                                                                                                 | List?                       | /                | /      | yes          |
| dialogTitle        | The title to be set on desktop platforms modal dialog. Hasn't any effect on Web or Mobile                                                                                           | String?                     | /                | /      | no           |
| initialDirectory   | Can be optionally set to an absolute path to specify where the dialog should open                                                                                                   | String?                     | /                | /      | no           |
| withData           | Sets if the file should be immediately loaded into memory and available as Uint8List on its PlatformFile instance                                                                   | bool?                       | /                | /      | yes          |
| compressionQuality | Defines the compression quality percentage to use when compressing images. This value ranges from 0 (no compression) to 100                                                         | int?                        | /                | /      | no           |
| withReadStream     | Allows the file to be read into a Stream> instead of immediately loading it into memory, to prevent high usage, specially with bigger files                                         | bool?                       | /                | /      | no           |
| lockParentWindow   | If true, then the child window (file picker window) will stay in front of the Flutter window until it is closed (like a modal window)                                               | bool?                       | /                | /      | no           |
| type               | Defines the type of the filtered files                                                                                                                                              | FileType                    | /                | /      | yes          |
| onFileLoading      | When provided, will receive the processing status of picked files. This is particularly useful if you want to display a loading dialog or so when files are being downloaded/cached | Function(FilePickerStatus)? | FilePickerStatus | void   | no           |

## 5. Known Issues

- [ ] ohos file picker selectMode setting does not work for folder
  selection: [issue#14](https://gitcode.com/openharmony-sig/fluttertpc_file_picker/issues/14).

## 6. Others

## 7. License

This project is licensed
under [The MIT License (MIT)](/LICENSE).
