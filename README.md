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



# Problem Questions:

* **Does this data set even make sense? What are the limitations of this data set?**
* **Is the lookback window of 60 seconds helpful? What are its limitations? What other features would you want to see in this data set?**

This dataset is very limited. When modeling, more data is typically better and there were only 10k seconds of prices for our model to learn from. It would be helpful if there were substantially more data to train on. I found the lookback window of 60 seconds to be very useful. The current price of bitcoin is heavily dependent on the recent price of bitcoin. I only used the price and ignored the other columns. The volume may have improved the model but I was able to achieve a decent RMSE only using the lookback price.

* **If you stuck with the neural network, what did you change to make it better? Did you change the architecture, did you change the optimizer? The learning rate? The activation function(s)? Why was the model stuck at `0` with an incredibly high root mean squared error?**

I stuck with a neural network but decided to use a LSTM RNN model. This model architecture is perfect for modeling time series or sequential datasets, which bitcoin price follows into. I kept the Adam optimization function with a 0.01 learning rate and was able to achieve accurate results with only 10-20 epochs. 

* **Did you include any regularization strategies in your model? If so, why'd you choose the one you did?**

I scaled the bitcoin prices on a 0-1 scale for the neural network. Models achieve better results when the input data is scaled, especially deep neural networks.

* **Did you include visualizations? (everyone loves a good graphic)**

I included some visualizations in the [notebook](https://github.com/papagorgio23/Bitcoin/blob/main/RNN_Notebook.ipynb) but not in the actual python program. I visualized the model's predicted prices vs the actual prices as well as the RMSE during the model training process. 


