import yfinance as yf
tickers = [“ Name of the Tickers from Yahoo Finance“]  			
#Ticker list for chosen stock exchange
data= yf.download(tickers, start="1998-11-30", end="1999-12-31", interval="1mo")['Adj Close']
data_1 = data.dropna(axis=1,how='all')
data_2 = data_1.dropna(axis=0,how='all')
data_3 = data_2.pct_change().dropna(axis=0,how='all')
data_4 =data_3.mean()
data_5= data_4[data_4 < 1]
results_data= data_5.nlargest(80)
#This code choses 80 highest return of chosen stocks
print(results_data)

#Code Alternative for results with NaN & Infinity;

data= yf.download(tickers, start="2003-12-30", end="2004-12-31", interval="1mo")['Adj Close']
data_1 = data.dropna(axis=1,how='all')
data_2 = data_1.dropna(axis=0,how='all')
a= data_2.dropna(axis=0, thresh=2)
b=a.replace(np.nan, 0)
c = b.replace('Infinity', 0)
d = c.replace('-Infinity', 0)
data_3 = d.pct_change()
data_4 = data_3.mean()
data_5= data_4[data_4 < 1]
results_data= data_5.nlargest(200)
print(results_data)
