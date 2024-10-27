# storage
storage 的目标定位是一个开源的分布式存储引擎，包括数据持久化引擎、网络模块、各种服务、各种存储应用等。写storage的初期目的以设计、学习、实践存储作为主要的目的，本repo也主要用于记录、探讨我们对于存储的新奇想法、已经对于工程实践的验证和讨论。

### 1. 文档部分 
文档使用markdown的形式进行记录
推荐使用 [***macdown***](https://macdown.uranusjr.com/) 作为编辑器
```brew install --cask macdown ```

文档中的图片使用***drawio***进行绘制，可以在vscode中使用***vscode-drawio***插件进行编辑

图片绘制规则：

### 2. 代码部分
底层存储引擎拟用**C++**进行开发，kv、对象、table等应用拟用进行**Golang**进行开发、块、文件等应用开发拟使用**C**语言开发。管控服务等可以使用**Golang**进行开发。

* C++编译使用CMAKE
* C、Golang编译使用MAKE
* 存储引擎、各应用分开编译

### 3. 提交

建议使用以下形式进行提交 ```module: [feature] .... ```