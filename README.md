# unix wine ver for zhanbalao/mc26-one ！（use AI）
# Minecraft 26.2 ".exe"（原版） 基于zhanbalao/mc26-one的开源项目
## 法律声明
 # 这2次分发了Minecraft JAVA 
 # 重申Minecraft文件来源：https://github.com/zhanbalao/mc26-one
 # 违反mojang的用户条例
 # 可能下载到病毒软件
 # 没有xhs-256比对
 # 具有不确定性，我们无法保证不会泄露个人信息
## 使用方式
提交issue可直接在本页面提交
将 Minecraft 26.2 打包成一个 exe（Windows应用程序） 和python （.py）文件——内置 Java 25 
Minecraft资源文件位于.exe程序内部（wine只能解压）
运行.py时下载启动程序，可以扔到任何x64wine上直接运行。（或者windows 64）
## 前置条件
    一个donat10运行库（.net 10Lts）
    wine ver10.0++
    python ver 3.14++
## 成品内容

-  _data文件夹 (~765 MB) + 262.exe （～765MB） +mc_build文件夹+mc_output文件夹+logs文件夹  — Minecraft 26.2 原版 无任何外置（all～3gib）
- 玩家名 = exe 文件名（重命名即改名）
- 存档保存在 （py生成的）exe 同级 `Minecraft\vision\` 目录

## 原理

```
┌─────────────────────────────────────────────┐
│                262.exe                      │
│  ┌───────────────────────────────────────┐  │
│  |.NET 10 运行程序                        |
│  ├────────────────────────────────────── |  │
│  │  内嵌 ZIP (~695 MB)                    | |
│  │  ├─ app/      所有 .jar 库 + mc.jar    |  │
│  │  ├─ runtime/  Java 25 JRE (100 MB)    │  │
│  │  └─ assets/   游戏资源文件 (455 MB)   │    │
│  └───────────────────────────────────────┘  │
└─────────────────────────────────────────────┘
┌─────────────────────────────────────────────┐
│               py                     │
│  ┌───────────────────────────────────────┐  │
│  |.NET 10                         |
│  ├────────────────────────────────────── |  │
│  │  jar配置  ，内存配置文件，启动器生成
│  └───────────────────────────────────────┘  │
└─────────────────────────────────────────────┘
```

首次运行：262自解压到 `\_data\` → 运行py → 启动 Minecraft。


## 构建（可选）

如需自行编辑内存配置，需要：

| 工具 | 用途 |
|------|------|
| MS.NET 10 | 编译 C# 启动器 |
| Python 3.14+ | 运行构建脚本 |
编辑 `build_vanilla_262.py` 中 C# 模板的 `jvmArgs` 字符串：
```
-Xms2G -Xmx4G -XX:
```

### 修改启动参数
高级内容请专业人员修改
## 常见问题
运用AI生成和修改
## 法律声明
这2次分发了Minecraft JAVA 重申Minecraft文件来源：https://github.com/zhanbalao/mc26-one
相关文件声明https://github.com/zhanbalao/mc26-one
