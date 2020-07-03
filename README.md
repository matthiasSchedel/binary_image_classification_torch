# Doku Vorgehensweise:
## Verwendete Libs
* numpy
* pytorch
* torchvision
* matplotlib
* PIL
* tensorboard

## Arch Code/Networks
* Base: Resnet 18
* mit linear input layer 512x2
* SGD optiizer mit lr von 0.001 und momentum von 0.9
* 100 epochs for training
* LR decay by fator of 0.1 every 20 epochs
* CrossEntropyLoss

## Optimierung:
* Testern verschiedener parameter für: 


## Data Pre-Processing:
Train = alle ungeraden X_ bilder
Valuation = alle geraden X_ bilder
resize by factor .25
using shell scripts

## Data transformationen:

```
data_transforms = {
    'train': transforms.Compose([
        transforms.RandomResizedCrop(224),
        transforms.RandomHorizontalFlip(),
        transforms.ToTensor(),
        transforms.Normalize([0.485, 0.456, 0.406], [0.229, 0.224, 0.225])
    ]),
    'val': transforms.Compose([
        transforms.Resize(256),
        transforms.CenterCrop(224),
        transforms.ToTensor(),
        transforms.Normalize([0.485, 0.456, 0.406], [0.229, 0.224, 0.225])
    ]),
}
```