# R
It contains the information &amp; sources of R, which is a programming language for analysis.

## At the beginning

This is the first page.


### `rJava`

```sh
sudo apt-get install default-jre
sudo apt-get install default-jdk
sudo apt-get install r-cran-rjava
sudo R CMD javareconf

```

Then :

```r
install.packages('rJava')
install.packages('RJDBC')

```

In case of Error:

`Installation failed: Peer certificate cannot be authenticated with given CA certificates`

```r
library(httr)
set_config(config(ssl_verifypeer = 0L))
```
