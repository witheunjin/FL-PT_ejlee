## HOW TO EXECUTE
updated: June, 22, 2021

### `../baseline_main.py`
```
$ python3 src/baseline_main.py
```

### EXAMPLE
```
$ python3 src/baseline_main.py --epochs=5
```
**RESULT**
```
/usr/local/lib/python3.8/dist-packages/torchvision/datasets/mnist.py:498: UserWarning: The given NumPy array is not writeable, and PyTorch does not support non-writeable tensors. This means you can write to the underlying (supposedly non-writeable) NumPy array using the tensor. You may want to copy the array to protect its data or make it writeable before converting it to a tensor. This type of warning will be suppressed for the rest of this program. (Triggered internally at  /pytorch/torch/csrc/utils/tensor_numpy.cpp:143.)
  return torch.from_numpy(parsed.astype(m[2], copy=False)).view(*s)
MLP(
  (layer_input): Linear(in_features=784, out_features=64, bias=True)
  (relu): ReLU()
  (dropout): Dropout(p=0.5, inplace=False)
  (layer_hidden): Linear(in_features=64, out_features=10, bias=True)
  (softmax): Softmax(dim=1)
)
args.epochs: 5
  0%|                                                                                            | 0/5 [00:00<?, ?it/s]

-------------------------------------------------------
Train Epoch: 1 [0/60000 (0%)]	Loss: -0.104527
Train Epoch: 1 [3200/60000 (5%)]	Loss: -0.121032
Train Epoch: 1 [6400/60000 (11%)]	Loss: -0.123924
Train Epoch: 1 [9600/60000 (16%)]	Loss: -0.243595
Train Epoch: 1 [12800/60000 (21%)]	Loss: -0.268434
Train Epoch: 1 [16000/60000 (27%)]	Loss: -0.303137
Train Epoch: 1 [19200/60000 (32%)]	Loss: -0.396029
Train Epoch: 1 [22400/60000 (37%)]	Loss: -0.404278
Train Epoch: 1 [25600/60000 (43%)]	Loss: -0.565204
Train Epoch: 1 [28800/60000 (48%)]	Loss: -0.481940
Train Epoch: 1 [32000/60000 (53%)]	Loss: -0.554722
Train Epoch: 1 [35200/60000 (59%)]	Loss: -0.518952
Train Epoch: 1 [38400/60000 (64%)]	Loss: -0.582722
Train Epoch: 1 [41600/60000 (69%)]	Loss: -0.560948
Train Epoch: 1 [44800/60000 (75%)]	Loss: -0.680610
Train Epoch: 1 [48000/60000 (80%)]	Loss: -0.701481
Train Epoch: 1 [51200/60000 (85%)]	Loss: -0.722896
Train Epoch: 1 [54400/60000 (91%)]	Loss: -0.687722
Train Epoch: 1 [57600/60000 (96%)]	Loss: -0.642859

Train loss: -0.4670003616670047
 20%|████████████████▊                                                                   | 1/5 [00:08<00:34,  8.73s/it]

-------------------------------------------------------
Train Epoch: 2 [0/60000 (0%)]	Loss: -0.596561
Train Epoch: 2 [3200/60000 (5%)]	Loss: -0.664525
Train Epoch: 2 [6400/60000 (11%)]	Loss: -0.655001
Train Epoch: 2 [9600/60000 (16%)]	Loss: -0.807380
Train Epoch: 2 [12800/60000 (21%)]	Loss: -0.711499
Train Epoch: 2 [16000/60000 (27%)]	Loss: -0.766815
Train Epoch: 2 [19200/60000 (32%)]	Loss: -0.668618
Train Epoch: 2 [22400/60000 (37%)]	Loss: -0.739188
Train Epoch: 2 [25600/60000 (43%)]	Loss: -0.697733
Train Epoch: 2 [28800/60000 (48%)]	Loss: -0.782141
Train Epoch: 2 [32000/60000 (53%)]	Loss: -0.697066
Train Epoch: 2 [35200/60000 (59%)]	Loss: -0.709502
Train Epoch: 2 [38400/60000 (64%)]	Loss: -0.778945
Train Epoch: 2 [41600/60000 (69%)]	Loss: -0.705746
Train Epoch: 2 [44800/60000 (75%)]	Loss: -0.730282
Train Epoch: 2 [48000/60000 (80%)]	Loss: -0.756045
Train Epoch: 2 [51200/60000 (85%)]	Loss: -0.756305
Train Epoch: 2 [54400/60000 (91%)]	Loss: -0.744472
Train Epoch: 2 [57600/60000 (96%)]	Loss: -0.683481

Train loss: -0.7117984894750469
 40%|█████████████████████████████████▌                                                  | 2/5 [00:17<00:26,  8.81s/it]

-------------------------------------------------------
Train Epoch: 3 [0/60000 (0%)]	Loss: -0.772406
Train Epoch: 3 [3200/60000 (5%)]	Loss: -0.758188
Train Epoch: 3 [6400/60000 (11%)]	Loss: -0.755434
Train Epoch: 3 [9600/60000 (16%)]	Loss: -0.783524
Train Epoch: 3 [12800/60000 (21%)]	Loss: -0.735500
Train Epoch: 3 [16000/60000 (27%)]	Loss: -0.752179
Train Epoch: 3 [19200/60000 (32%)]	Loss: -0.851381
Train Epoch: 3 [22400/60000 (37%)]	Loss: -0.786096
Train Epoch: 3 [25600/60000 (43%)]	Loss: -0.739383
Train Epoch: 3 [28800/60000 (48%)]	Loss: -0.837677
Train Epoch: 3 [32000/60000 (53%)]	Loss: -0.810314
Train Epoch: 3 [35200/60000 (59%)]	Loss: -0.757963
Train Epoch: 3 [38400/60000 (64%)]	Loss: -0.777881
Train Epoch: 3 [41600/60000 (69%)]	Loss: -0.765773
Train Epoch: 3 [44800/60000 (75%)]	Loss: -0.791825
Train Epoch: 3 [48000/60000 (80%)]	Loss: -0.784948
Train Epoch: 3 [51200/60000 (85%)]	Loss: -0.769742
Train Epoch: 3 [54400/60000 (91%)]	Loss: -0.758684
Train Epoch: 3 [57600/60000 (96%)]	Loss: -0.786076

Train loss: -0.7605716047256486
 60%|██████████████████████████████████████████████████▍                                 | 3/5 [00:26<00:17,  8.72s/it]

-------------------------------------------------------
Train Epoch: 4 [0/60000 (0%)]	Loss: -0.718053
Train Epoch: 4 [3200/60000 (5%)]	Loss: -0.814486
Train Epoch: 4 [6400/60000 (11%)]	Loss: -0.736566
Train Epoch: 4 [9600/60000 (16%)]	Loss: -0.837943
Train Epoch: 4 [12800/60000 (21%)]	Loss: -0.663848
Train Epoch: 4 [16000/60000 (27%)]	Loss: -0.752164
Train Epoch: 4 [19200/60000 (32%)]	Loss: -0.782960
Train Epoch: 4 [22400/60000 (37%)]	Loss: -0.782873
Train Epoch: 4 [25600/60000 (43%)]	Loss: -0.700005
Train Epoch: 4 [28800/60000 (48%)]	Loss: -0.776247
Train Epoch: 4 [32000/60000 (53%)]	Loss: -0.828096
Train Epoch: 4 [35200/60000 (59%)]	Loss: -0.815559
Train Epoch: 4 [38400/60000 (64%)]	Loss: -0.876128
Train Epoch: 4 [41600/60000 (69%)]	Loss: -0.718639
Train Epoch: 4 [44800/60000 (75%)]	Loss: -0.805586
Train Epoch: 4 [48000/60000 (80%)]	Loss: -0.760543
Train Epoch: 4 [51200/60000 (85%)]	Loss: -0.771354
Train Epoch: 4 [54400/60000 (91%)]	Loss: -0.783941
Train Epoch: 4 [57600/60000 (96%)]	Loss: -0.818001

Train loss: -0.7795656789213355
 80%|███████████████████████████████████████████████████████████████████▏                | 4/5 [00:34<00:08,  8.71s/it]

-------------------------------------------------------
Train Epoch: 5 [0/60000 (0%)]	Loss: -0.695386
Train Epoch: 5 [3200/60000 (5%)]	Loss: -0.834531
Train Epoch: 5 [6400/60000 (11%)]	Loss: -0.863213
Train Epoch: 5 [9600/60000 (16%)]	Loss: -0.767347
Train Epoch: 5 [12800/60000 (21%)]	Loss: -0.808900
Train Epoch: 5 [16000/60000 (27%)]	Loss: -0.769650
Train Epoch: 5 [19200/60000 (32%)]	Loss: -0.730258
Train Epoch: 5 [22400/60000 (37%)]	Loss: -0.852816
Train Epoch: 5 [25600/60000 (43%)]	Loss: -0.819877
Train Epoch: 5 [28800/60000 (48%)]	Loss: -0.811751
Train Epoch: 5 [32000/60000 (53%)]	Loss: -0.774198
Train Epoch: 5 [35200/60000 (59%)]	Loss: -0.852399
Train Epoch: 5 [38400/60000 (64%)]	Loss: -0.781512
Train Epoch: 5 [41600/60000 (69%)]	Loss: -0.813020
Train Epoch: 5 [44800/60000 (75%)]	Loss: -0.747112
Train Epoch: 5 [48000/60000 (80%)]	Loss: -0.743515
Train Epoch: 5 [51200/60000 (85%)]	Loss: -0.801678
Train Epoch: 5 [54400/60000 (91%)]	Loss: -0.828281
Train Epoch: 5 [57600/60000 (96%)]	Loss: -0.766557

Train loss: -0.7919832654217921
100%|████████████████████████████████████████████████████████████████████████████████████| 5/5 [00:43<00:00,  8.72s/it]
Training is ended successfully.
-------------------------------------------------------
Test on 10000 samples
Test Accuracy: 84.40%/100%
```
