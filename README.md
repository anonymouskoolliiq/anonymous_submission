## Preliminaries
This code is based on [CoinRun](https://github.com/openai/coinrun) platform. 
After installing all packages in [CoinRun](https://github.com/openai/coinrun), 
replace `coninrun.cpp`, `policies.py`, `config.py`, `train_random.py`, `random_ppo2.py` and `coinrunenv.py` with ours.

## Training PPO agents

Vanilar PPO 
```
python -m coinrun.train_agent --run-id myrun --save-interval 1
```

Vanilar PPO + CutOut
```
python -m coinrun.train_agent --run-id myrun --save-interval 1 -uda 1
```

Vanilar PPO + Dropout
```
python -m coinrun.train_agent --run-id myrun --save-interval 1 -dropout 0.1
```

Vanilar PPO + BN
```
python -m coinrun.train_agent --run-id myrun --save-interval 1 -norm 1
```

Vanilar PPO + L2
```
python -m coinrun.train_agent --run-id myrun --save-interval 1 -l2 0.0001
```

Vanilar PPO + Grayout
```
python -m coinrun.train_agent --run-id myrun --save-interval 1 -ubw 1
```


Vanilar PPO + Inversion
```
python -m coinrun.train_agent --run-id myrun --save-interval 1 -ui 1
```


Vanilar PPO + Color Jitter
```
python -m coinrun.train_agent --run-id myrun --save-interval 1 -uct 1
```

PPO + ours
```
python -m coinrun.train_random --run-id myrun --save-interval 1 -lstm 2
```

## Test on unseen environments

```
python -m coinrun.enjoy --test-eval --restore-id myrun -num-eval N -rep K -train_flag 1
```

