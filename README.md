看季节性，趋势等的图
import statsmodels.api as sm
res = sm.tsa.seasonal_decompose(x,freq=12, model = 'multiplicative')
fig = res.plot()
fig.show()
