Financials database currently holds stock prices and St. Louis Fed macro data series. New data is uploaded at end of each day. 

List of available data series can be gathered through the following code:

```
SELECT TOP (1000) [id]
      ,[description]
      ,[longDescription]
      ,[source]
  FROM [datax].[dbo].[seriesDesc]
  ```
[source] is for macroseries st. louis fred, or for stock prices alphavantage

In order to get historical values of stock price VTR use the following view

```
SELECT TOP (1000) [timestamp]
      ,[description]
      ,[close]
      ,[high]
      ,[low]
      ,[open]
      ,[volume]
  FROM [datax].[dbo].[vStockSeries]
  where [description] = 'VTR'
  order by [timestamp] desc
```
And for FRED macro series; ex; SP500 index series :

```
SELECT TOP (1000) [date]
      ,[description]
      ,[value]
  FROM [datax].[dbo].[vFredSeries]
  where [description] = 'SP500'
  order by date desc
```