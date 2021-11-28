🌡 ITS-90 SPRT Calibration Data Format
======================================

## ITS-90 Compact v1.0

This format is dedicated for QR Codes and URLs but can be used for any purpose.

File extension: `.qt90`

### Format:

```
qt90://[Sub-Range]/[Fixed point]_[Fixed point]/[Coefficient]_[Coefficient]
```

#### Fixed points:

```
[Temperature(Kelvin)~Uncertainty(Kelvin)]K[Resistance(Ohms)~Uncertainty(Ohms)]
```

Example:

```
273.16~0.009K100.017~0.006
```

#### Coefficients:

Format: `[A]_[B]_[C]`

Example:

```
-2.0786366E-04_-8.8309895E-05
```

### Full example

Sub-Range 8: 0.01 °C to 419.527 °C (Water-Zinc)

Fixed points:

- Water: 273.16±0.009K Resistance: 100.0135±0.006Ω
- Tin:  505.078±0.012K Resistance: 188.9427±0.006Ω
- Zinc: 692,677±0.096K Resistance: 256.6981±0.006Ω

Coefficients:

- a8: -2.0786366E-04
- b8: -8.8309895E-05



#### Put together:

```
8/273.16~0.009K100.0135~0.006_505.078+0.012K188.9427~0.006_692,677~0.096K256.6981~0.006/-2.0786366E-04_-8.8309895E-05
```

Notice how `±` is represented by `~`!

#### Full payload:

```
qt90://8/273.16~0.009K100.0135~0.006_505.078+0.012K188.9427~0.006_692,677~0.096K256.6981~0.006/-2.0786366E-04_-8.8309895E-05
```

As QR code:

![frame-2](https://user-images.githubusercontent.com/3382607/143776121-851bdc9b-fe55-4568-84d2-ed5c8e63789c.png)

