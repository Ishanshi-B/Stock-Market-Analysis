# Stock Analysis Project

This project is designed to analyze historical stock data for some automotive companies using Python. It fetches data from Yahoo Finance, processes it, and provides visualizations to help understand stock performance over time. 

## How It's Made:
**Tech used:** Python, Pandas, Matplotlib, yFinance, Jupyter Notebook

This project was built using Python, focusing on data analysis and visualization. The main libraries used include Pandas for data manipulation, Matplotlib for plotting, and yFinance for fetching stock data. The analysis was conducted in a Jupyter Notebook, allowing for an interactive data exploration. This project was made from the Udemy tutorial "Python for Financial Analysis and Algorithmic Trading."

Here's a brief overview of how the project was constructed:
- **Data Fetching:** Used yFinance to download historical stock data.
- **Data Processing:** Cleaned and formatted the data using Pandas.
- **Data Visualization:** Created various plots such as line charts for stock prices and bar charts for trading volumes using Matplotlib.


## Issues

There were several hurdles encountered during the development of this project:

1. **DataReader Updates**: The `pandas_datareader` library underwent updates that caused some of the previously working code to break. For instance, the method `web.DataReader("TSLA", 'google', start, end)` no longer works because Google Finance is no longer supported as a data source in `pandas_datareader`.

2. **Deprecated Features**: Some features and methods used in earlier versions of the libraries became deprecated. For example, certain methods in `yfinance` and `pandas_datareader` are no longer recommended and were replaced with new methods. This required revisiting the code and updating it to use the latest recommended practices.

3. **Data Fetching Issues**: There were issues with fetching the data reliably. The previous approach of using Google Finance through `pandas_datareader` stopped working, and alternatives had to be explored. This led to the adoption of `yfinance` as the primary method for fetching stock data.

4. **Switch to yFinance**: To overcome the data fetching issues, the project transitioned from using `pandas_datareader` to `yfinance`. `yfinance` proved to be a robust alternative for retrieving historical stock data from Yahoo Finance, ensuring that the project could continue to function.

### Specific Example: Tesla Data Fetching
The code snippet `web.DataReader("TSLA", 'google', start, end)` used to fetch Tesla's stock data from Google Finance no longer works because Google Finance API support was removed. This necessitated a shift to a different data source. The new approach involves using `yfinance` to fetch the data:

```python

# Fetch data for Tesla using yfinance
ticker = ['TSLA']
data = yf.download(ticker, start=start, end=end)

```

By making these changes, we ensured that the project could fetch the necessary stock data reliably and continue to function as intended.

## Lessons Learned
Throughout this project, I learned a lot about data analysis and visualization in Python. Some key takeaways include:
- **Data Handling:** Gained a deeper understanding of using Pandas for efficient data manipulation.
- **Visualization Techniques:** Improved my skills in creating clear and informative visualizations using Matplotlib.
- **Staying Updated:** Staying updated on Python and its different libraries is helpful when it comes to any sort of data manipulation and finance work especially as you might not get the desierd output because of Deprecated features.
