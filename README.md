
# Financial Series Treatment and Triple Barrier Method
## About this project

I did this project as one of the parts from a Python test for my Master's degree.

The objective was to practice the treatment of financial time series.

For this I used tick by tick data from an IVE ETF (S&P 500 Value Index) and I developed 
the so-called ticks bars and dollar bars.

Using the Dollar bars, I run a labeling algorithm (Triple Barrier Method) and then 
I look for a way to get the number of labels for each class as balanced as possible

## Dataset
The data will be obtained from http://www.kibot.com/free_historical_data.aspx,
available in the section "free tick intraday data" subsection IVE: "Tick with bid ask
data".

## Financial Series Treatment

I load the data tick by tick in pandas, and calculate candles (open, high, low, close, vol) 
hourly, daily, monthly and yearly and then chart each one.
I create functions to calculate dollar bars and tick bars.
I compare return distributions of different candlestick types.

## Triple Barrier Method

#### Introduction

Lopez de Prado introduces a labeling technique known as the triple barrier method.

The triple barrier method involves “labeling an observation according to the first barrier 
touched of out three barriers, two horizontal barriers and one vertical barrier”.

The horizontal barriers can be thought as profit and loss and the vertical as an expiration.

![tbm](https://user-images.githubusercontent.com/121939304/211831107-f356016b-e0d0-4709-b648-2fc9eed42e7c.jpg)
Example of Triple Barrier Method (Lopez de Prado)

#### My code
Using the dollar bars also developed here I made a function that calculates for each sample 
a label, which will have value 0, 1 or -1. These values are determined depending on which 
barrier is touched first: 0 for the vertical barrier, 1 for the upper horizontal barrier 
and -1 for the lower one.  
The distance in percentage to the vertical barriers and the number of samples to 
the horizontal barrier are parameters of the function.

Then performed a study of the distance in percentage to the vertical barriers and the
number of samples to the horizontal, looking for a way to obtain the number of labels 
of each class (0, -1 and 1) as balanced as possible.


