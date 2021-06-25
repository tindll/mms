# **MMS**
- ### General Statements :
   Although it would be unfair to still call this a proof of concept, this project is still unfinished. I undoubtedly intend on continuing it.
   
   The goal for this project wasn't to make an algorithm capable of making a profit, despite the name, but more so to serve as an introduction to the automation
   of trading and machine learning. <br>In hindsight, I may have set my expectations too high from the start, seeing as either of the two aforementioned subjects alone      would have provided me with more than enough work and research to do.
   
   For the main algorithm, I could have simply adopted a trend following or mean reversion on high timeframe approach (to simplify the entry conditions for a      trade & reduce trade frequency) but instead I went for a technical analysis approach. <br>I went this route as I wanted to trade on lower timeframes with relatively      high frequency.<br> This can result in bad signals and increases risk significantly.
   
   The signals generated by the algorithm still need work (some like DMI/ADX cross are just wrong), some tweaking and thorough backtesting.
   <br>The algorithm looks for positions on the 15m, 1h & 1D charts, for 10 different cryptocurrencies.
   <br>It looks for positions based mainly on RSI divergences, MACD crossovers & Bollinger bands.

         
     ![most recent chart](https://github.com/tindll/mms/blob/main/chart.png)

- ### Simplified rundown:

   1)'TA_algo.py' connects to Binance's API. It retrieves OHLC information from the API, then calls functions from various different python libraries such as pandas,      mplfinance and finta. Thanks to these libraries, the algorithm produces charts, like the one below, based on dataframes containing the OHLC data.
   
   2)Several functions, like 'find_macd_signalCrossovers(df)' & 'find_divergences(df)', are then called on the dataframe to analyze the data and to find potential          positions.
   
   3)If a position is found, it is added to 'trades.json' with all pertinent information to that trade (open price, position type ...).
   'trades.json' is then sent to http://www.zjamsty.com/ , where are recent trades are shown with their respective charts (like the one above).


1) A python script will create signals when it thinks it's a good time to enter a position (short/long), based on RSI divergences, close above/below bbands, macd crossovers and potentially ichimoku clouds (given a better understanding of clouds).
The python code also produces charts (as seen below) and I would like to make a website that shows all active trades with pertinent information : http://www.zjamsty.com/

2) I would also like to try and make a regression based machine learning AI using tensorflow. (My python code produces a CSV like file (see c:\data\pandas.txt), and thanks to the binance API, I have access to a near unlimited supply of price information, my datasets will be produced thanks to these "CSV" files)





*List of tasks in progress and to do are under the project tab.*

