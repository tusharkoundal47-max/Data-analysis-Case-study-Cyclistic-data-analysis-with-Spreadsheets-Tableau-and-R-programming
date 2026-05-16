# Cyclistic-data-Project-Spreadsheets-and-R-programming-
Case study 1: How does a bike-share navigate speedy success? This is my practice project, that is part of the Google Data Analytics Professional Certificate helps convey my approach to analysing data.

Case Study cyclistic data

# Introduction
This case study have been done on the lines of Google Data analytics program under capstone project. The data used in this case study is sourced from Motivate International Inc under this license agreement.
 <https://divvybikes.com/data-license-agreement>
 #The steps involved my the data analysis process are: 
1 Ask
2 Prepare
3 Process
4 Analyse
5 Share
6 Act.

The following notebook conveys my approach to analysing data for the case study which  explores the business problem of a hypothetical bike-sharing service named Cyclistic.

#Scenario
         
You are a junior data analyst working on the marketing analyst team at Cyclistic, a bike-share company in Chicago. The director of marketing believes the company’s future success depends on maximizing the number of annual memberships. Therefore, your team wants to understand how casual riders and annual members use Cyclistic bikes differently. From these insights, your team will design a new marketing strategy to convert casual riders into annual members. But first, Cyclistic executives must approve your recommendations, so they must be backed up with compelling data insights and professional data visualizations.

## Background
    
 Cyclistic has grown into a fleet of 5,824 bicycles that are geo-tracked and locked into a network of 692 stations across Chicago over the years since 2016. The bikes can be unlocked from one station and returned to any other station in the system anytime.

```R


```
#Ask (1st phase)

###Three questions will guide the problem statement:
1. How do annual members and casual riders use Cyclistic bikes differently?
2. Why would casual riders buy Cyclistic annual memberships?
3. How can Cyclistic use digital media to influence casual riders to become members?

### Approaching this phase:
*Business problem statement includes viewing the two types of subscribers i.e. Annual members and Casual riders and then analysing their usage patterns.
*Reason to why subscribers opt for annual memberships and what can trigger or accelerate this behaviour.
*How can we tweak the marketing strategy to make casual riders convert into annual subscribers.

After identification of Business tasks and considering the requirements of key stakeholders, gathering prerequisites for the task comes next. 


```r



```
#Prepare (2nd phase)

###These questions will guide the prepare step:
1. Status of data organisation and its location.
2. Are there any issues related to bias or credibility and data licencing?
3. What are problems with gathered data?

### Approaching this phase:
*Downloading the data and giving proper naming conventions to keep data organised and storing it appropriately.
*Taking a gist of what the data contains and how is it relevant for our problem statement.
*Sorting, filtering and combining the data.

The data used in this case study is publicly available with sharing license <https://divvybikes.com/data-license-agreement> , for the purpose of this study I have gathered data for past 12 months (May 2025 to April 2026) in 'csv' file format from this repository link <https://divvy-tripdata.s3.amazonaws.com/index.html>.

Then the data is first saved in appropriate folders with proper naming conventions and a backup of raw data is saved for future reference and other copy was utilized for processing purposes.

Processing involved deletion of redundant columns using spreadsheet program and then adding a column specifying "ride duration" by calculating difference between "Ride start at" and "Ride end at" times. The files were gathered in a single workbook and saved for further processing in Posit Cloud workspace where I used R programming language for further analysis.

###Installing and loading tidyverse packages in R posit cloud

