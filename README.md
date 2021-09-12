# algo-tradegator

This project is a collaboration between a number of cohort members of a FinTech Bootcamp through Monash Uni (Australia).  What we're attempting to build is an Algorithmic Trader which incorporates a number of signals (indicators and other inputs) into which a Machine Learning Model is created and trained.  Using the ML model we create, trades can be made based on what the model predicts.  Thus the name for our repo: algo-tradegotor :D

---

## Preamble

The current version of the Algo-Tradegator as is avialable (in this repo as of this very comment), is not what we would be happy with declaring as the final version.  It isn't. It is fairly redamentary, but illustrates what we wanted to demonstrate.  It needs more work; that much is true.

## Tradegator

### Notebook Approach

**Trading Signals**  
The Notebook runs through the pulling of data, and prepping the data for determining trading signals.  

This is done through calculating a number of standard/popular indicators used by contemporary technical analysis, moving averages and the like, and then calculates entry and exit signals based on those indicators.

It then visualises the entry and exit signals, afterwhich it runs through the effect on a portfolio of $100k should the entry and exit signals have been executed as they arose ... so it visualises the back-testing of those signals. 

**Machine Learning**  
The Notebook then takes the signals generated earlier and uses those only as the *features* for the machine learning model. In our case we chose to use the Linear Regression, Random Forests Model ... very fast for fairly simplistic data.  

Our target was "positive return", i.e. taking the return and if it was positive, transform as a 1 and if negative, a 0.

We then use an amazing library, *Facets* to help visualise the training and testing sets of data for both the full set of all data and then features.  Facets makes this task very easy, hence our use of it.

### Notebook Instructions  

The Notebook will work equally well on either Google Colab or Jupyter Notebook.  For Colab though, ensure the required files are uploaded; these are: - 
- `./Resources/btc-usd_2014-2021.csv`
- `./vertex_results/BTC-USD_vertex_preds.csv`  

For all executions, ensure you set the variables, before execution.
- To make life easy, use Bitcoin 
  - `ticker = 'BTC-USD'`
  - `live = False`    -> for Colab, use `False`
  - `colab = False`   -> for Colab, use `True`, obviously
  - `vertex = False`  -> for `BTC-USD`, use `True`, else `False`
- If you don't want to use Bitcoin, use any Ticker, but then you need to have `live = True` to ensure the Notebook can pull data live from Pandas Datareader.

Then run through the Notebook, and have fun with the analysis.  Make sure you pause with the use of *Facets* and explore its use; it is exceptionally powerful for what it is.

## Google Vertex AI  

### Process  

We decided to use Google Vertex AI for 2 main reasons, firstly in learning what Google has to offer as opposed to AWS and secondly for the purposes of comparing a model that runs in seconds as opposed to hours.

### Quick Overview

- Requires Google account
- Upload data
- Analyse data
- identify features, target and split
- Generate model

... and then wait ...  

  ![Oops, image not available](./Images/spoungebob_3_hours_later.png "And wait ...")  

### Detailed Look at Vertex AI  

For a more detailed look at Vertex, please dive into the [following PDF](./Resources/Google-Vertex-Summary-and-Walkthrough.pdf), which has been included in the repository and explains a little more about it (with some URLs to learning more) and then shows the process we went through with screenshots.

If you're even more curious, look at the screenshots found in `./Images`.

---
# Acknowledgments
## Non-standarad Libraries Used
- Pandas Datareader:  An amazingly fast/easy means of downloading pricing data
- [Facets](https://pair-code.github.io/facets/): A POWERFUL library for visualising data!  Useful for comparing training and testing data.
  - Facets allows for visualising data from both an overview as well as a detailed level; these are provided by *Facets Overview* and *Facets Dive*, respectively.
## Sources
- We have used a new Pandas package, `pandas-datareder` to read in some additional data for this project.  We learnt about this package from jakevdp [here](https://jakevdp.github.io/PythonDataScienceHandbook/03.11-working-with-time-series.html).
- Spongebob Fandom was the source of the Spongebob image; license, trademarks and terms of use are attributed to original owners (source [here](https://spongebob.fandom.com/wiki/List_of_instances_in_which_the_fourth_wall_is_broken))
