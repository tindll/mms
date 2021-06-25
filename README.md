# **MMS**
- ### General Statements :
   Although it would be unfair to still call this a proof of concept, this project is still unfinished. I undoubtedly intend on continuing it.
   The goal for this project wasn't to make an algorithm capable of making a profit, despite the name, but more so to serve as an introduction to the automation
   of trading and machine learning. <br>In hindsight, I may have set my expectations too high from the start, seeing as either of the two aforementioned subjects alone      would have provided me with more than enough work and research to do.
   
   For the main algorithm, I could have simply adopted a trend following or mean reversion on high timeframe approach (to simplify the entry conditions for a      trade & reduce trade frequency) but instead I went for a technical analysis approach. <br>I went this route as I wanted to trade on lower timeframes with relatively      high frequency.<br> This can result in bad signals and significantly increases risk.
   
   The signals generated by the algorithm still need work (some like DMI/ADX cross are just wrong), others need some tweaking and thorough backtesting.
   <br>***It's for this reason that the algorithm does not currently open any real positions.***
   <br>The algorithm looks for positions on the 15m, 1h & 1D charts, for 10 different cryptocurrencies.
   <br>It looks for positions based mainly on RSI divergences, MACD crossovers & Bollinger bands.

         
     ![most recent chart](https://github.com/tindll/mms/blob/main/chart.png)

- ### Simplified rundown:

   1)'TA_ALGO.py' connects to Binance's API. It retrieves OHLC information from the API, then calls functions from various different python libraries such as pandas,      mplfinance and finta. Thanks to these libraries, the algorithm produces charts, like the one above, based on dataframes containing the OHLC data.
   
   2)Several functions, like 'find_macd_signalCrossovers(df)' & 'find_divergences(df)', are then called on the dataframe to analyze the data and to find potential          positions.
   
   3)If a position is found, it is added to 'trades.json' with all pertinent information to that trade (open price, position type ...).
   'trades.json' is then sent to http://www.zjamsty.com/ , where all recent trades are shown with their respective charts (like the one above).

   4)'TA_ALGO.py' also produces a .csv file from the dataframe that contains price and indicator information.
   That .csv file (dfCSV.txt) is then sent to my docker container 'intelligent_goldberg'
   
   5)'test1.py' & 'test2.py' (more information is available in 'ml_models'), 2 ML models, are then executed in the container.

- ### What now ?
   Having spent most of my time recently; either learning about trading with techinical analysis and the basic principles of machine learning or failing resit exams,
   I intend on taking a break.
   <br> Having said that, there are still many tasks that I haven't yet done, including pattern recognition (like in [this paper](https://mpra.ub.uni-muenchen.de/60825/1/MPRA_paper_60825.pdf) or [this one](https://projet.liris.cnrs.fr/imagine/pub/proceedings/ICANN-2010/papers/6354/63540130.pdf))
   <br> I have a solid foundation (that still needs a considerable amount of work), a lot can be improved upon, a non-exhaustive list could be :
   fixing everything that's wrong with what I already have, create a backtesting engine, create more robust classification model, making the website better...
   <br> And that's just off the top of my head.


*List of tasks in progress and to do are under the project tab.*

