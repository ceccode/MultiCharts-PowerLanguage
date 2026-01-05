# Control Flow

## Conditional Statements

### If-Then

```powerlanguage
If Close > Open then
    Plot1(Close, "Bullish");
```

### If-Then-Else

```powerlanguage
If Close > Open then
    Plot1(Close, "Bullish")
else
    Plot1(Open, "Bearish");
```

### If-Then Begin-End (Multiple Statements)

```powerlanguage
If Close > Open then begin
    Plot1(Close, "Bullish");
    Alert("Bullish bar");
end;
```

### If-Then-Else Begin-End

```powerlanguage
If Close > Open then begin
    Plot1(Close, "Bullish");
    SetPlotColor(1, Green);
end
else begin
    Plot1(Open, "Bearish");
    SetPlotColor(1, Red);
end;
```

### Nested Conditions

```powerlanguage
If Close > Open then begin
    If Volume > Average(Volume, 20) then
        Alert("Strong bullish bar");
end;
```

## Comparison Operators

| Operator | Description |
|----------|-------------|
| `=` | Equal to |
| `<>` | Not equal to |
| `>` | Greater than |
| `<` | Less than |
| `>=` | Greater than or equal |
| `<=` | Less than or equal |
| `crosses above` | Crosses over |
| `crosses below` | Crosses under |

## Logical Operators

| Operator | Description |
|----------|-------------|
| `and` | Both conditions true |
| `or` | Either condition true |
| `not` | Negation |

```powerlanguage
If Close > Open and Volume > 1000 then
    Alert("High volume bullish");

If Close > High[1] or Close < Low[1] then
    Alert("Breakout");

If not (Close > Open) then
    Alert("Not bullish");
```

## Loops

### For Loop

```powerlanguage
Variables: Sum(0), i(0);

Sum = 0;
For i = 0 to 9 begin
    Sum = Sum + Close[i];
end;
```

### While Loop

```powerlanguage
Variables: Counter(0);

Counter = 0;
While Counter < 10 begin
    Print(Counter);
    Counter = Counter + 1;
end;
```

## Switch/Case (Condition)

```powerlanguage
Condition1 = Close > Open;
Condition2 = Close < Open;

If Condition1 then
    // Bullish logic
else if Condition2 then
    // Bearish logic
else
    // Neutral logic
```
