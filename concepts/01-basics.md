# PowerLanguage Basics

## Overview

PowerLanguage is MultiCharts' programming language for creating indicators, strategies, and functions. It's compatible with TradeStation's EasyLanguage.

## Study Types

### 1. Indicators

Visual tools that plot on charts. Used for technical analysis.

```powerlanguage
// Simple Moving Average Indicator
Inputs: Length(14);
Variables: SMA(0);

SMA = Average(Close, Length);
Plot1(SMA, "SMA");
```

### 2. Signals (Strategies)

Automated trading logic with entry/exit rules.

```powerlanguage
// Simple Crossover Strategy
Inputs: FastLength(9), SlowLength(21);
Variables: FastMA(0), SlowMA(0);

FastMA = Average(Close, FastLength);
SlowMA = Average(Close, SlowLength);

If FastMA crosses above SlowMA then
    Buy next bar at market;

If FastMA crosses below SlowMA then
    Sell next bar at market;
```

### 3. Functions

Reusable code blocks that return values.

```powerlanguage
// Function: PercentChange
Inputs: Value1(NumericSimple), Value2(NumericSimple);

If Value2 <> 0 then
    PercentChange = ((Value1 - Value2) / Value2) * 100
else
    PercentChange = 0;
```

## Data Types

| Type | Description | Example |
|------|-------------|---------|
| `Numeric` | Numbers | `Variables: MyVar(0);` |
| `TrueFalse` | Boolean | `Variables: IsValid(false);` |
| `String` | Text | `Variables: MyText("");` |

## Reserved Words (Bar Data)

- `Open` - Opening price
- `High` - Highest price
- `Low` - Lowest price
- `Close` - Closing price
- `Volume` - Trading volume
- `OpenInt` - Open interest
- `Date` - Bar date
- `Time` - Bar time

## Bar Referencing

Access historical bars using brackets:

- `Close[0]` - Current bar close (same as `Close`)
- `Close[1]` - Previous bar close
- `Close[n]` - n bars ago

## Comments

```powerlanguage
// Single line comment

{ Multi-line
  comment block }
```
