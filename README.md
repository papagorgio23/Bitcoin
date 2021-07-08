# Bitcoin
RNN Model to predict bitcoin price

## Google Colab Notebook

The notebook with the steps to develop the neural network can be found [here](https://github.com/papagorgio23/Bitcoin/blob/main/RNN_Notebook.ipynb)


## Run Model

This program was developed using [poetry](https://python-poetry.org/). After installing poetry by following their documentation, you will be able to reproduce this program on your computer with the following code:


#### Prepare Enviornment:

``` bash
git clone https://github.com/papagorgio23/Bitcoin.git
cd Bitcoin

poetry shell
poetry install
```


There are 2 options when running the program - `Train` or `Eval`

Train will train a new RNN model and Eval will load and use the previously trained RNN model.


#### Train New Model:

``` bash
python main.py --train Train
```

or 

#### Evaluate Previous Model:

``` bash
python main.py --train Eval
```
