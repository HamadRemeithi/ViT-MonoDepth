## Usage

1. Images should be included in [`input`](vit_for_depth_estimation/input)

2. Select one of the four models:
   - `DPT_Large`: Largest model
   - `DPT_Hybrid`
   - `MiDaS`
   - `MiDaS_small`
3. Inference:

```shell
python inference.py -i ../input -o ../output -t DPT_Large
```

```shell
python inference.py -i ../input -o ../output -t DPT_Hybrid
```

```shell
python inference.py -i ../input -o ../output -t MiDaS
```

```shell
python inference.py -i ../input -o ../output -t MiDaS_small
```

4. Depth Estimation

The models perform relative depth estimation.

To perform absolute depth estimation, use the below script.

```shell
python inference.py -i ../input -o ../output -t <model_name> -a true
```

5. Output

- Results are saved in [`output`](vit_for_depth_estimation/output) folder in png format. Output can be visualized using:

```shell
python plot.py
```

## NOTE:

Training script is not provided by the original authors, refer issue [#43](https://github.com/isl-org/MiDaS/issues/43). The authors utilize the strategies proposed in the paper ["Multi-Task Learning as Multi-Objective Optimization"](https://arxiv.org/abs/1810.04650) for training on different datasets with different objectives. The authors have shared the loss function in pytorch code [here](https://gist.github.com/ranftlr/1d6194db2e1dffa0a50c9b0a9549cbd2)
