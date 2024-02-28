## 欢迎来到开悟

### 赛题介绍：

**场景：** 王者荣耀1v1

**地图：** 墨家机关道

**阵容：** 中级（孙尚香）；高级（虞姬、百里守约、李元芳）

**支持框架：** PyTorch

**支持算法：** PPO

### 代码目录说明

```
/aiarena/
├── battle        # 本地对战启动脚本 (不需要打包上传平台)
├── checkpoints   # learner保存的ckpt路径 (不需要打包上传平台)
├── code          # RL 训练代码
├── logs          # 代码运行产生的日志 (不需要打包上传平台, 反馈issue时需要提供)
├── process       # 本地测试入口 (python版) (不需要打包上传平台)
└── scripts       # 集群训练启动脚本
```

```
/rl_framework/gamecore/simulator_output # 本地对战产生的abs文件以及对局日志
```

### 代码开发说明

```
/aiarena/code/
├── actor
│   ├── __init__.py
│   ├── actor.py                # actor 流程, 一般不需要改动
│   ├── agent.py                # base agent, 一般不需要改动
│   ├── agent_demo.py           # 规则agent的示例
│   ├── config.json             # reward 配置
│   ├── custom.py               # 在agent中自定义feature示例
│   ├── entry.py                # actor 程序入口
│   ├── model.py                # model 文件, 一般不需要改动
│   ├── rl_data_info.py         # 一般不需要改动
│   ├── sample_manager.py       # 发送样本给learner, 修改feature或样本需要修改
│   └── server.py               # 对战 server 程序入口, 用于平台对战
├── common
│   ├── algorithm_tf.py         # tensorflow 网络代码
│   ├── algorithm_torch.py      # pytorch 网络代码
│   └── config.py               # 部分配置文件
└── learner
    ├── __init__.py
    ├── config
    │   └── common.conf         # learner的默认配置, 一般不需要改动
    └── train.py                # learner 程序入口
```

💡[点此查看王者荣耀1v1开发指南](https://doc.aiarena.tencent.com/kaiwu-arena/hok1v1/1.0.0/)
