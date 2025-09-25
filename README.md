## Part 0: Setup virtual environment

1. Clone the project repository to your local machine:
2. Create and switch to a new branch named `dev-[yourname]`
3. Create a new virtual environment named `.venv`
4. Activate the virtual environment

## Part 1: Warmup exercise

1. Go to the jupyter notebook `warmup.ipynb`

## Part 2: Backend (Python with Pandas) - Financial Data Analysis (30 minutes)

You will analyze a financial dataset using Python and Pandas. We’ll provide a CSV file named `financial_data.csv` in your working directory with ~100 rows and the following columns:
- `date`: Date in YYYY-MM-DD format.
- `stock_symbol`: String (e.g., "AAPL", "GOOG").
- `open_price`: Float (stock’s opening price).
- `close_price`: Float (stock’s closing price).
- `volume`: Integer (trading volume).

**Example CSV Content** (for reference):
```
date,stock_symbol,open_price,close_price,volume
2025-01-01,AAPL,150.00,152.50,1000000
2025-01-02,AAPL,152.00,151.75,800000
2025-01-01,GOOG,2500.00,2525.00,500000
...
```

Write a Python script (e.g., `analyze_financials.py`) to perform the following tasks using Pandas.

### Requirements
1. Load the CSV into a Pandas DataFrame.
2. Compute and print the following:
   - **Average close price** across all stocks.
   - **Total trading volume** for each stock (group by `stock_symbol` and sum `volume`).
   - **Date with the highest close price** for a specific stock (e.g., ask the interviewer for a stock symbol like "AAPL", or hardcode one for testing).
3. Create a new DataFrame containing only rows where `close_price > open_price` (i.e., days the stock gained value).
4. Save the filtered DataFrame to a new CSV file named `gains.csv`.
5. Handle errors gracefully (e.g., missing file or invalid data) using try-except blocks.

**Example Starter Code**:
```python
import pandas as pd

def main():
    try:
        df = pd.read_csv('financial_data.csv')
        # Your code here...
        
        print("Average close price:", avg_close)
        print("Total volume by stock:", volume_by_stock)
        # etc.
        
        filtered_df.to_csv('gains.csv', index=False)
    except FileNotFoundError:
        print("CSV file not found.")
    except Exception as e:
        print(f"Error: {e}")

if __name__ == "__main__":
    main()
```

**Testing**: Run your script and show the output (average, volumes, max price date, and confirm `gains.csv` is created).  
**Bonus** (if time allows): Add a simple visualization (e.g., use Matplotlib to plot `close_price` over time for one stock), but this is optional.