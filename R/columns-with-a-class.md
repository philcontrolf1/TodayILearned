# Get all columns with a specific class from a data frame

When you're doing ETL, it's sometimes useful to just pick out all the columns from
a data frame which have a specific class.

```r
getColumnsWithType <- function(df, clazz) {
  names(Filter(function(c) identical(c, clazz), lapply(df, class)))
}
```

Usage is fairly simple: `getColumnsWithType(df, "logical")` will give you the names of all the
logical columns in `df`. If you actually want to get the values of the columns as well,
`df %>% select(one_of(getColumnsWithType(df, "logical")))`.

The only catch is for date/time columns, where you'll need to do
`getColumnsWithType(df, c("POSIXct", "POSIXt"))`.
