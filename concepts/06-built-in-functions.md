# Built-in Functions

## Moving Averages

```powerlanguage
// Simple Moving Average
Average(Close, 14)
AverageFC(Close, 14)  // Fast calculation

// Exponential Moving Average
XAverage(Close, 14)

// Weighted Moving Average
WAverage(Close, 14)

// Adaptive Moving Average
AdaptiveMovAvg(Close, 14, 2, 30)
```

## Price Functions

```powerlanguage
// Highest/Lowest over N bars
Highest(High, 20)      // Highest high
Lowest(Low, 20)        // Lowest low
HighestBar(High, 20)   // Bars ago of highest
LowestBar(Low, 20)     // Bars ago of lowest

// Range
Range                  // High - Low (current bar)
TrueRange             // True range
AvgTrueRange(14)      // ATR

// Typical/Median Price
TypicalPrice          // (H + L + C) / 3
MedianPrice           // (H + L) / 2
```

## Momentum/Oscillators

```powerlanguage
// RSI
RSI(Close, 14)

// Stochastic
SlowK(14)
SlowD(14)
FastK(14)
FastD(14)

// MACD
MACD(Close, 12, 26)
MACDAvg(Close, 12, 26, 9)
MACDDiff(Close, 12, 26, 9)

// CCI
CCI(14)

// Momentum
Momentum(Close, 14)
RateOfChange(Close, 14)
```

## Volatility

```powerlanguage
// Standard Deviation
StdDev(Close, 20)

// Average True Range
AvgTrueRange(14)

// Bollinger Bands
BollingerBand(Close, 20, 2)   // Upper
BollingerBand(Close, 20, -2)  // Lower

// Keltner Channel
KeltnerChannel(20, 1.5)
```

## Volume Functions

```powerlanguage
// Volume averages
Average(Volume, 20)

// On Balance Volume
OBV

// Volume Rate of Change
VolumeROC(14)
```

## Math Functions

```powerlanguage
// Basic math
AbsValue(-5)          // 5
Square(4)             // 16
SquareRoot(16)        // 4
Power(2, 3)           // 8
Log(100)              // Natural log
ExpValue(1)           // e^1

// Rounding
Round(3.7, 0)         // 4
IntPortion(3.7)       // 3
Ceiling(3.2)          // 4
Floor(3.7)            // 3

// Min/Max
MaxList(a, b, c)      // Maximum of list
MinList(a, b, c)      // Minimum of list

// Trigonometry
Sine(degrees)
Cosine(degrees)
Tangent(degrees)
ArcTangent(value)
```

## String Functions

```powerlanguage
// Concatenation
Text1 = "Price: " + NumToStr(Close, 2);

// Conversion
NumToStr(123.45, 2)   // "123.45"
StrToNum("123")       // 123

// String operations
StrLen("Hello")       // 5
LeftStr("Hello", 2)   // "He"
RightStr("Hello", 2)  // "lo"
MidStr("Hello", 2, 3) // "ell"
```

## Date/Time Functions

```powerlanguage
// Current bar
Date                  // YYYMMDD format
Time                  // HHMM format
DateTime              // Combined

// Components
Year(Date)
Month(Date)
DayOfMonth(Date)
DayOfWeek(Date)       // 0=Sunday, 6=Saturday

// Session
SessionStartTime
SessionEndTime
BarsSinceSession
```

## Bar Counting

```powerlanguage
CurrentBar            // Current bar number
BarNumber             // Same as CurrentBar
TotalBarsLoaded       // Total bars on chart
LastBarOnChart        // True if last bar
```
