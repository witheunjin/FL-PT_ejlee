This file is for writing down how I run & fix errors in this project step-by-step.

## INSTALLATION
Python3 is already installed.(in my case)

But installation of 'tqdm' and 'TorchVision' is required and I installed them like below. 
```
$ sudo pip install tqdm
$ sudo apt install torchvision
```
If the installation is ended successfully, you can see these messages.
* tqdm
```
Collecting tqdm
  Downloading tqdm-4.61.1-py2.py3-none-any.whl (75 kB)
     |████████████████████████████████| 75 kB 813 kB/s 
Installing collected packages: tqdm
Successfully installed tqdm-4.61.1
```
* torchvision
```
Collecting torchvision
  Downloading torchvision-0.10.0-cp38-cp38-manylinux1_x86_64.whl (22.1 MB)
     |████████████████████████████████| 22.1 MB 817 kB/s 
Collecting torch==1.9.0
  Downloading torch-1.9.0-cp38-cp38-manylinux1_x86_64.whl (831.4 MB)
     |████████████████████████████████| 831.4 MB 28 kB/s 
Requirement already satisfied: numpy in /usr/local/lib/python3.8/dist-packages (from torchvision) (1.20.3)
Requirement already satisfied: pillow>=5.3.0 in /usr/lib/python3/dist-packages (from torchvision) (7.0.0)
Requirement already satisfied: typing-extensions in /usr/lib/python3/dist-packages (from torch==1.9.0->torchvision) (3.7.4.1)
Installing collected packages: torch, torchvision
Successfully installed torch-1.9.0 torchvision-0.10.0
```
-----

