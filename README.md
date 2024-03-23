# Assign11

tukey_multiple <- function(x) {
+   outliers <- array(TRUE,dim=dim(x))
+   for (j in 1:ncol(x))
+   {
+    outliers[,j] <- outliers[,j] && tukey.outlier(x[,j])
+   }
+   outliers.vec <-vector(length=nrow(x))
+   for (i in 1:nrow(x))
+   {
+    outliers.vec[i] <- all(outliers[i,])
+   }
+   return(outliers.vec)
+   }


> traceback()
No traceback available 


> debug(tukey_multiple)
> tukey_multiple(x)

debugging in: tukey_multiple(x)
debug at #1: {
    outliers <- array(TRUE, dim = dim(x))
    for (j in 1:ncol(x)) {
        outliers[, j] <- outliers[, j] && tukey.outlier(x[, j])
    }
    outliers.vec <- vector(length = nrow(x))
    for (i in 1:nrow(x)) {
        outliers.vec[i] <- all(outliers[i, ])
    }
    return(outliers.vec)
}
Browse[2]> n
debug at #2: outliers <- array(TRUE, dim = dim(x))
Browse[2]> n
Error: object 'x' not found

> z <- matrix(rnorm(100), ncol=5)

> tukey_multiple(x)
debugging in: tukey_multiple(x)
debug at #1: {
    outliers <- array(TRUE, dim = dim(x))
    for (j in 1:ncol(x)) {
        outliers[, j] <- outliers[, j] && tukey.outlier(x[, j])
    }
    outliers.vec <- vector(length = nrow(x))
    for (i in 1:nrow(x)) {
        outliers.vec[i] <- all(outliers[i, ])
    }
    return(outliers.vec)
}
Browse[2]> n
debug at #2: outliers <- array(TRUE, dim = dim(x))
Browse[2]> n
debug at #3: for (j in 1:ncol(x)) {
    outliers[, j] <- outliers[, j] && tukey.outlier(x[, j])
}
Browse[2]> n
debug at #5: outliers[, j] <- outliers[, j] && tukey.outlier(x[, j])
Browse[2]> n

Error in tukey.outlier(x[, j]) : could not find function "tukey.outlier"
  
>  tukey_multiple <- function(x) {
+   outliers <- array(TRUE,dim=dim(x))
+   for (j in 1:ncol(x))
+   {
+    outliers[,j] <- outliers[,j] & tukey.outlier[,j]
+   }
+   outliers.vec <-vector(length=nrow(x))
+   for (i in 1:nrow(x))
+   {
+    outliers.vec[i] <- all(outliers[i,])
+   }
+   return(outliers.vec)
+   }

> debug(tukey_multiple)
> 
> tukey_multiple(x)

debugging in: tukey_multiple(x)
debug at #1: {
    outliers <- array(TRUE, dim = dim(x))
    for (j in 1:ncol(x)) {
        outliers[, j] <- outliers[, j] & tukey.outlier[, j]
    }
    outliers.vec <- vector(length = nrow(x))
    for (i in 1:nrow(x)) {
        outliers.vec[i] <- all(outliers[i, ])
    }
    return(outliers.vec)
}

Browse[2]> n
debug at #2: outliers <- array(TRUE, dim = dim(x))
Browse[2]> n
debug at #3: for (j in 1:ncol(x)) {
    outliers[, j] <- outliers[, j] & tukey.outlier[, j]
}
Browse[2]> n
debug at #5: outliers[, j] <- outliers[, j] & tukey.outlier[, j]
Browse[2]> n
debug at #5: outliers[, j] <- outliers[, j] & tukey.outlier[, j]
Browse[2]> n
debug at #5: outliers[, j] <- outliers[, j] & tukey.outlier[, j]
Browse[2]> n
debug at #5: outliers[, j] <- outliers[, j] & tukey.outlier[, j]
Browse[2]> n
debug at #5: outliers[, j] <- outliers[, j] & tukey.outlier[, j]
Browse[2]> n
debug at #7: outliers.vec <- vector(length = nrow(x))
Browse[2]> n
debug at #8: for (i in 1:nrow(x)) {
    outliers.vec[i] <- all(outliers[i, ])
}
Browse[2]> n
debug at #10: outliers.vec[i] <- all(outliers[i, ])
Browse[2]> n
debug at #10: outliers.vec[i] <- all(outliers[i, ])
Browse[2]> n
debug at #10: outliers.vec[i] <- all(outliers[i, ])
Browse[2]> n
debug at #10: outliers.vec[i] <- all(outliers[i, ])
Browse[2]> Q
