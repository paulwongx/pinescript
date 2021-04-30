## PineScript

### Inputs

```js
// Study vs Strategy
study(
	title,
	shorttitle,
	overlay,
	format,
	precision,
	scale,
	max_bars_back,
	max_lines_count,
	max_labels_count,
	resolution,
	resolution_gaps
);
strategy(
	title,
	shorttitle,
	overlay,
	format,
	precision,
	scale,
	pyramiding,
	calc_on_order_fills,
	calc_on_every_tick,
	max_bars_back,
	backtest_fill_limits_assumption,
	default_qty_type,
	default_qty_value,
	initial_capital,
	currency,
	max_lines_count,
	max_labels_count,
	slippage,
	commission_type,
	commission_value,
	process_orders_on_close,
	close_entries_rule
);

// Inputs
length = input(title="Length", type=integer, minval=1, defval=14)
src = input(title="Source", type=source, defval=close)

from_month = input(defval = 1, title = "From Month", minval = 1, maxval = 12)
from_day   = input(defval = 1, title = "From Day", minval = 1, maxval = 31)
from_year  = input(defval = 2021, title = "From Year")
to_month   = input(defval = 1, title = "To Month", minval = 1, maxval = 12)
to_day     = input(defval = 1, title = "To Day", minval = 1, maxval = 31)
to_year    = input(defval = 9999, title = "To Year")
start  = timestamp(from_year, from_month, from_day, 00, 00)  // backtest start window
finish = timestamp(to_year, to_month, to_day, 23, 59)        // backtest finish window
window = time >= start and time <= finish ? true : false // create function "within window of time"

// Buy & Sell
strategy.entry("buy", strategy.long, 4, when=strategy.position_size <= 0)
strategy.entry("sell", strategy.short, 6, when=strategy.position_size > 0)

// Variables
bar_index                   Current bar index. 0 to infinity

```

## Resources

[3Commas Webhook URL](https://3commas.io/trade_signal/trading_view)
[Trading Indicators](https://zenandtheartoftrading.com/indicators/)
[Pandas Technical Analysis Indicators](https://github.com/twopirllc/pandas-ta)
[Python Technical Analysis Indicators](https://github.com/bukosabino/ta)
[Python TA-Lib](https://github.com/mrjbq7/ta-lib)
[Kelly Criterion in PineScript](https://www.tradingview.com/script/20AKzpqU-Trailing-Kelly-Ratio/)
[Pinescript Indicators](https://github.com/everget/tradingview-pinescript-indicators)
[Pine Script Documentation](https://www.tradingview.com/pine-script-reference/v4/)
[Kodify Example Strategies](https://kodify.net/tradingview/strategies/)