```R
#Install and load tidyverse packages
install.packages("tidyverse")
```
Installing package into ‘/cloud/lib/x86_64-pc-linux-gnu-library/4.6’
(as ‘lib’ is unspecified)
also installing the dependencies ‘fastmap’, ‘sys’, ‘bit’, ‘ps’, ‘sass’, ‘digest’, ‘cachem’, ‘farver’, ‘labeling’, ‘RColorBrewer’, ‘viridisLite’, ‘rappdirs’, ‘rematch’, ‘askpass’, ‘base64enc’, ‘bit64’, ‘prettyunits’, ‘processx’, ‘evaluate’, ‘highr’, ‘xfun’, ‘yaml’, ‘bslib’, ‘fontawesome’, ‘htmltools��, ‘jquerylib’, ‘tinytex’, ‘backports’, ‘generics’, ‘glue’, ‘lifecycle’, ‘memoise’, ‘blob’, ‘DBI’, ‘R6’, ‘tidyselect’, ‘vctrs’, ‘withr’, ‘data.table’, ‘gtable’, ‘isoband’, ‘S7’, ‘scales’, ‘gargle’, ‘uuid’, ‘cellranger’, ‘curl’, ‘ids’, ‘rematch2’, ‘cpp11’, ‘pkgconfig’, ‘mime’, ‘openssl’, ‘timechange’, ‘utf8’, ‘systemfonts’, ‘textshaping’, ‘clipr’, ‘crayon’, ‘vroom’, ‘tzdb’, ‘progress’, ‘callr’, ‘fs’, ‘knitr’, ‘rmarkdown’, ‘selectr’, ‘stringi’, ‘broom’, ‘conflicted’, ‘cli’, ‘dbplyr’, ‘dplyr’, ‘dtplyr’, ‘forcats’, ‘ggplot2’, ‘googledrive’, ‘googlesheets4’, ‘haven’, ‘hms’, ‘httr’, ‘jsonlite’, ‘lubridate’, ‘magrittr’, ‘modelr’, ‘pillar’, ‘purrr’, ‘ragg’, ‘readr’, ‘readxl’, ‘reprex’, ‘rlang’, ‘rstudioapi’, ‘rvest’, ‘stringr’, ‘tibble’, ‘tidyr’, ‘xml2’
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/fastmap_1.2.0.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/sys_3.4.3.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/bit_4.6.0.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/ps_1.9.3.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/sass_0.4.10.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/digest_0.6.39.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/cachem_1.1.0.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/farver_2.1.2.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/labeling_0.4.3.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/RColorBrewer_1.1-3.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/viridisLite_0.4.3.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/rappdirs_0.3.4.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/rematch_2.0.0.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/askpass_1.2.1.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/base64enc_0.1-6.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/bit64_4.8.0.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/prettyunits_1.2.0.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/processx_3.9.0.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/evaluate_1.0.5.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/highr_0.12.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/xfun_0.57.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/yaml_2.3.12.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/bslib_0.10.0.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/fontawesome_0.5.3.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/htmltools_0.5.9.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/jquerylib_0.1.4.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/tinytex_0.59.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/backports_1.5.1.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/generics_0.1.4.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/glue_1.8.1.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/lifecycle_1.0.5.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/memoise_2.0.1.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/blob_1.3.0.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/DBI_1.3.0.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/R6_2.6.1.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/tidyselect_1.2.1.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/vctrs_0.7.3.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/withr_3.0.2.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/data.table_1.18.4.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/gtable_0.3.6.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/isoband_0.3.0.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/S7_0.2.2.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/scales_1.4.0.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/gargle_1.6.1.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/uuid_1.2-2.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/cellranger_1.1.0.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/curl_7.1.0.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/ids_1.0.1.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/rematch2_2.1.2.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/cpp11_0.5.5.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/pkgconfig_2.0.3.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/mime_0.13.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/openssl_2.4.0.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/timechange_0.4.0.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/utf8_1.2.6.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/systemfonts_1.3.2.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/textshaping_1.0.5.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/clipr_0.8.0.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/crayon_1.5.3.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/vroom_1.7.1.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/tzdb_0.5.0.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/progress_1.2.3.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/callr_3.7.6.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/fs_2.1.0.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/knitr_1.51.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/rmarkdown_2.31.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/selectr_0.5-1.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/stringi_1.8.7.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/broom_1.0.12.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/conflicted_1.2.0.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/cli_3.6.6.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/dbplyr_2.5.2.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/dplyr_1.2.1.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/dtplyr_1.3.3.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/forcats_1.0.1.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/ggplot2_4.0.3.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/googledrive_2.1.2.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/googlesheets4_1.1.2.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/haven_2.5.5.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/hms_1.1.4.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/httr_1.4.8.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/jsonlite_2.0.0.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/lubridate_1.9.5.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/magrittr_2.0.5.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/modelr_0.1.11.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/pillar_1.11.1.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/purrr_1.2.2.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/ragg_1.5.2.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/readr_2.2.0.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/readxl_1.4.5.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/reprex_2.1.1.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/rlang_1.2.0.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/rstudioapi_0.18.0.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/rvest_1.0.5.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/stringr_1.6.0.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/tibble_3.3.1.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/tidyr_1.3.2.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/xml2_1.5.2.tar.gz'
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/tidyverse_2.0.0.tar.gz'
* installing *binary* package ‘fastmap’ ...
* package ‘fastmap’ successfully unpacked and SHA256 sums checked
* DONE (fastmap)
* installing *binary* package ‘sys’ ...
* package ‘sys’ successfully unpacked and SHA256 sums checked
* DONE (sys)
* installing *binary* package ‘bit’ ...
* package ‘bit’ successfully unpacked and SHA256 sums checked
* DONE (bit)
* installing *binary* package ‘ps’ ...
* package ‘ps’ successfully unpacked and SHA256 sums checked
* DONE (ps)
* installing *binary* package ‘digest’ ...
* package ‘digest’ successfully unpacked and SHA256 sums checked
* DONE (digest)
* installing *binary* package ‘farver’ ...
* package ‘farver’ successfully unpacked and SHA256 sums checked
* DONE (farver)
* installing *binary* package ‘labeling’ ...
* package ‘labeling’ successfully unpacked and SHA256 sums checked
* DONE (labeling)
* installing *binary* package ‘RColorBrewer’ ...
* package ‘RColorBrewer’ successfully unpacked and SHA256 sums checked
* DONE (RColorBrewer)
* installing *binary* package ‘viridisLite’ ...
* package ‘viridisLite’ successfully unpacked and SHA256 sums checked
* DONE (viridisLite)
* installing *binary* package ‘rappdirs’ ...
* package ‘rappdirs’ successfully unpacked and SHA256 sums checked
* DONE (rappdirs)
* installing *binary* package ‘rematch’ ...
* package ‘rematch’ successfully unpacked and SHA256 sums checked
* DONE (rematch)
* installing *binary* package ‘base64enc’ ...
* package ‘base64enc’ successfully unpacked and SHA256 sums checked
* DONE (base64enc)
* installing *binary* package ‘prettyunits’ ...
* package ‘prettyunits’ successfully unpacked and SHA256 sums checked
* DONE (prettyunits)
* installing *binary* package ‘evaluate’ ...
* package ‘evaluate’ successfully unpacked and SHA256 sums checked
* DONE (evaluate)
* installing *binary* package ‘xfun’ ...
* package ‘xfun’ successfully unpacked and SHA256 sums checked
* DONE (xfun)
* installing *binary* package ‘yaml’ ...
* package ‘yaml’ successfully unpacked and SHA256 sums checked
* DONE (yaml)
* installing *binary* package ‘backports’ ...
* package ‘backports’ successfully unpacked and SHA256 sums checked
* DONE (backports)
* installing *binary* package ‘generics’ ...
* package ‘generics’ successfully unpacked and SHA256 sums checked
* DONE (generics)
* installing *binary* package ‘glue’ ...
* package ‘glue’ successfully unpacked and SHA256 sums checked
* DONE (glue)
* installing *binary* package ‘DBI’ ...
* package ‘DBI’ successfully unpacked and SHA256 sums checked
* DONE (DBI)
* installing *binary* package ‘R6’ ...
* package ‘R6’ successfully unpacked and SHA256 sums checked
* DONE (R6)
* installing *binary* package ‘withr’ ...
* package ‘withr’ successfully unpacked and SHA256 sums checked
* DONE (withr)
* installing *binary* package ‘data.table’ ...
* package ‘data.table’ successfully unpacked and SHA256 sums checked
* DONE (data.table)
* installing *binary* package ‘S7’ ...
* package ‘S7’ successfully unpacked and SHA256 sums checked
* DONE (S7)
* installing *binary* package ‘uuid’ ...
* package ‘uuid’ successfully unpacked and SHA256 sums checked
* DONE (uuid)
* installing *binary* package ‘curl’ ...
* package ‘curl’ successfully unpacked and SHA256 sums checked
* DONE (curl)
* installing *binary* package ‘cpp11’ ...
* package ‘cpp11’ successfully unpacked and SHA256 sums checked
* DONE (cpp11)
* installing *binary* package ‘pkgconfig’ ...
* package ‘pkgconfig’ successfully unpacked and SHA256 sums checked
* DONE (pkgconfig)
* installing *binary* package ‘mime’ ...
* package ‘mime’ successfully unpacked and SHA256 sums checked
* DONE (mime)
* installing *binary* package ‘utf8’ ...
* package ‘utf8’ successfully unpacked and SHA256 sums checked
* DONE (utf8)
* installing *binary* package ‘clipr’ ...
* package ‘clipr’ successfully unpacked and SHA256 sums checked
* DONE (clipr)
* installing *binary* package ‘crayon’ ...
* package ‘crayon’ successfully unpacked and SHA256 sums checked
* DONE (crayon)
* installing *binary* package ‘fs’ ...
* package ‘fs’ successfully unpacked and SHA256 sums checked
* DONE (fs)
* installing *binary* package ‘stringi’ ...
* package ‘stringi’ successfully unpacked and SHA256 sums checked
* DONE (stringi)
* installing *binary* package ‘cli’ ...
* package ‘cli’ successfully unpacked and SHA256 sums checked
* DONE (cli)
* installing *binary* package ‘jsonlite’ ...
* package ‘jsonlite’ successfully unpacked and SHA256 sums checked
* DONE (jsonlite)
* installing *binary* package ‘magrittr’ ...
* package ‘magrittr’ successfully unpacked and SHA256 sums checked
* DONE (magrittr)
* installing *binary* package ‘rlang’ ...
* package ‘rlang’ successfully unpacked and SHA256 sums checked
* DONE (rlang)
* installing *binary* package ‘rstudioapi’ ...
* package ‘rstudioapi’ successfully unpacked and SHA256 sums checked
* DONE (rstudioapi)
* installing *binary* package ‘cachem’ ...
* package ‘cachem’ successfully unpacked and SHA256 sums checked
* DONE (cachem)
* installing *binary* package ‘askpass’ ...
* package ‘askpass’ successfully unpacked and SHA256 sums checked
* DONE (askpass)
* installing *binary* package ‘bit64’ ...
* package ‘bit64’ successfully unpacked and SHA256 sums checked
* DONE (bit64)
* installing *binary* package ‘processx’ ...
* package ‘processx’ successfully unpacked and SHA256 sums checked
* DONE (processx)
* installing *binary* package ‘highr’ ...
* package ‘highr’ successfully unpacked and SHA256 sums checked
* DONE (highr)
* installing *binary* package ‘htmltools’ ...
* package ‘htmltools’ successfully unpacked and SHA256 sums checked
* DONE (htmltools)
* installing *binary* package ‘tinytex’ ...
* package ‘tinytex’ successfully unpacked and SHA256 sums checked
* DONE (tinytex)
* installing *binary* package ‘lifecycle’ ...
* package ‘lifecycle’ successfully unpacked and SHA256 sums checked
* DONE (lifecycle)
* installing *binary* package ‘isoband’ ...
* package ‘isoband’ successfully unpacked and SHA256 sums checked
* DONE (isoband)
* installing *binary* package ‘timechange’ ...
* package ‘timechange’ successfully unpacked and SHA256 sums checked
* DONE (timechange)
* installing *binary* package ‘tzdb’ ...
* package ‘tzdb’ successfully unpacked and SHA256 sums checked
* DONE (tzdb)
* installing *binary* package ‘xml2’ ...
* package ‘xml2’ successfully unpacked and SHA256 sums checked
* DONE (xml2)
* installing *binary* package ‘sass’ ...
* package ‘sass’ successfully unpacked and SHA256 sums checked
* DONE (sass)
* installing *binary* package ‘fontawesome’ ...
* package ‘fontawesome’ successfully unpacked and SHA256 sums checked
* DONE (fontawesome)
* installing *binary* package ‘jquerylib’ ...
* package ‘jquerylib’ successfully unpacked and SHA256 sums checked
* DONE (jquerylib)
* installing *binary* package ‘memoise’ ...
* package ‘memoise’ successfully unpacked and SHA256 sums checked
* DONE (memoise)
* installing *binary* package ‘vctrs’ ...
* package ‘vctrs’ successfully unpacked and SHA256 sums checked
* DONE (vctrs)
* installing *binary* package ‘gtable’ ...
* package ‘gtable’ successfully unpacked and SHA256 sums checked
* DONE (gtable)
* installing *binary* package ‘scales’ ...
* package ‘scales’ successfully unpacked and SHA256 sums checked
* DONE (scales)
* installing *binary* package ‘openssl’ ...
* package ‘openssl’ successfully unpacked and SHA256 sums checked
* DONE (openssl)
* installing *binary* package ‘systemfonts’ ...
* package ‘systemfonts’ successfully unpacked and SHA256 sums checked
* DONE (systemfonts)
* installing *binary* package ‘callr’ ...
* package ‘callr’ successfully unpacked and SHA256 sums checked
* DONE (callr)
* installing *binary* package ‘knitr’ ...
* package ‘knitr’ successfully unpacked and SHA256 sums checked
* DONE (knitr)
* installing *binary* package ‘lubridate’ ...
* package ‘lubridate’ successfully unpacked and SHA256 sums checked
* DONE (lubridate)
* installing *binary* package ‘bslib’ ...
* package ‘bslib’ successfully unpacked and SHA256 sums checked
* DONE (bslib)
* installing *binary* package ‘blob’ ...
* package ‘blob’ successfully unpacked and SHA256 sums checked
* DONE (blob)
* installing *binary* package ‘tidyselect’ ...
* package ‘tidyselect’ successfully unpacked and SHA256 sums checked
* DONE (tidyselect)
* installing *binary* package ‘ids’ ...
* package ‘ids’ successfully unpacked and SHA256 sums checked
* DONE (ids)
* installing *binary* package ‘textshaping’ ...
* package ‘textshaping’ successfully unpacked and SHA256 sums checked
* DONE (textshaping)
* installing *binary* package ‘conflicted’ ...
* package ‘conflicted��� successfully unpacked and SHA256 sums checked
* DONE (conflicted)
* installing *binary* package ‘ggplot2’ ...
* package ‘ggplot2’ successfully unpacked and SHA256 sums checked
* DONE (ggplot2)
* installing *binary* package ‘hms’ ...
* package ‘hms’ successfully unpacked and SHA256 sums checked
* DONE (hms)
* installing *binary* package ‘httr’ ...
* package ‘httr’ successfully unpacked and SHA256 sums checked
* DONE (httr)
* installing *binary* package ‘pillar’ ...
* package ��pillar’ successfully unpacked and SHA256 sums checked
* DONE (pillar)
* installing *binary* package ‘purrr’ ...
* package ‘purrr’ successfully unpacked and SHA256 sums checked
* DONE (purrr)
* installing *binary* package ‘stringr’ ...
* package ‘stringr’ successfully unpacked and SHA256 sums checked
* DONE (stringr)
* installing *binary* package ‘gargle’ ...
* package ‘gargle’ successfully unpacked and SHA256 sums checked
* DONE (gargle)
* installing *binary* package ‘progress�� ...
* package ‘progress’ successfully unpacked and SHA256 sums checked
* DONE (progress)
* installing *binary* package ‘rmarkdown’ ...
* package ‘rmarkdown’ successfully unpacked and SHA256 sums checked
* DONE (rmarkdown)
* installing *binary* package ‘selectr’ ...
* package ‘selectr’ successfully unpacked and SHA256 sums checked
* DONE (selectr)
* installing *binary* package ‘ragg’ ...
* package ‘ragg’ successfully unpacked and SHA256 sums checked
* DONE (ragg)
* installing *binary* package ‘tibble’ ...
* package ‘tibble’ successfully unpacked and SHA256 sums checked
* DONE (tibble)
* installing *binary* package ‘cellranger’ ...
* package ‘cellranger’ successfully unpacked and SHA256 sums checked
* DONE (cellranger)
* installing *binary* package ‘rematch2’ ...
* package ‘rematch2’ successfully unpacked and SHA256 sums checked
* DONE (rematch2)
* installing *binary* package ‘vroom’ ...
* package ‘vroom’ successfully unpacked and SHA256 sums checked
* DONE (vroom)
* installing *binary* package ‘dplyr’ ...
* package ‘dplyr’ successfully unpacked and SHA256 sums checked
* DONE (dplyr)
* installing *binary* package ‘forcats’ ...
* package ‘forcats’ successfully unpacked and SHA256 sums checked
* DONE (forcats)
* installing *binary* package ‘googledrive’ ...
* package ‘googledrive’ successfully unpacked and SHA256 sums checked
* DONE (googledrive)
* installing *binary* package ‘reprex’ ...
* package ‘reprex’ successfully unpacked and SHA256 sums checked
* DONE (reprex)
* installing *binary* package ‘rvest’ ...
* package ‘rvest’ successfully unpacked and SHA256 sums checked
* DONE (rvest)
* installing *binary* package ‘dtplyr’ ...
* package ‘dtplyr’ successfully unpacked and SHA256 sums checked
* DONE (dtplyr)
* installing *binary* package ‘googlesheets4’ ...
* package ‘googlesheets4’ successfully unpacked and SHA256 sums checked
* DONE (googlesheets4)
* installing *binary* package ‘readr’ ...
* package ‘readr’ successfully unpacked and SHA256 sums checked
* DONE (readr)
* installing *binary* package ‘readxl’ ...
* package ‘readxl’ successfully unpacked and SHA256 sums checked
* DONE (readxl)
* installing *binary* package ‘tidyr’ ...
* package ‘tidyr’ successfully unpacked and SHA256 sums checked
* DONE (tidyr)
* installing *binary* package ‘broom’ ...
* package ‘broom’ successfully unpacked and SHA256 sums checked
* DONE (broom)
* installing *binary* package ‘dbplyr’ ...
* package ‘dbplyr’ successfully unpacked and SHA256 sums checked
* DONE (dbplyr)
* installing *binary* package ‘haven’ ...
* package ‘haven’ successfully unpacked and SHA256 sums checked
* DONE (haven)
* installing *binary* package ‘modelr’ ...
* package ‘modelr’ successfully unpacked and SHA256 sums checked
* DONE (modelr)
* installing *binary* package ‘tidyverse’ ...
* package ‘tidyverse’ successfully unpacked and SHA256 sums checked
* DONE (tidyverse)
The downloaded source packages are in
	‘/tmp/RtmpQoamUH/downloaded_packages’









