Lab 02 - Plastic waste
================
Insert your name here
Insert date here

## Load packages and data

``` r
library(tidyverse) 
```

``` r
plastic_waste <- read.csv("data/plastic-waste.csv")
```

## Exercises

### Exercise 1

First plots are histograms of the distribution of plastic waste per
capita faceted by continent.

Second plot is the same data as a density plot.

``` r
true_plastic <- plastic_waste %>%
  filter(plastic_waste_per_cap < 3)

ggplot(data = true_plastic, aes(x = plastic_waste_per_cap)) +
  #To make them one graph by color, add in fill = continent after plastice_waste_per_cap
  geom_histogram(binwidth = 0.2) + facet_wrap(~continent) +
  labs(
      x = "Plastic waste per captia by country",
      y = "Amount",
      title = "Plastic Waste"
  )
```

![](lab-02_files/figure-gfm/plastic-waste-continent-1.png)<!-- -->

``` r
ggplot(
  data = true_plastic,
  mapping = aes(
    x = plastic_waste_per_cap,
    color = continent,
    fill = continent
  )
) +
  geom_density(alpha = 0.7) +
  labs(
      x = "Plastic waste per captia",
      y = "amount",
      title = "Density map of Plastic Waste by country"
  )
```

![](lab-02_files/figure-gfm/plastic-waste-continent-2.png)<!-- --> What
I can tell is that they all look pretty similar in terms of plastic
waste per capita. North America has a singular outlier which makes the
graph all look the same. Took out North America outlier, all still
follow similar trend. Africa has higher plastic waste.

### Exercise 2

``` r
ggplot(
  data = true_plastic,
  mapping = aes(
    x = plastic_waste_per_cap,
    color = continent,
    fill = continent
  )
) +
  geom_density(alpha = 0.1)
```

![](lab-02_files/figure-gfm/plastic-waste-density-1.png)<!-- -->

``` r
#plot side by side
ggplot(
  data = true_plastic,
  mapping = aes(
    x = continent,
    y = plastic_waste_per_cap
  )
) +
  geom_boxplot() +
labs(
      x = "Plastic waste per captia",
      y = "amount",
      title = "Side by side of Plastic Waste by country"
  )
```

![](lab-02_files/figure-gfm/plastic-waste-density-2.png)<!-- -->

We use color and fill for aesthetics because they are tied to a variable
(continent). This allows for the color to change with each variable and
show multiple colors. Density is universal and not tied to a variable.

### Exercise 3

They all look like vases. Asia has a really skinny neck.

``` r
ggplot(
  data = true_plastic,
  mapping = aes(
    x = continent,
    y = plastic_waste_per_cap
  )
) +
 geom_violin() +
  labs(
      x = "Plastic waste per captia",
      y = "amount",
      title = "Violin map of Plastic Waste by country"
  )
```

![](lab-02_files/figure-gfm/plastic-waste-violin-1.png)<!-- -->

### Exercise 4

Remove this text, and add your answer for Exercise 4 here.

``` r
# insert code here
```

``` r
# insert code here
```

``` r
# insert code here
```

``` r
# insert code here
```

### Exercise 5

Remove this text, and add your answer for Exercise 5 here.

``` r
# insert code here
```
