# Pytorch-Lightning-Template

## colab workflow

### quick run

+ First use[graph_test.ipynb](graph_test.ipynb) to test data and net algorithm
+ Then use [graph_colab_clasification_main.ipynb](graph_colab_clasification_main.ipynb) to test Net performance

### run

update `colab_main` repo url and floder name

1. push local code to remote
2. open github notebook in colab
3. change to gpu
4. clone code to google drive
5. use `git pull` to update code
6. run

### How to use `colab_main`

1. Init Net
2. pass Net instance to MInterface

### Problems

1. [dictionary update sequence element #0 has length 1; 2 is required](https://github.com/Lightning-AI/lightning/issues/9318)
   when run Trainer?

```
    def __init__(self, some_method, n_features: int, n_classes: int):
        ...
        save_hyperparameters(ignore=["model"])
```

Do not save the weights of the model to hparams.yaml

2. Need last state grad in RNN?
use `state.data` instead of `state`, otherwise graph think it need last state to compute
