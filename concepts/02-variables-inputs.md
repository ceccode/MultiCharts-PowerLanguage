# Variables and Inputs

## Inputs

Inputs are user-configurable parameters. They appear in the study's settings dialog.

```powerlanguage
// Numeric input with default value
Inputs: Length(14);

// Multiple inputs
Inputs: 
    FastPeriod(9),
    SlowPeriod(21),
    Multiplier(2.0);

// String input
Inputs: AlertMessage("Signal triggered!");

// Boolean input
Inputs: ShowPlot(true);
```

### Input Types

- `NumericSimple` - Single numeric value
- `NumericSeries` - Series of numeric values (for functions)
- `StringSimple` - Single string value
- `StringSeries` - Series of string values

## Variables

Variables store values that can change during execution.

```powerlanguage
// Numeric variable
Variables: MyValue(0);

// Multiple variables
Variables:
    Counter(0),
    Total(0),
    Average(0);

// Boolean variable
Variables: IsTriggered(false);

// String variable
Variables: Status("");

// IntraBar variable (resets each tick)
Variables: IntraBarVar(0, IntraBarPersist);
```

## Arrays

Fixed-size collections of values.

```powerlanguage
// Declare array
Arrays: Prices[10](0);

// Access elements (1-based indexing)
Prices[1] = Close;
Prices[2] = Close[1];

// Loop through array
For i = 1 to 10 begin
    Prices[i] = Close[i-1];
end;
```

## Variable Scope

- **Local variables** - Declared with `Variables:`, persist across bars
- **IntraBar variables** - Reset each tick within a bar
- **Once statement** - Execute code only on first bar

```powerlanguage
// Initialize once
Once begin
    MyVar = 100;
    Print("Initialized");
end;
```

## Constants

Values that don't change.

```powerlanguage
// Using inputs as constants
Inputs: PI(3.14159);

// Or define in code
Variables: MaxBars(500);
```
