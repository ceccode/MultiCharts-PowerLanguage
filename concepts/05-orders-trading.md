# Orders and Trading

## Entry Orders

### Market Orders

```powerlanguage
// Long entry
Buy next bar at market;
Buy ("Long Entry") next bar at market;

// Short entry
Sell Short next bar at market;
SellShort ("Short Entry") next bar at market;
```

### Limit Orders

```powerlanguage
// Buy at specific price or better
Buy next bar at 100.00 limit;

// Sell short at specific price or better
SellShort next bar at 105.00 limit;
```

### Stop Orders

```powerlanguage
// Buy when price rises to level
Buy next bar at 100.00 stop;

// Sell short when price falls to level
SellShort next bar at 95.00 stop;
```

## Exit Orders

### Market Exits

```powerlanguage
// Exit long position
Sell next bar at market;
Sell ("Exit Long") next bar at market;

// Exit short position (cover)
Buy to Cover next bar at market;
BuyToCover ("Exit Short") next bar at market;
```

### Limit Exits (Take Profit)

```powerlanguage
// Exit long at profit target
Sell next bar at EntryPrice + 5.00 limit;

// Exit short at profit target
BuyToCover next bar at EntryPrice - 5.00 limit;
```

### Stop Exits (Stop Loss)

```powerlanguage
// Exit long at stop loss
Sell next bar at EntryPrice - 2.00 stop;

// Exit short at stop loss
BuyToCover next bar at EntryPrice + 2.00 stop;
```

## Position Sizing

```powerlanguage
// Buy specific number of contracts/shares
Buy 100 shares next bar at market;
Buy 2 contracts next bar at market;

// Variable position size
Variables: PositionSize(0);
PositionSize = 1000 / Close;  // $1000 worth
Buy PositionSize shares next bar at market;
```

## Position Information

| Keyword | Description |
|---------|-------------|
| `MarketPosition` | Current position: 1=long, -1=short, 0=flat |
| `CurrentShares` | Number of shares/contracts held |
| `CurrentContracts` | Same as CurrentShares |
| `EntryPrice` | Average entry price |
| `EntryPrice(n)` | Entry price of nth entry |
| `BarsSinceEntry` | Bars since position opened |
| `OpenPositionProfit` | Unrealized P&L |

```powerlanguage
// Only enter if flat
If MarketPosition = 0 then
    Buy next bar at market;

// Exit after 10 bars
If BarsSinceEntry >= 10 then
    Sell next bar at market;

// Trail stop based on entry
If MarketPosition = 1 then
    Sell next bar at EntryPrice * 0.98 stop;
```

## Built-in Stop Functions

```powerlanguage
// Set stop loss (points)
SetStopLoss(100);

// Set profit target (points)
SetProfitTarget(200);

// Set breakeven stop
SetBreakeven(50);  // Move to breakeven after 50 points profit

// Set dollar trailing stop
SetDollarTrailing(500);

// Set percent trailing stop
SetPercentTrailing(2);
```

## Order Naming

```powerlanguage
// Named orders for tracking
Buy ("MA Cross Long") next bar at market;
Sell ("MA Cross Exit") next bar at market;

// Check which order filled
If MarketPosition = 1 and EntryName = "MA Cross Long" then
    Print("Entered via MA Cross");
```
