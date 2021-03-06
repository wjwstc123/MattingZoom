# MattingZoom
A PyTorch-based library for trimap-free matting. A complete project will be released soon!



## Supported Models:
- [x] SHM
- [x] U2Net
- [x] MODNet
- [x] GFM
- [x] P3M-Net
- [ ] LF
- [ ] HATT

## Supported Loaders:

- [x] U2Net
- [x] GFM
- [x] P3M-Net
- [x] FBDM

## Usage

`python public_worker.py --model GFM`

## The requirement for extending custom method.
- model file: 
  - Put the model file in the **models** directory.
  - The name of model file should follow **[custom]_net**.
  - The class name should follow **[custom]_Net**.
  - The parameter of __init__ of **[custom]_Net** must is **args**.
  - The last return of **forward** must is the **matte** ~ [0,1].
- trainer file:
  - Put the model file in the **traners** directory.
  - The name of traner file should follow **[custom]_traner**.
  - The function name should follow **[custom]_Trainer**.
  - The returns of **[custom]_Trainer** should a loss dict, which requires the first key is *loss*.
- config file:
  - Put the config file in the **config** directory.
  - The name of config file should follow **[custom]_config.yaml**.
  - warming: the values in config file will become the value of **args**.