####load the core tidyverse packages
```R
library("tidyverse")
```
The downloaded source packages are in
	‘/tmp/RtmpQoamUH/downloaded_packages’
> library('tidyverse')
── Attaching core tidyverse packages ────────────────────────── tidyverse 2.0.0 ──
✔ dplyr     1.2.1     ✔ readr     2.2.0
✔ forcats   1.0.1     ✔ stringr   1.6.0
✔ ggplot2   4.0.3     ✔ tibble    3.3.1
✔ lubridate 1.9.5     ✔ tidyr     1.3.2
✔ purrr     1.2.2     
── Conflicts ──────────────────────────────────────────── tidyverse_conflicts() ──
✖ dplyr::filter() masks stats::filter()
✖ dplyr::lag()    masks stats::lag()
ℹ Use the conflicted package to force all conflicts to become errors








####importing dataset
####uploaded dataset to posit cloud as csv file then imported in the project
```R
cydata525 <- read.csv("")
cydata625 <- read.csv("")
cydata725 <- read.csv("")
cydata825 <- read.csv("")
cydata925 <- read.csv("")
cydata1025 <- read.csv("")
cydata1125 <- read.csv("")
cydata1225 <- read.csv("")
cydata126 <- read.csv("")
cydata226 <- read.csv("")
cydata326 <- read.csv("")
cydata426 <- read.csv("")

# here i have named the cyclistic data files as cydata[myy] ie from May 2025 to April 2026
```


