<h1>DailyBigPlayerCandlestickWithPercentileRank</h1>



<h2>Description</h2>
 The program computes the volume-to-outstanding shares ratio based on all daily transactions (including buys and sells). It then outputs the number of buy and sell transactions exceeding a user-defined percentile threshold.
<br />


<h2>Languages and Libraries Used</h2>

- <b>Python</b> 
- <b>Matplotlib</b>
- <b>NumPy</b>
- <b>CSV</b>

<h2>Environments Used </h2>

- <b>Windows 10 Pro</b>
- <b>Jupyter Notebook</b>

<h2>Program walk-through:</h2>

<p align="justify"> The Program walk-through is a variation to <a href="https://github.com/DrShah-Quant/PeriodBigPlayers"> PeriodBigPlayers </a> and <a href="https://github.com/DrShah-Quant/PeriodBigPlayer"> PeriodBigPlayersCandlesticks </a> except in this version I have enabled cutomization on the percentile selection, and big players filteration is as a ratio of outstanding shares calculated on daily basis. The significance of this approach is explained in more detail in the following paragraphs. </p>

<p align="justify"> The example run presented here is from a Jupyter Notebook environment. You can run the file using Ctrl+Enter key presses. Alternatively you can run the python script <i>DailyBigPlayerCandlestickWithPercentileRank.py</i> using command <i>python DailyBigPlayerCandlestickWithPercentileRank.py</i> in a command line if you have python installed properly. The program is depended on a CSV file containing stock transactions raw data. In the example presented below, I have used raw data provided by M+ Securities, a Malaysian stock broker. The raw data contains comma separated values organized into the following colums: "Time","Type","Price","Chg","Vol","Value". "Time" is the time when the transaction occured. "Type" refers to the type of transaction such as buy, close, and open. "Price" refers to the price the share was transacted. "Chg" refers to the difference from the previous price. "Vol" refers to the transaction volume measured in lot sizes (1 lot = 100 shares). And finally "Value" refers to the value of the trasaction (i.e. no of shares x share price). </p>

<p align="center">
Sample CSV raw data : <br/>
<img src="https://i.imgur.com/ZwC3mJi.png" height="80%" width="80%" />
<br />
 <br/>
Launch the Program and enter CSV data file location, percentile, and outstanding shareholders : <br/>
<img src="https://i.imgur.com/KPWRSbx.png" height="80%" width="80%"/>
<br />
<br />
Legend:  <br/>
<img src="https://i.imgur.com/SJArPMm.png" height="80%" width="80%" />
<br />
<br />
Above X percentile buy/sell volume transactions along with Japanese Candlestics: <br/>
<img src="https://i.imgur.com/jTvHRG4.png" height="80%" width="80%" />
<br />
 <p align="justify"> The figure above shows periodic time series illustrating the top X% volume transactions along with Japanese Candlestics. Assuming big players (e.g. fund managers, high net worth individuals, etc) transact in large quantities, from this figure we can know at what price and when the transactions occur. This program provides flexibility to the users to determine the X percentile. Further, the percentile calculation is done on the ratio of volume/outstanding shares over all the transactions of a day. In <a href="https://github.com/DrShah-Quant/PeriodBigPlayers"> PeriodBigPlayers </a> and <a href="https://github.com/DrShah-Quant/PeriodBigPlayer"> PeriodBigPlayersCandlesticks </a>, i have interpreted big players in an absolute manner for the period in interest (specified by the number of CSV files -- each CSV file provides transactions for a day), however, in this program, the big players are interpreted in relative manner relaive to outstanding shares. Users can also specity the percentile, so for example, if the percentile is 70%, then the program will pick top daily 30% big players relative to outstanding shares. The augmented Japanese Candlesticks adds more insights (e.g. big players transactions at open and close, also along the body and tails).  </p>
<br />
Number of buy and sell transactions with volume per buy (or sell) transaction along with Japanese Candlestics:  <br/>
<img src="https://i.imgur.com/QCPxhJ8.png" height="80%" width="80%" />
<br />
 <p align="justify"> The figure above is a time series depicting the volume of buy (or sell) transactions at each price level across the time domain. The visualization highlights the price level that attracts the most buying or selling activity. Corresponding to this information, we are also presented with volume per buy(or sell) transaction at each price level to enable us analyse the magnitude of interest at each price level. The augmented Japanese Candlesticks adds more insights (e.g. overall transactions at open and close, also along the body and tails).    </p>
<br />

</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
