## Project Structure

```
AquaBind/
├── AquaBind-code/
│   ├── AquaBind.py              # main model: AquaBindSegmentation
│   ├── eval.py                  # evaluation entry point
│   ├── get_flops.py             # compute FLOPs
│   ├── build_bank.py
│   ├── custom_datasets.py
│   ├── fbdd.py                  # FBDD module
│   ├── fbdd_density.py
│   ├── spc.py
│   ├── myutils.py
│   ├── vision_transformer.py
│   ├── configs/
│   │   ├── base_config.py       # base config (model type = AquaBindSegmentation)
│   │   ├── cfg_AquaOV255.py
│   │   ├── cfg_dutuseg.py
│   │   ├── cfg_mas3k.py
│   │   ├── cfg_suimtrainval.py
│   │   ├── cfg_usis10kvaltest.py
│   │   └── cfg_usis16k.py
│   ├── depth_anything_v2/       # DepthAnything model
│   ├── dinov2/                  # DINOv2 backbone
│   ├── open_clip/               # Open-CLIP model
│   ├── prompts/
│   │   └── imagenet_template.py
│   ├── requirements.txt
│   ├── run.sh                   # run evaluation on all datasets
│   ├── dist_test.sh
│   ├── getclass_result.sh
│   └── get_miou_maccc_class.py
├── assets/
│   ├── Framework.jpg
│   └── Framework.pdf
└── README.md
```

## Dependencies and Installation

```
# create new anaconda env
conda create -n AquaBind python=3.10
conda activate AquaBind

# install torch and dependencies
pip install -r requirements.txt
```

## Model evaluation
Please modify some settings in `configs/base_config.py` before running the evaluation.

For **DepthAnything Model** and **Open-CLIP Model** please download from their official website or our [LINK](https://1drv.ms/f/c/69a773fee5342110/Es-h3W58AfVKkaqbgZHHxtoB97YPTtrl2lWUAw_64kma5A?e=Hk9Puc) and put them in `./pretrained_ckpt/`.

Evaluation on all datasets:
```
sh run.sh
```

The results will be saved in `./work_logs/`.
