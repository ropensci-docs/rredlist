# Helper to get and save IUCN API key

Provides instruction on how to get and store a key for the IUCN API.
Users of `rredlist` must do this before using any of the package's other
functionality. Note that registering for a key requires an email address
and information about your organization.

## Usage

``` r
rl_use_iucn()
```

## Value

Invisibly returns the sign-up URL for the IUCN Red List API.

## Details

Note that after filling the online form, you should receive an API key
shortly but not immediately.

## Examples

``` r
if (FALSE) { # \dontrun{
# Sign up for an API key
rl_use_iucn()
} # }
```