I also used the compiled dataset in posit R the step involved is as follows:

```R
Cyclisticdata <- read.csv("/cloud/project/divvy-tripdata6months.csv")
```







####view the head (viewing the first 6 rows helps in verifying weather the data has been loaded correctly)
```R
head(Cyclisticdata)
```

>           ride_id rideable_type              started_at                ended_at start_station_name start_station_id end_station_name end_station_id
1 9B9C7B1E3F4FC96C electric_bike 2026-04-13 14:47:32.170 2026-04-13 14:48:57.868                                                                    
2 8FE476DD539B3402 electric_bike 2026-04-13 09:56:56.062 2026-04-13 10:24:12.047                                                                    
3 CFA502A5FDC3E2D6 electric_bike 2026-04-13 08:33:39.927 2026-04-13 08:55:36.991                                                                    
4 AE6216BBF65C38AC electric_bike 2026-04-13 12:04:56.051 2026-04-13 12:31:00.820                                                                    
5 65C4A1F96AA07A5A electric_bike 2026-04-26 08:50:42.378 2026-04-26 08:56:44.514                                                                    
6 85DFEBC925D79F5C electric_bike 2026-04-26 12:42:25.222 2026-04-26 12:47:11.556                                                                    
  start_lat start_lng end_lat end_lng member_casual