## RUN
### 1st(Initial) Trial
* CODE
```
$ python3 src/baseline_main.py
```
* RESULT
```
Downloading http://yann.lecun.com/exdb/mnist/train-images-idx3-ubyte.gz
Failed to download (trying next):
HTTP Error 503: Service Unavailable

Downloading https://ossci-datasets.s3.amazonaws.com/mnist/train-images-idx3-ubyte.gz
Downloading https://ossci-datasets.s3.amazonaws.com/mnist/train-images-idx3-ubyte.gz to ../data/mnist/MNIST/raw/train-images-idx3-ubyte.gz
9913344it [00:01, 5570549.47it/s]                                               
Extracting ../data/mnist/MNIST/raw/train-images-idx3-ubyte.gz to ../data/mnist/MNIST/raw

Downloading http://yann.lecun.com/exdb/mnist/train-labels-idx1-ubyte.gz
Downloading http://yann.lecun.com/exdb/mnist/train-labels-idx1-ubyte.gz to ../data/mnist/MNIST/raw/train-labels-idx1-ubyte.gz
29696it [00:00, 179353.04it/s]                                                  
Extracting ../data/mnist/MNIST/raw/train-labels-idx1-ubyte.gz to ../data/mnist/MNIST/raw

Downloading http://yann.lecun.com/exdb/mnist/t10k-images-idx3-ubyte.gz
Downloading http://yann.lecun.com/exdb/mnist/t10k-images-idx3-ubyte.gz to ../data/mnist/MNIST/raw/t10k-images-idx3-ubyte.gz
Failed to download (trying next):
HTTP Error 503: Service Unavailable

Downloading https://ossci-datasets.s3.amazonaws.com/mnist/t10k-images-idx3-ubyte.gz
Downloading https://ossci-datasets.s3.amazonaws.com/mnist/t10k-images-idx3-ubyte.gz to ../data/mnist/MNIST/raw/t10k-images-idx3-ubyte.gz
1649664it [00:01, 1420622.64it/s]                                               
Extracting ../data/mnist/MNIST/raw/t10k-images-idx3-ubyte.gz to ../data/mnist/MNIST/raw

Downloading http://yann.lecun.com/exdb/mnist/t10k-labels-idx1-ubyte.gz
Downloading http://yann.lecun.com/exdb/mnist/t10k-labels-idx1-ubyte.gz to ../data/mnist/MNIST/raw/t10k-labels-idx1-ubyte.gz
5120it [00:00, 37609170.72it/s]                                                 
Extracting ../data/mnist/MNIST/raw/t10k-labels-idx1-ubyte.gz to ../data/mnist/MNIST/raw

/usr/local/lib/python3.8/dist-packages/torchvision/datasets/mnist.py:498: UserWarning: The given NumPy array is not writeable, and PyTorch does not support non-writeable tensors. This means you can write to the underlying (supposedly non-writeable) NumPy array using the tensor. You may want to copy the array to protect its data or make it writeable before converting it to a tensor. This type of warning will be suppressed for the rest of this program. (Triggered internally at  /pytorch/torch/csrc/utils/tensor_numpy.cpp:143.)
  return torch.from_numpy(parsed.astype(m[2], copy=False)).view(*s)
MLP(
  (layer_input): Linear(in_features=784, out_features=64, bias=True)
  (relu): ReLU()
  (dropout): Dropout(p=0.5, inplace=False)
  (layer_hidden): Linear(in_features=64, out_features=10, bias=True)
  (softmax): Softmax(dim=1)
)
  0%|                                                    | 0/10 [00:00<?, ?it/s]Train Epoch: 1 [0/60000 (0%)]	Loss: -0.101403
Train Epoch: 1 [3200/60000 (5%)]	Loss: -0.108775
Train Epoch: 1 [6400/60000 (11%)]	Loss: -0.143798
Train Epoch: 1 [9600/60000 (16%)]	Loss: -0.234992
Train Epoch: 1 [12800/60000 (21%)]	Loss: -0.288048
Train Epoch: 1 [16000/60000 (27%)]	Loss: -0.307187
Train Epoch: 1 [19200/60000 (32%)]	Loss: -0.376749
Train Epoch: 1 [22400/60000 (37%)]	Loss: -0.529415
Train Epoch: 1 [25600/60000 (43%)]	Loss: -0.460616
Train Epoch: 1 [28800/60000 (48%)]	Loss: -0.527029
Train Epoch: 1 [32000/60000 (53%)]	Loss: -0.471818
Train Epoch: 1 [35200/60000 (59%)]	Loss: -0.558514
Train Epoch: 1 [38400/60000 (64%)]	Loss: -0.529963
Train Epoch: 1 [41600/60000 (69%)]	Loss: -0.571892
Train Epoch: 1 [44800/60000 (75%)]	Loss: -0.536378
Train Epoch: 1 [48000/60000 (80%)]	Loss: -0.589250
Train Epoch: 1 [51200/60000 (85%)]	Loss: -0.649947
Train Epoch: 1 [54400/60000 (91%)]	Loss: -0.746225
Train Epoch: 1 [57600/60000 (96%)]	Loss: -0.668191

Train loss: -0.4555298010073999
 10%|████▍                                       | 1/10 [00:08<01:18,  8.77s/it]Train Epoch: 2 [0/60000 (0%)]	Loss: -0.611295
Train Epoch: 2 [3200/60000 (5%)]	Loss: -0.617507
Train Epoch: 2 [6400/60000 (11%)]	Loss: -0.658346
Train Epoch: 2 [9600/60000 (16%)]	Loss: -0.693962
Train Epoch: 2 [12800/60000 (21%)]	Loss: -0.730293
Train Epoch: 2 [16000/60000 (27%)]	Loss: -0.599848
Train Epoch: 2 [19200/60000 (32%)]	Loss: -0.661033
Train Epoch: 2 [22400/60000 (37%)]	Loss: -0.674989
Train Epoch: 2 [25600/60000 (43%)]	Loss: -0.732002
Train Epoch: 2 [28800/60000 (48%)]	Loss: -0.661982
Train Epoch: 2 [32000/60000 (53%)]	Loss: -0.664866
Train Epoch: 2 [35200/60000 (59%)]	Loss: -0.685800
Train Epoch: 2 [38400/60000 (64%)]	Loss: -0.588811
Train Epoch: 2 [41600/60000 (69%)]	Loss: -0.575999
Train Epoch: 2 [44800/60000 (75%)]	Loss: -0.634176
Train Epoch: 2 [48000/60000 (80%)]	Loss: -0.634332
Train Epoch: 2 [51200/60000 (85%)]	Loss: -0.681542
Train Epoch: 2 [54400/60000 (91%)]	Loss: -0.697976
Train Epoch: 2 [57600/60000 (96%)]	Loss: -0.672057

Train loss: -0.6676162542310605
 20%|████████▊                                   | 2/10 [00:17<01:09,  8.71s/it]Train Epoch: 3 [0/60000 (0%)]	Loss: -0.673187
Train Epoch: 3 [3200/60000 (5%)]	Loss: -0.652892
Train Epoch: 3 [6400/60000 (11%)]	Loss: -0.612361
Train Epoch: 3 [9600/60000 (16%)]	Loss: -0.670274
Train Epoch: 3 [12800/60000 (21%)]	Loss: -0.680529
Train Epoch: 3 [16000/60000 (27%)]	Loss: -0.675451
Train Epoch: 3 [19200/60000 (32%)]	Loss: -0.647789
Train Epoch: 3 [22400/60000 (37%)]	Loss: -0.721068
Train Epoch: 3 [25600/60000 (43%)]	Loss: -0.638325
Train Epoch: 3 [28800/60000 (48%)]	Loss: -0.774649
Train Epoch: 3 [32000/60000 (53%)]	Loss: -0.802747
Train Epoch: 3 [35200/60000 (59%)]	Loss: -0.796060
Train Epoch: 3 [38400/60000 (64%)]	Loss: -0.746180
Train Epoch: 3 [41600/60000 (69%)]	Loss: -0.813405
Train Epoch: 3 [44800/60000 (75%)]	Loss: -0.756924
Train Epoch: 3 [48000/60000 (80%)]	Loss: -0.837190
Train Epoch: 3 [51200/60000 (85%)]	Loss: -0.816512
Train Epoch: 3 [54400/60000 (91%)]	Loss: -0.740029
Train Epoch: 3 [57600/60000 (96%)]	Loss: -0.784165

Train loss: -0.7390864455242401
 30%|█████████████▏                              | 3/10 [00:26<01:00,  8.68s/it]Train Epoch: 4 [0/60000 (0%)]	Loss: -0.758908
Train Epoch: 4 [3200/60000 (5%)]	Loss: -0.864475
Train Epoch: 4 [6400/60000 (11%)]	Loss: -0.792138
Train Epoch: 4 [9600/60000 (16%)]	Loss: -0.870229
Train Epoch: 4 [12800/60000 (21%)]	Loss: -0.834472
Train Epoch: 4 [16000/60000 (27%)]	Loss: -0.889956
Train Epoch: 4 [19200/60000 (32%)]	Loss: -0.793251
Train Epoch: 4 [22400/60000 (37%)]	Loss: -0.809137
Train Epoch: 4 [25600/60000 (43%)]	Loss: -0.775830
Train Epoch: 4 [28800/60000 (48%)]	Loss: -0.817803
Train Epoch: 4 [32000/60000 (53%)]	Loss: -0.727198
Train Epoch: 4 [35200/60000 (59%)]	Loss: -0.845079
Train Epoch: 4 [38400/60000 (64%)]	Loss: -0.811183
Train Epoch: 4 [41600/60000 (69%)]	Loss: -0.801487
Train Epoch: 4 [44800/60000 (75%)]	Loss: -0.788587
Train Epoch: 4 [48000/60000 (80%)]	Loss: -0.839409
Train Epoch: 4 [51200/60000 (85%)]	Loss: -0.847852
Train Epoch: 4 [54400/60000 (91%)]	Loss: -0.828244
Train Epoch: 4 [57600/60000 (96%)]	Loss: -0.860871

Train loss: -0.8112410944916292
 40%|█████████████████▌                          | 4/10 [00:34<00:51,  8.65s/it]Train Epoch: 5 [0/60000 (0%)]	Loss: -0.833005
Train Epoch: 5 [3200/60000 (5%)]	Loss: -0.833228
Train Epoch: 5 [6400/60000 (11%)]	Loss: -0.761769
Train Epoch: 5 [9600/60000 (16%)]	Loss: -0.860622
Train Epoch: 5 [12800/60000 (21%)]	Loss: -0.847116
Train Epoch: 5 [16000/60000 (27%)]	Loss: -0.766509
Train Epoch: 5 [19200/60000 (32%)]	Loss: -0.793008
Train Epoch: 5 [22400/60000 (37%)]	Loss: -0.835082
Train Epoch: 5 [25600/60000 (43%)]	Loss: -0.854617
Train Epoch: 5 [28800/60000 (48%)]	Loss: -0.879882
Train Epoch: 5 [32000/60000 (53%)]	Loss: -0.857699
Train Epoch: 5 [35200/60000 (59%)]	Loss: -0.879613
Train Epoch: 5 [38400/60000 (64%)]	Loss: -0.901500
Train Epoch: 5 [41600/60000 (69%)]	Loss: -0.838912
Train Epoch: 5 [44800/60000 (75%)]	Loss: -0.830216
Train Epoch: 5 [48000/60000 (80%)]	Loss: -0.832539
Train Epoch: 5 [51200/60000 (85%)]	Loss: -0.683447
Train Epoch: 5 [54400/60000 (91%)]	Loss: -0.832039
Train Epoch: 5 [57600/60000 (96%)]	Loss: -0.850938

Train loss: -0.8331982508651229
 50%|██████████████████████                      | 5/10 [00:43<00:43,  8.64s/it]Train Epoch: 6 [0/60000 (0%)]	Loss: -0.754384
Train Epoch: 6 [3200/60000 (5%)]	Loss: -0.876145
Train Epoch: 6 [6400/60000 (11%)]	Loss: -0.843713
Train Epoch: 6 [9600/60000 (16%)]	Loss: -0.777072
Train Epoch: 6 [12800/60000 (21%)]	Loss: -0.804585
Train Epoch: 6 [16000/60000 (27%)]	Loss: -0.842582
Train Epoch: 6 [19200/60000 (32%)]	Loss: -0.885205
Train Epoch: 6 [22400/60000 (37%)]	Loss: -0.858614
Train Epoch: 6 [25600/60000 (43%)]	Loss: -0.718186
Train Epoch: 6 [28800/60000 (48%)]	Loss: -0.779529
Train Epoch: 6 [32000/60000 (53%)]	Loss: -0.801682
Train Epoch: 6 [35200/60000 (59%)]	Loss: -0.842020
Train Epoch: 6 [38400/60000 (64%)]	Loss: -0.816091
Train Epoch: 6 [41600/60000 (69%)]	Loss: -0.861517
Train Epoch: 6 [44800/60000 (75%)]	Loss: -0.866623
Train Epoch: 6 [48000/60000 (80%)]	Loss: -0.843085
Train Epoch: 6 [51200/60000 (85%)]	Loss: -0.901580
Train Epoch: 6 [54400/60000 (91%)]	Loss: -0.894627
Train Epoch: 6 [57600/60000 (96%)]	Loss: -0.881063

Train loss: -0.8467343968114873
 60%|██████████████████████████▍                 | 6/10 [00:51<00:34,  8.63s/it]Train Epoch: 7 [0/60000 (0%)]	Loss: -0.796179
Train Epoch: 7 [3200/60000 (5%)]	Loss: -0.875651
Train Epoch: 7 [6400/60000 (11%)]	Loss: -0.818231
Train Epoch: 7 [9600/60000 (16%)]	Loss: -0.874749
Train Epoch: 7 [12800/60000 (21%)]	Loss: -0.893777
Train Epoch: 7 [16000/60000 (27%)]	Loss: -0.881145
Train Epoch: 7 [19200/60000 (32%)]	Loss: -0.871987
Train Epoch: 7 [22400/60000 (37%)]	Loss: -0.834033
Train Epoch: 7 [25600/60000 (43%)]	Loss: -0.778695
Train Epoch: 7 [28800/60000 (48%)]	Loss: -0.894952
Train Epoch: 7 [32000/60000 (53%)]	Loss: -0.898515
Train Epoch: 7 [35200/60000 (59%)]	Loss: -0.867421
Train Epoch: 7 [38400/60000 (64%)]	Loss: -0.807424
Train Epoch: 7 [41600/60000 (69%)]	Loss: -0.818592
Train Epoch: 7 [44800/60000 (75%)]	Loss: -0.866539
Train Epoch: 7 [48000/60000 (80%)]	Loss: -0.839396
Train Epoch: 7 [51200/60000 (85%)]	Loss: -0.889946
Train Epoch: 7 [54400/60000 (91%)]	Loss: -0.821186
Train Epoch: 7 [57600/60000 (96%)]	Loss: -0.880956

Train loss: -0.8577337202741139
 70%|██████████████████████████████▊             | 7/10 [01:00<00:25,  8.61s/it]Train Epoch: 8 [0/60000 (0%)]	Loss: -0.884772
Train Epoch: 8 [3200/60000 (5%)]	Loss: -0.852941
Train Epoch: 8 [6400/60000 (11%)]	Loss: -0.885748
Train Epoch: 8 [9600/60000 (16%)]	Loss: -0.854279
Train Epoch: 8 [12800/60000 (21%)]	Loss: -0.847527
Train Epoch: 8 [16000/60000 (27%)]	Loss: -0.807422
Train Epoch: 8 [19200/60000 (32%)]	Loss: -0.865049
Train Epoch: 8 [22400/60000 (37%)]	Loss: -0.789615
Train Epoch: 8 [25600/60000 (43%)]	Loss: -0.878137
Train Epoch: 8 [28800/60000 (48%)]	Loss: -0.897998
Train Epoch: 8 [32000/60000 (53%)]	Loss: -0.837652
Train Epoch: 8 [35200/60000 (59%)]	Loss: -0.821732
Train Epoch: 8 [38400/60000 (64%)]	Loss: -0.868017
Train Epoch: 8 [41600/60000 (69%)]	Loss: -0.919548
Train Epoch: 8 [44800/60000 (75%)]	Loss: -0.842817
Train Epoch: 8 [48000/60000 (80%)]	Loss: -0.868649
Train Epoch: 8 [51200/60000 (85%)]	Loss: -0.844962
Train Epoch: 8 [54400/60000 (91%)]	Loss: -0.860602
Train Epoch: 8 [57600/60000 (96%)]	Loss: -0.902238

Train loss: -0.864074145807132
 80%|███████████████████████████████████▏        | 8/10 [01:09<00:17,  8.59s/it]Train Epoch: 9 [0/60000 (0%)]	Loss: -0.872655
Train Epoch: 9 [3200/60000 (5%)]	Loss: -0.890222
Train Epoch: 9 [6400/60000 (11%)]	Loss: -0.860521
Train Epoch: 9 [9600/60000 (16%)]	Loss: -0.871071
Train Epoch: 9 [12800/60000 (21%)]	Loss: -0.858384
Train Epoch: 9 [16000/60000 (27%)]	Loss: -0.894942
Train Epoch: 9 [19200/60000 (32%)]	Loss: -0.850989
Train Epoch: 9 [22400/60000 (37%)]	Loss: -0.877637
Train Epoch: 9 [25600/60000 (43%)]	Loss: -0.875301
Train Epoch: 9 [28800/60000 (48%)]	Loss: -0.835257
Train Epoch: 9 [32000/60000 (53%)]	Loss: -0.865294
Train Epoch: 9 [35200/60000 (59%)]	Loss: -0.826656
Train Epoch: 9 [38400/60000 (64%)]	Loss: -0.868875
Train Epoch: 9 [41600/60000 (69%)]	Loss: -0.860282
Train Epoch: 9 [44800/60000 (75%)]	Loss: -0.903524
Train Epoch: 9 [48000/60000 (80%)]	Loss: -0.852831
Train Epoch: 9 [51200/60000 (85%)]	Loss: -0.893546
Train Epoch: 9 [54400/60000 (91%)]	Loss: -0.886277
Train Epoch: 9 [57600/60000 (96%)]	Loss: -0.892831

Train loss: -0.8693592824153046
 90%|███████████████████████████████████████▌    | 9/10 [01:17<00:08,  8.58s/it]Train Epoch: 10 [0/60000 (0%)]	Loss: -0.794492
Train Epoch: 10 [3200/60000 (5%)]	Loss: -0.881286
Train Epoch: 10 [6400/60000 (11%)]	Loss: -0.838339
Train Epoch: 10 [9600/60000 (16%)]	Loss: -0.908109
Train Epoch: 10 [12800/60000 (21%)]	Loss: -0.847726
Train Epoch: 10 [16000/60000 (27%)]	Loss: -0.895676
Train Epoch: 10 [19200/60000 (32%)]	Loss: -0.881535
Train Epoch: 10 [22400/60000 (37%)]	Loss: -0.867876
Train Epoch: 10 [25600/60000 (43%)]	Loss: -0.871884
Train Epoch: 10 [28800/60000 (48%)]	Loss: -0.917817
Train Epoch: 10 [32000/60000 (53%)]	Loss: -0.847639
Train Epoch: 10 [35200/60000 (59%)]	Loss: -0.887379
Train Epoch: 10 [38400/60000 (64%)]	Loss: -0.865489
Train Epoch: 10 [41600/60000 (69%)]	Loss: -0.860351
Train Epoch: 10 [44800/60000 (75%)]	Loss: -0.876092
Train Epoch: 10 [48000/60000 (80%)]	Loss: -0.858252
Train Epoch: 10 [51200/60000 (85%)]	Loss: -0.880075
Train Epoch: 10 [54400/60000 (91%)]	Loss: -0.901297
Train Epoch: 10 [57600/60000 (96%)]	Loss: -0.843125

Train loss: -0.8738294276855648
100%|███████████████████████████████████████████| 10/10 [01:26<00:00,  8.61s/it]
Traceback (most recent call last):
  ### SECRET ###
FileNotFoundError: [Errno 2] No such file or directory: '../save/nn_mnist_mlp_10.png'
```
OOPS! There is an error... But it's okay I can fix it.
As you see, an error `No such file or directory: '../save/nn_mnist_mlp_10.png'` is occurred.
So the 2nd trial is about 'how I fix this error'.

### 2nd Trial
So I looked for 'where the error is occurred' and I can see a related code in `../src/baseline_main.py` file.
```python3
92  plt.savefig('../save/nn_{}_{}_{}.png'.format(args.dataset, args.model, args.epochs))
```
