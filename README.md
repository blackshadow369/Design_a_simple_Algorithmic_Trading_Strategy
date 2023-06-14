# Design-a-simple-Algorithmic-Trading-Strategy

1. Designed a ScriptData class that will fetch US Stock with the following functions:
  #fetch_intraday_data(argument:script) : will fetch data from the API in json
  #convert_intraday_data(argument:script): will change the data to dataframe with given columns:
  -timestamp(data type: pandas.Timestamp)
  -open(data type: float)
  -high(data type:float)
  -low(data type:float)
  -close(data type:float)
  -volume(data type:int)
  
  also overloaded methods for the following operations:
  1. getitem
  2. setitem
  3. contains
 
2. Defined a function indicator1 that takes 2 arguments previous dataframe and timeperiod.
   And give output as another dataframe with 2 columns. 
   Timestamp: as timestamp
   Indicator: moving average fo the 'close' column.
   
3.Design a class Strategy that will do the following functionality
- Fetch intraday historical day using Scriptdata class
- Compute indicator data on following dataframe using indicator1 function
- Generate a pandas dataframe called signals with 2 columns:
  Timestamp: same as above
  signal: This columsn can have the following values:
          1. Buy(When: if indicator_data cuts close_data upwards)
          2. SEll(When: if indicator_data cuts close_data downwords)
          3. No_Signal (When: if indicator_data and close_data don't cut each other)
 -Print the 'signals' Dataframe with only those rows where the signals is either 'Buy' or 'Sell'
