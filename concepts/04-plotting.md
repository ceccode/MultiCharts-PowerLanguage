# Plotting and Visualization

## Basic Plotting

```powerlanguage
// Plot a value
Plot1(Close, "Close Price");

// Multiple plots
Plot1(High, "High");
Plot2(Low, "Low");
Plot3(Close, "Close");
```

## Plot Styling

### Set Plot Color

```powerlanguage
Plot1(Close, "Price");
SetPlotColor(1, Blue);

// Conditional coloring
If Close > Open then
    SetPlotColor(1, Green)
else
    SetPlotColor(1, Red);
```

### Set Plot Width

```powerlanguage
SetPlotWidth(1, 2);  // Plot 1, width 2
```

### Plot Styles

```powerlanguage
// Line (default)
SetPlotType(1, ptLine);

// Histogram
SetPlotType(1, ptHistogram);

// Points/Dots
SetPlotType(1, ptPoint);

// Cross
SetPlotType(1, ptCross);
```

## Color Constants

| Color | Constant |
|-------|----------|
| Red | `Red` |
| Green | `Green` |
| Blue | `Blue` |
| Yellow | `Yellow` |
| White | `White` |
| Black | `Black` |
| Cyan | `Cyan` |
| Magenta | `Magenta` |

### Custom Colors (RGB)

```powerlanguage
SetPlotColor(1, RGB(255, 128, 0));  // Orange
```

## Conditional Plotting

```powerlanguage
// Plot only when condition is met
If Close > Average(Close, 20) then
    Plot1(Close, "Above MA");

// NoPlot to skip
If Volume < 100 then
    NoPlot(1);
```

## Text and Arrows

### Text Objects

```powerlanguage
If Close crosses above Average(Close, 20) then
    Text_New(Date, Time, Low, "BUY");
```

### Arrow Objects

```powerlanguage
If Close crosses above Average(Close, 20) then
    ArrowUp(Low - Range * 0.1);

If Close crosses below Average(Close, 20) then
    ArrowDown(High + Range * 0.1);
```

## Horizontal Lines

```powerlanguage
// Plot horizontal line at value
HLine(100, "Support");
```

## Background Coloring

```powerlanguage
// Color the background
If Close > Open then
    SetBarBGColor(RGB(0, 50, 0))  // Dark green
else
    SetBarBGColor(RGB(50, 0, 0)); // Dark red
```
