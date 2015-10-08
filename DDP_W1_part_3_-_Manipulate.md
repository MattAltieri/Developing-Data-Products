# Manipulate



## `manipulate`

- Suppose that you want to create a quick interactive graphic
    - You have to do it _now_
    - The intended users also use RStudio
- `manipulate` is a really cool solution that is often all you need to quickly make interactive graphics

---

## Documentation

- `manipulate` is well-documented at the RStudio website here
    - [https://support.rstudio.com/hc/en-us/articles/200551906-Interactive-Plotting-with-Manipulate](https://support.rstudio.com/hc/en-us/articles/200551906-Interactive-Plotting-with-Manipulate)
- From there, try this `library(manipulate); manipulate(plot(1:x), Xx = slider(1,100))`
- You can create a slider, checkbox, or picker (dropdown) and have more than one

---

## Example from the Regression Class


```r
library(manipulate)
library(UsingR)
data(galton)
myHist <- function(mu) {
    hist(galton$child, col="blue", breaks=100)
    lines(c(mu,mu), c(0,150), col="red", lwd=5)
    mse <- mean((galton$child - mu)^2)
    text(63, 150, paste("mu = ", mu))
    text(63, 140, paste("MSE = ", round(mse, 2)))
}
manipulate(myHist(mu), mu=slider(62, 74, step=0.5))
```

---
