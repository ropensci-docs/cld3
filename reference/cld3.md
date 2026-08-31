# Compact Language Detector 3

The function `detect_language()` is vectorised and guesses the the
language of each string in `text` or returns `NA` if the language could
not reliably be determined. The function `detect_language_multi()` is
not vectorised and detects all languages inside the entire character
vector as a whole.

## Usage

``` r
detect_language(text)

detect_language_mixed(text, size = 3)
```

## Arguments

- text:

  a string with text to classify or a connection to read from

- size:

  number of languages to detect

## Examples

``` r
# Vectorized best guess
text <- c("To be or not to be?", "Ce n'est pas grave.",
  "Hij heeft de klok horen luiden maar weet niet waar de klepel hangt.")
detect_language(text)
#> [1] "en" "fr" "nl"

# Multiple languages in one text (doesn't seem to work well)
detect_language_mixed(text)
#>   language probability reliable proportion
#> 1       nl   0.9999962     TRUE          1
#> 2      und   0.0000000    FALSE          0
#> 3      und   0.0000000    FALSE          0
```