1     41.96    -87.65   41.96  -87.65        member
2     41.91    -87.66   41.88  -87.63        member
3     41.96    -87.65   41.91  -87.66        member
4     41.88    -87.63   41.96  -87.65        member
5     41.93    -87.64   41.92  -87.64        member
6     41.94    -87.65   41.96  -87.65        member






###Dataset contains several variables consisting of qualitative and quantitative data, now using the 'glimpse' function, we can see the column names, column data types, and a list of the first few rows of the dataset.
```R
glimpse(Cyclisticdata)
```
>Rows: 448,252
Columns: 14
$ ride_id            <chr> "9B9C7B1E3F4FC96C", "8FE476DD539B3402", "CFA502A5FDC3…
$ rideable_type      <chr> "electric_bike", "electric_bike", "electric_bike", "e…
$ started_at         <chr> "47:32.2", "56:56.1", "33:39.9", "04:56.1", "50:42.4"…
$ ended_at           <chr> "48:57.9", "24:12.0", "55:37.0", "31:00.8", "56:44.5"…
$ Trip_duration      <chr> "01:25.7", "27:16.0", "21:57.1", "26:04.8", "06:02.1"…
$ start_station_name <chr> "", "", "", "", "", "", "", "", "", "", "", "", "", "…
$ start_station_id   <chr> "", "", "", "", "", "", "", "", "", "", "", "", "", "…
$ end_station_name   <chr> "", "", "", "", "", "", "", "", "", "", "", "", "", "…
$ end_station_id     <chr> "", "", "", "", "", "", "", "", "", "", "", "", "", "…
$ start_lat          <dbl> 41.96, 41.91, 41.96, 41.88, 41.93, 41.94, 41.91, 41.9…
$ start_lng          <dbl> -87.65, -87.66, -87.65, -87.63, -87.64, -87.65, -87.6…
$ end_lat            <dbl> 41.96, 41.88, 41.91, 41.96, 41.92, 41.96, 41.90, 41.9…
$ end_lng            <dbl> -87.65, -87.63, -87.66, -87.65, -87.64, -87.65, -87.6…
$ member_casual      <chr> "member", "member", "member", "member", "member", "me…

