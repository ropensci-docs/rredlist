# rredlist: 'IUCN' Red List Client

'IUCN' Red List (<https://api.iucnredlist.org/>) client. The 'IUCN' Red
List is a global list of threatened and endangered species. Functions
cover all of the Red List 'API' routes. An 'API' key is required.

## Authentication

IUCN requires you to get your own API key, an alphanumeric string that
you need to send in every request. See
[`rl_use_iucn()`](https://docs.ropensci.org/rredlist/reference/rl_use_iucn.md)
for help getting and storing it. Get it at
<https://api.iucnredlist.org/users/sign_up>. Keep this key private. You
can pass the key in to each function via the `key` parameter, but it's
better to store the key either as an environment variable
(`IUCN_REDLIST_KEY`) or an R option (`iucn_redlist_key`) - we recommend
using the former option.

## High vs. Low level package APIs

**High level API** High level functions do the HTTP request and parse
data to a data.frame for ease of downstream use. The high level
functions have no underscore on the end of the function name, e.g.,
[`rl_species()`](https://docs.ropensci.org/rredlist/reference/rl_species.md).

**Low level API** The parsing to data.frame in the high level API does
take extra time. The low level API only does the HTTP request, and gives
back JSON without doing any more parsing. The low level functions DO
have an underscore on the end of the function name, e.g.,
[`rl_species_()`](https://docs.ropensci.org/rredlist/reference/rl_species.md).

## No Spatial

This package does not include support for spatial data from the IUCN Red
List. IUCN Red List Spatial data can be downloaded at
<https://www.iucnredlist.org/resources/spatial-data-download>.

## Citing the IUCN Red List API

Get the proper citation for the version of the Red List you are using by
programatically running
[`rl_citation()`](https://docs.ropensci.org/rredlist/reference/rl_citation.md).
Also see <https://api.iucnredlist.org/>.

## Red List API Terms of Use

See <https://www.iucnredlist.org/terms/terms-of-use>.

## Rate limiting

From the IUCN folks: Too many frequent calls, or too many calls per day
might get your access blocked temporarily. If you're a heavy API user,
the Red List Unit asked that you contact them, as there might be better
options. They suggest a 2-second delay between your calls if you plan to
make a lot of calls.

## See also

Useful links:

- <https://docs.ropensci.org/rredlist/>

- <https://github.com/ropensci/rredlist>

- Report bugs at <https://github.com/ropensci/rredlist/issues>

## Author

**Maintainer**: William Gearty <willgearty@gmail.com>
([ORCID](https://orcid.org/0000-0003-0076-3262))

Authors:

- Scott Chamberlain <myrmecocystus@gmail.com>
  ([ORCID](https://orcid.org/0000-0003-1444-9135))

Other contributors:

- rOpenSci ([ROR](https://ror.org/019jywm96)) \[funder\]

- Maëlle Salmon <maelle.salmon@yahoo.se>
  ([ORCID](https://orcid.org/0000-0002-2815-0399)) \[contributor\]

- Kevin Cazelles <kevin.cazelles@insileco.io>
  ([ORCID](https://orcid.org/0000-0001-6619-9874)) \[reviewer\]

- Stephanie Hazlitt <stephhazlitt@gmail.com>
  ([ORCID](https://orcid.org/0000-0002-3161-2304)) \[reviewer\]
