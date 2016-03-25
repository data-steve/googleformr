![](inst/googleformr_yay.png)

**googleformr** let's you POST data more securely to Google Forms without needing authentication or permissions like with Google Sheets.

Installation
============

To download the development version of **googleformr**:

Download the [zip
ball](https://github.com/data-steve/googleformr/zipball/master) or
[tar
ball](https://github.com/data-steve/googleformr/tarball/master),
decompress and run `R CMD INSTALL` on it, or use the **pacman** package
to install the development version:

    if (!require("pacman")) install.packages("pacman")
    pacman::p_load_gh("data-steve/googleformr")

DEMO
=======

**googleformr** comes pre-loaded with a demo function `why_R_u_opensource`. To try out, [read more about it here](http://data-steve.github.io/googleformr-asks-why-R-u-opensource). 

```r
googleformr::why_R_u_opensource("") # <- your reason goes here
```

Here's how I made it
```r
# create function
form <- "https://docs.google.com/forms/d/1Ttl_SGI1cjRHSw_oU7kwxnGESoMwf4BU4NMAqPA-BRs/viewform"
why_R_u_opensource <- googleformr::gformr(form,
                                        custom_reply= "Thanks for being open!")

# send reason!
why_R_u_opensource("R community in my city has been really supportive to my learning.")
```

You can create your own linked-function to a Google Form using: 
```r
# create function
form <- "your_google_form_url"
your_func <- googleformr::gformr(form)

# send data
your_func(your_data)
```


You can extract Google Form question text or entry points using:

```r
# questions
form <- "your_google_form_url"
form %>% get_form() %>% get_form_questions()

# entry ids
form %>% get_form() %>% get_form_entry_ids()
```

Contact
=======

You are welcome to: 
- submit suggestions and bug-reports at: <https://github.com/data-steve/googleformr/issues> 
- send a pull request on: <https://github.com/data-steve/googleformr/> 
- compose a friendly e-mail to: <steven.troy.simpson@gmail.com>