###Data insights I gathered from previewing are: 
* Membership data type will help sorting and filtering data for comparing between casual and annual subscribers.
* The Trip duration column that I calculated earlier will help in analysing duration comparisons among members.
* Geographic data will help in finding trends for location which are more accessible to cyclists and where is potential market for next phase of company expansion.

```R



```

#Process (3rd phase)

###The guiding questions for this phase will be:
1. What tools should I choose and why?
2. Ensuring data is clean and data integrity is maintained.
3. Documenting the cleaning and manipulation process properly.

Merging the workbook files into one big csv file is the first step in creating a workable file. After compiling this data in one big single data frame

Now converting raw text into recognizable date-time format:

```R
Cyclistic_cleaned <-  Cyclisticdata %>%
  mutate(
    formatted_datetime = ymd_hms(started_at),

    separated_month = month(started_at), 
    
    separated_day = day(formatted_datetime)
  )
```

View the final result
```R
print("Cleaned Dataset with Separated Columns:")
glimpse(Cyclistic_cleaned )
```

This notebook keeps track of data processing phase and now the dataset has been renamed as "Cyclistic_cleaned" which will render the processed dataset when queried.

```R



```

#Analyze (4th phase)

###The guiding questions for this phase will be:
1. Is the data properly formatted for this step to proceed?
2. What are visible trends and relationships I have found so far in this data??
3. Organise and format the data then proceed for trend analysis.

