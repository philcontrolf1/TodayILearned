# Custom functions to dplyr

[dplyr](https://cran.rstudio.com/web/packages/dplyr/vignettes/introduction.html) is great. However, it's not entirely obvious how to pass a custom function to something like `mutate`.

```r
fn <- function (column1, column2) {
  # Do some clever stuff with column1 and column2
}

vectorizedFn <- Vectorize(r, c("column1", "column2"))

df <- df %>% mutate(Column3 = vectorizedFn(Column1, Column2))
```

[Source](http://stackoverflow.com/a/21818651/525010)
