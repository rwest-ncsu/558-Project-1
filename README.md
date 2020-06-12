README
================
Robert West
6/8/2020

# Describe JSON data. What is it, where does it get used, and why is it a good way to store data? This should be detailed enough that someone that hasn’t seen JSON data would have a good idea what they are dealing with. You should link to references where applicable.

*Java Script Object Notation* (or JSON) is a text-based data format that
is used primarily to send and receive data from internet applications.
It is so widely used because its text structure makes it much easier to
send files. The “issue” that this can bring with it is that you need to
convert the text representation of data into an object that R (or any
other language) knows how to work
with.

# Discuss the possible packages/functions that are available for reading JSON data into R. (There are three major packages for JSON data.) Choose one and explain why you’ve chosen it.

The package that I chose to work with is the `jsonlite` package. I chose
this because it offers the functionality to return a nested list as a
data frame without parsing the data yourself.

To get a feel for handling JSON data, let’s communicate with an API
(Application Programming Interface) for the NHL. The URL for accessing
the API is saved below and a function for requesting Franchise
information is provided to make code more readable. In this function, I
utilize:

  - httr::GET() to access a given web address
  - httr::content() to turn the output into a text file
  - jsonlite::fromJSON() to turn the text file into a data frame

To access more data from the API, I wrote 4 more functions
extraordinarily similar to the `get_franchises()` function but with
different URLs. Every API is different. To determine how to request the
right information, you need to read the
[documentation](https://gitlab.com/dword4/nhlapi/-/blob/master/records-api.md)

``` r
base_url = "https://records.nhl.com/site/api"
```

``` r
get_franchises = function(){
  full_url = paste0(base_url, "/franchise")
  text = content(GET(url=full_url), "text") #Converts the JSON output from the API to a text file
  list_output = jsonlite::fromJSON(text, flatten = T)
  
  return(list_output$data)
}
```
