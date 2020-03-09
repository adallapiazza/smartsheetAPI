libraries <- c('odbc', 'DBI', 'curl', 'rstudioapi', 'httr', 'readr', 'jsonlite', 'data.table', 'tidyverse', "lubridate", "stringr")
invisible(suppressMessages(suppressWarnings(lapply(libraries, require, character.only = TRUE))))

options(scipen = 999)
# Convert all warnings to errors
options(warn = 2)

## Scrape SmartSheet data into a data frame ##################################################
# API Key - this is user dependent
api = "PUT_API_KEY_HERE"

# Function to read Smartsheet sheets
ss_pull <- function(api, sheet_num) {
  # Sys.setenv(https_proxy = 'http://proxy.site.com:PORT') # set proxy if needed
  p <- NULL
  temp1 <- NULL
  p <- GET(paste0("https://api.smartsheet.com/2.0/sheets/", sheet_num), add_headers(Authorization = paste("Bearer", api), Accept = "text/csv"))
  temp1 <- suppressWarnings(suppressMessages(content(p, as = "parsed")))
  df_raw <- NULL
  df_raw <- data.table(temp1)
}

unqiue_sheet_num <- "PUT SHEET NUMBER HERE"
df_smartsheet <- ss_pull(api, unqiue_sheet_num)
