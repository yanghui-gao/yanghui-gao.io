# flutter混编

### 环境要求:

- 符合flutter运行的基本环境要求
- iOS 8.0以上
- CocoaPods版本在1.10 以上

### 混编方式

- 使用CocoaPods管理
- 编译为 .framework 手动集成

### 使用CocoaPods管理

使用此方法需要所有小伙伴本地本地安装 Flutter SDK, 只需要在 Xcode 中编译应用，就可以自动运行脚本来集成 dart 代码和 plugin。这个方法允许你使用 Flutter module 中的最新代码快速迭代开发，而无需在 Xcode 以外执行额外的命令。

- 好处 
  - 配置简单 不需要额外配置专注业务开发
  - 不需要单独拆分组件，免去管理组件的版本及发布成本
- 弊端:
  - 所有团队开发成员都需要安装flutterSDK
  - 非常耦合，需要修改原有 native 工程配置

### 生成编译后的产物

