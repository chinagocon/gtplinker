## Competition Notes for 2019 “CHINA SECURITIES Cup” World AI Go Test Provisions

#### 1. GTP connector download and instructions for use
> Please click the link to download the connector [here](https://github.com/chinagocon/gtplinker)

---

> 4 files included in the resource:

```
config.yaml //config file
gtp-linker_linux // linux client
gtp-linker_mac // osx client
gtp-linker_windows.exe //windows client
```

#### 2. Explanation for the config file


```
user:
  user: ""  # login account
  password: "" #login password
game:
  safe_time: 0 #safe time(sec)，will be reduced in time_left
  min_time: 0 # when time_left < safe_time, it will be used as your ai engine thinking
time
  shell: "" # AI GTP Engine
```
> How to config safe_time and min_time

|Basic time(sec) | Overtime periods | Safte Time |  Min Time | GTP |
|---|---|---|---|---|
|300 | 30sec/3times | 5 | 1 | time_left b 295 0|
|0 | 30sec/3times | 5 | 1 | time_left b 25 1|
|0 | 30sec/3times | 5 | 1 | time_left b 1 1|

#### 3. Commands will be used

```
clear_board
boardsize
time_settings
play
genmove
undo
time_left
komi
```


#### 4. Test flow

> We provided two accounts, one for the regulation game, one for the test, you can use one inviting another to test.


```
config.yaml
config1.yaml
gtp-linker_linux // linux client
gtp-linker_mac // osx client
gtp-linker_windows.exe //windows client
```


```
 // client 1
 > cd  "linker dir"
 > ./gtp-linker_[os] --config config.yaml test
 // according to the prompt, press enter to waiting
```


```
 //client 2 
 > cd  "linker dir"
 > ./gtp-linker_[os] --config config1.yaml test
 // according to the prompt, press the test account to start test game
```


#### 5. Flow for regulation game

```
> cd  "linker dir"
> ./gtp-linker_[os] run
```
