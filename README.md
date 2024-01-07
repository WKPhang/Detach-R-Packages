# Detach-R-Packages
Detach all user-loaded R packages

## About
This custom function is used for detaching all user-loaded packages in R. This solution is originated from mjaniec's solution in [https://stackoverflow.com/questions/7505547/detach-all-packages-while-working-in-r] (2012).

## How to
Just create the custom function "detachAllPackages" and run it.

'''
detachAllPackages <- function() {
  basic.packages <- c("package:stats","package:graphics","package:grDevices","package:utils","package:datasets","package:methods","package:base")
  package.list <- search()[ifelse(unlist(gregexpr("package:",search()))==1,TRUE,FALSE)]
  package.list <- setdiff(package.list,basic.packages)
  if (length(package.list)>0)  for (package in package.list) detach(package, character.only=TRUE)
}
detachAllPackages()
'''