```R
usercount <- trips %>%
    group_by(user) %>%
    summarize(total = n()) %>%
    mutate(overall_total = sum(total)) %>%
    group_by(user) %>%
    summarize(percent_total = total/overall_total)

```
#####The query tells, 55.83% of the riders in past 12 months were annual subscribers and rest were casual riders.

```R
casual_member_biketype_used <- trips %>%
    filter(user == "casual") %>%
    group_by(bike) %>%
    summarize(total = n()) %>%
    mutate(overall_total = sum(total)) %>%
    group_by(bike) %>%
    summarize(percent_casual = total/overall_total)

```
##### The query suggests that Casual riders used classic bike for 61.3% of the times and used docked bikes the least for less than 15% of their usage combined



```R
riders_time_user <- trips %>%
    group_by(user) %>%
    summarize(avg_time = mean(ride_length), .groups = "drop")


riders_time_user$avg_time <- round(riders_time_user$avg_time , digits = 0)
```
#####This query returns average trip duration of casual users which is 28 minutes and annual subscribers ride for 13 minutes on average.

#### In conclusion it is found that casual riders spend twice as much time than annual members and also picks classic bikes for almost 62% of the time.


#Share (5th phase)

###These questions will guide this phase of analysis:
1. How do annual members and casual riders use Cyclistic bikes differently?
2. How does findings relate to original questions and are they visually sharable?
3. Is the result accessible to stakeholders?

For this visualization I have used Tableau but R (posit cloud) itself can be utilized with its ggplot package.
To extract the csv file to be loaded on Tableau following step is to be used.

```R
write_csv(Cyclistic_cleaned, "cyclistic_cleaned.csv")
```

Sometimes it is hard to find the saved file so I used this command to find the file path.
```R
getwd()

#This helps display the address where file is saved by R console

```
The file itself can be shared too and be used for further visualization too.
