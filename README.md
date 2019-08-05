#### 一.下载连接器和文件解释

> 请点击此链接下载连接器

---

> 在资源包中有 4 个文件分别为：

```
config.yaml //连接器的配置文件
gtp-linker_linux // linux client
gtp-linker_mac // osx client
gtp-linker_windows.exe //windows client
```

#### 二.配置文件详解

```
user:
  user: ""  # 登录名，由主办方提供
  password: ""  #登录密码,由主办方提供
game:
  safe_time: 0  #安全时间（秒），会在time_left中自动扣减
  min_time: 0 #当剩余时间< 安全时间时,使用此值作为引擎思考时间
  shell: "" # AI GTP Engine
```

> safe_time 和 min_time 使用

| 常规时间(s) | 读秒时间(s) | 读秒次数 | safe time | min time | gtp               |
| ----------- | ----------- | -------- | --------- | -------- | ----------------- |
| 300         | 30          | 3        | 5         | 1        | time_left b 295 0 |
| 0           | 30          | 3        | 5         | 1        | time_left b 25 1  |
| 0           | 3           | 3        | 5         | 1        | time_left b 1 1   |

#### 三.关于连接器使用到的命令有

```
clear_board
boardsize
time_settings
play
gen_move
undo
time_left
komi
```

#### 四.测试赛流程

> 主办方会提供每位参赛这两个账号用于测试使用，当拿到账号时各位需要复制两个配置文件,目录结构如下

```
config.yaml //连接器的配置文件
config1.yaml
gtp-linker_linux // linux client
gtp-linker_mac // osx client
gtp-linker_windows.exe //windows client
```

```
// client 1
 > cd  "linker dir"
 > ./gtp-linker_[os] --config config.yaml test
 // 提示输入邀请人账号，直接回车进入等待邀请
```

```
//client 2
 > cd  "linker dir"
 > ./gtp-linker_[os] --config config1.yaml test
 // 提示输入邀请人账号，输入 "client 1"中的账号邀请其对弈
```

#### 五.比赛流程

```
> cd  "linker dir"
> ./gtp-linker_[os] run
```
