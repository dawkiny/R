

```R
library(devtools)
library(roxygen2)
```


```R
getwd()
```


'/home/pydemia/workspaces/r'



```R
create('unipyr')
```


    Error: Directory exists and is not empty
    Traceback:


    1. create("unipyr")

    2. stop("Directory exists and is not empty", call. = FALSE)


### edit DESCRIPTION


```R
#` MariaDB Query Function in 'R' Folder with comments
#` Save it "dbConnector.R"

#` DataBase Connector Functions
#'
#' This function allows you to access Databases.
#' @param query, username, password
#' @keywords query, username, password
#' @export
#' @examples
#' mdbQuery()

mdbQuery <- function(query = NULL, username, password){
    
    require(RJDBC)
    
    drv <- JDBC("org.mariadb.jdbc.Driver", "~/jdbcDriver/mariadb-java-client-1.5.6.jar") 
    conn <- dbConnect(drv, "jdbc:mariadb://windows.pydemia.org:3306", username, password)
    res <- dbGetQuery(conn, query)
    print(res)
    return(res)
}
```


```R
setwd('/home/pydemia/workspaces/r/unipyr')
```


```R
getwd()
```


'/home/pydemia/workspaces/r/unipyr'



```R
document()
```

    Updating unipyr documentation
    Loading unipyr


    Writing NAMESPACE
    Writing mdbQuery.Rd



```R
# Compile for Windows

setwd('/home/pydemia/workspaces/r')

build_win('unipyr')
```

    Building windows version of unipyr for R-devel with win-builder.r-project.org.
    
    '/usr/lib/R/bin/R' --no-site-file --no-environ --no-save --no-restore --quiet  \
      CMD build '/home/pydemia/workspaces/r/unipyr' --no-resave-data --no-manual 
    



    Error in curl::curl_fetch_memory(url, handle = h): Upload failed (at start/before it took off)
    Traceback:


    1. build_win("unipyr")

    2. lapply(url, upload_ftp, file = built_path)

    3. FUN(X[[i]], ...)

    4. curl::curl_fetch_memory(url, handle = h)



```R
# submit on CRAN (https://xmpalantir.wu.ac.at/cransubmit/)

```

### Distribute it on github


```R
# just create a repository and upload it
```


```R
devtools::install_github('pydemia/unipyr', force=TRUE)
```

    Downloading GitHub repo pydemia/unipyr@master
    from URL https://api.github.com/repos/pydemia/unipyr/zipball/master
    Installing unipyr
    '/usr/lib/R/bin/R' --no-site-file --no-environ --no-save --no-restore --quiet  \
      CMD INSTALL '/tmp/RtmpVFNrZd/devtools344a1106c5e8/pydemia-unipyr-6ae73d0'  \
      --library='/home/pydemia/R/x86_64-pc-linux-gnu-library/3.4' --install-tests 
    
    Reloading installed unipyr
    
    Attaching package: ‘unipyr’
    
    The following object is masked _by_ ‘.GlobalEnv’:
    
        mdbQuery
    
    The following object is masked from ‘package:unipy’:
    
        mdbQuery
    



```R

```
