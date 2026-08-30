# IUCN Red List color scales

ggplot2 color scales using the colors for the IUCN Red List threat
categories, as documented in [this
chart](https://nc.iucnredlist.org/redlist/resources/files/1646067752-FINAL_IUCN_Red_List_colour_chart.pdf).

## Usage

``` r
scale_color_iucn(...)

scale_fill_iucn(...)

scale_discrete_iucn(aesthetics, ...)
```

## Arguments

- ...:

  Arguments passed on to
  [ggplot2::discrete_scale](https://ggplot2.tidyverse.org/reference/discrete_scale.html)
  (except for `na.value` which is already set according to the IUCN
  standard of `#C1B5A5`)

- aesthetics:

  Character string or vector of character strings listing the name(s) of
  the aesthetic(s) that this scale works with. This can be useful, for
  example, to apply color settings to the `color` and `fill` aesthetics
  at the same time, via `aesthetics = c("color", "fill")`.

## Examples

``` r
library(ggplot2)
categories <- c("NE", "DD", "LC", "NT", "VU", "EN", "CR", "RE", "EW", "EX")
df <- data.frame(
  x = runif(1000, 0, 10), y = runif(1000, 0, 10),
  color = sample(categories, 1000, TRUE), shape = 21
)
ggplot(df) +
  geom_point(aes(x = x, y = y, fill = color), shape = 21) +
  scale_fill_iucn(name = "IUCN Category") +
  theme_classic()
```
