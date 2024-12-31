## 传统方式运行

### 1.安装前端部分的依赖

```
# macOS / Linux
./gradlew pnpmInstall

# Windows
./gradlew.bat pnpmInstall
```
### 2.编译插件
```
# macOS / Linux
./gradlew build

# Windows
./gradlew.bat build
```

### 3.修改 Halo 配置文件：
```
# 进入 Halo 项目根目录后，使用 cd 命令进入配置文件目录
cd application/src/main/resources

# 创建 application-local.yaml 文件
touch application-local.yaml
```
### 4.根据你的操作系统，将以下内容添加到 application-local.yaml 文件中。
```
# macOS / Linux
halo:
plugin:
runtime-mode: development
fixed-plugin-path:
# 配置为插件项目目录绝对路径
- /path/to/halo-plugin-hello-world

# Windows
halo:
plugin:
runtime-mode: development
fixed-plugin-path:
# 配置为插件项目目录绝对路径
- C:\path\to\halo-plugin-hello-world
```
### 5.启动 Halo
```
# macOS / Linux
./gradlew bootRun --args="--spring.profiles.active=dev,local"

# Windows
gradlew.bat bootRun --args="--spring.profiles.active=dev,win,local"
```
然后访问 http://localhost:8090/console

在插件列表将能看到插件已经被正确启动，并且在左侧菜单添加了一个 示例分组，其下有一个名 示例页面 的菜单。

