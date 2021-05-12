# histogram
[![license](https://img.shields.io/github/license/DAVFoundation/captain-n3m0.svg?style=flat-square)](https://github.com/stefanhengl/histogram/blob/master/LICENSE)

Compute and display histograms in the terminal. 

Histogram is 100% awk. It takes a stream of numbers and outputs a histogram with user-defined bins.

```bash
$ histogram -v b=0:800:50 < data.csv

```
The output is the following
```bash
  0 -  50: ██████████████████████████████████████████████████ (5104)
 50 - 100: ████████████████ (1643)
100 - 150: ██████████ (1021)
150 - 200: █████▊ (599)
200 - 250: ████ (416)
250 - 300: ███▌ (349)
300 - 350: ██▎ (242)
350 - 400: █▊ (172)
400 - 450: █▎ (127)
450 - 500: ▊ (76)
500 - 550: ▌ (63)
550 - 600: ▌ (50)
600 - 650: ▎ (35)
650 - 700: ▎ (24)
700 - 750: ▎ (16)
```

To print bins from large to small, reverse the range and use a negative step size (here -50).
```bash
$ histogram -v b=300:-1:-50 < data.csv
```

The output is the following:

```bash
250 - 300: ███▌ (349)
200 - 250: ████ (416)
150 - 200: █████▊ (599)
100 - 150: ██████████ (1021)
 50 - 100: ████████████████ (1643)
  0 -  50: ██████████████████████████████████████████████████ (5104)
```

## Usage
```bash

histogram -v b=RANGE [-v scale=SCALE]

RANGE   from:to:step (Python style)  
SCALE   postive integer (DEFAULT=50)
```


## Install
```bash
curl -o /usr/local/bin/histogram https://raw.githubusercontent.com/stefanhengl/histogram/master/histogram
chmod +x /usr/local/bin/histogram
```
