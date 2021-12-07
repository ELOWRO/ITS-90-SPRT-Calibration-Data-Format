🌡 ITS-90 SPRT Calibration Data Format
======================================

## ITS-90 Compact v1.0

This format is dedicated for QR Codes and URLs but can be used for any purpose.

File extension: `.qt90`

### Formats:

#### Variant A: 

```
qt90://[Sub-Range]/[Fixed point]_[Fixed point]/[Coefficient]_[Coefficient]
```

#### Variant B: 

```
qt90://[Sub-Range]/[Fixed point]_[Fixed point]
```

#### Variant C: 

```
qt90://[Sub-Range]/[Triple point of Water]/[Coefficient]_[Coefficient]
```


#### Sub-Range:

Integer identifier.

More at: Appendix A: ITS-90 Sub-ranges


#### Fixed points:

```
[Temperature(Kelvin)~Uncertainty(Kelvin)]K[Resistance(Ohms)~Uncertainty(Ohms)]
```

Notice how `±` is represented by `~`.

One can use one of the two notations:

- Temperatures

```
273.16~0.009K100.017~0.006
```

- Shorthand letters

```
W~0.009K100.0170~0.006
```

Notice how temperature is now replaced by one letter (for list of letters see Appendix B):


##### Uncertainty can be ommited for resistance:

```
273.16~0.009K100.017
```

#### Coefficients:

Format: `[A]_[B]_[C]`

Example:

```
-2.0786366E-04_-8.8309895E-05
```

### Full example

Sub-Range 8: 0.01 °C to 419.527 °C (Water-Zinc)

Calibration points:

- Water: 273.16 ± 0.009K 
  - Resistance: 100.0135 ± 0.006Ω
- Tin:  505.078 ± 0.012K 
  - Resistance: 188.9427 ± 0.006Ω
- Zinc: 692.677 ± 0.096K 
  - Resistance: 256.6981 ± 0.006Ω

Coefficients:

- a8: -2.0786366E-04
- b8: -8.8309895E-05

#### Calibration data:

##### Variant A:

- Temperatures

```
8/273.16~0.009K100.0135~0.006_505.078~0.012K188.9427~0.006_692.677~0.096K256.6981~0.006/-2.0786366E-04_-8.8309895E-05
```

- Shorthand letters: 

```
8/W~0.009K100.0135~0.006_T~0.012K188.9427~0.006_Z~0.096K256.6981~0.006/-2.0786366E-04_-8.8309895E-05
```

##### Variant B:

```
8/W~0.009K100.0135~0.006_T~0.012K188.9427~0.006_Z~0.096K256.6981~0.006
```

##### Variant C:

```
8/W~0.009K100.0135/-2.0786366E-04_-8.8309895E-05
```

#### Full payload:

```
qt90://8/273.16~0.009K100.0135~0.006_505.078+0.012K188.9427~0.006_692,677~0.096K256.6981~0.006/-2.0786366E-04_-8.8309895E-05
```

As QR code:

![frame-2](https://user-images.githubusercontent.com/3382607/143776121-851bdc9b-fe55-4568-84d2-ed5c8e63789c.png)

## Appendix A: ITS-90 Sub-ranges

### Sub-Range 1:

**-259.3467 °C to +0.01 °C**

TP of Hydrogen to TP of Water


### Sub-Range 2:

**-248.5939 °C to +0.01 °C**

TP of Neon to TP of Water


### Sub-Range 3:

**-218.7916 °C to +0.01 °C**

TP of Oxygen to TP of Water


### Sub-Range 4:

**-189.3442 °C to +0.01 °C**

TP of Argon to TP of Water


### Sub-Range 5:

**-38.8344 °C to +29.7646 °C**

TP of Mercury to MP of Gallium


### Sub-Range 6:

**+0.01 °C to +961.78 °C**

TP of Water to FP of Silver


### Sub-Range 7:

**+0.01 °C to +660.323 °C**

TP of Water to FP of Aluminum


### Sub-Range 8:

**+0.01 °C to +419.527 °C**

TP of Water to FP of Zinc


### Sub-Range 9:

**+0.01 °C to +231.928 °C**

TP of Water to FP of Tin


### Sub-Range 10:

**+0.01 °C to +156.5985 °C**

TP of Water to FP of Indium


### Sub-Range 11:

**+0.01 °C to +29.7646 °C**

TP of Water to MP of Gallium

## Appendix B: ITS-90 Fixed Points shorthand letters

- `L` - Freezing Point of Aluminum
- `R` - Triple Point of Argon
- `G` - Melting Point of Gallium
- `H` - Triple Point of Helium
- `I` - Freezing Point of Indium
- `M` - Freezing Point of Mercury
- `N` - Triple Point of Neon
- `O` - Triple Point of Oxygen
- `S` - Freezing Point of Silver
- `T` - Freezing Point of Tin
- `W` - Triple Point of Water
- `Z` - Freezing Point of Zinc

