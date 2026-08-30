# Extract an assessment element

Extract a given element from each of a list of assessments, such as the
output of
[`rl_assessment_list()`](https://docs.ropensci.org/rredlist/reference/rl_assessment_list.md).
This is useful for extracting specific details from the assessments,
such as taxonomy (`el_name = "taxon"`), synonyms
(`el_name = "taxon__synonyms"`), habitats (`el_name = "habitats"`), or
the red list category (`el_name = "red_list_category"`).

## Usage

``` r
rl_assessment_extract(lst, el_name, format = c("list", "df"), flatten = FALSE)
```

## Arguments

- lst:

  (list) A list of assessments, as returned by
  [`rl_assessment_list()`](https://docs.ropensci.org/rredlist/reference/rl_assessment_list.md).
  If `lst` contains any `NULL` elements, they will be removed.

- el_name:

  (character) The name of the element to extract from each assessment.
  Supports multilevel extraction using "\_\_" as the separator. For
  example, to extract the synonyms table, you could use
  "taxon\_\_synonyms". `el_name` may also be a character vector
  indicating multiple elements to extract. In this case, the output will
  contain all requested elements, either as a list (if
  `format = "list"`) or as a data.frame (if `format = "df"`). In the
  case of a data.frame, the extracted elements will be joined by
  `assessment_id`, which may result in an unexpected merged outcome when
  multiple rows are present in one or more of the extracted elements
  (e.g., the `"threats"` element).

- format:

  (character) The format of the output. Either "list" or "df" (for a
  data.frame).

- flatten:

  (logical) If `TRUE`, the output will be flattened to a data.frame.
  Note that this may not work for all elements, especially complex
  multilevel list elements. Only used when `format = "df"`. The `dplyr`,
  `tidyr`, and `tibble` packages are required to use this feature. Note
  that fields with no data across all assessments may be lost.

## Value

A list or data.frame containing the extracted element from each
assessment.

## Details

The following top-level element names can be extracted as of 2025-08-29:

- assessment_date

- assessment_id

- assessment_points

- assessment_ranges

- biogeographical_realms

- citation

- conservation_actions

- credits

- criteria

- documentation

- errata

- faos

- growth_forms

- habitats

- latest

- lmes

- locations

- population_trend

- possibly_extinct

- possibly_extinct_in_the_wild

- red_list_category

- references

- researches

- scopes

- sis_taxon_id

- stresses

- supplementary_info

- systems

- taxon

- threats

- url

- use_and_trade

- year_published

Note that there are also sublevels of the assessment hierarchy, but they
would be unwieldy to display here. A complete and up-to-date list can be
found by inspecting the return of an
[`rl_assessment()`](https://docs.ropensci.org/rredlist/reference/rl_assessment.md)
call.

## Examples

``` r
if (FALSE) { # \dontrun{
lst <- rl_assessment_list(ids = c(166290968, 136250858))
# get complex elements as a list
ex1 <- rl_assessment_extract(lst, "taxon")
# get simple elements as a data.frame
ex2 <- rl_assessment_extract(lst, "red_list_category__code", format = "df")
# get complex elements as a data.frame
ex3 <- rl_assessment_extract(lst, "threats", format = "df")
# get the same elements flattened to a single data.frame
ex4 <- rl_assessment_extract(lst, "threats", format = "df", flatten = TRUE)
# get subelements flattened to a data.frame
ex5 <- rl_assessment_extract(lst, "taxon__order_name", format = "df",
                             flatten = TRUE)
# get a data frame with both taxon name and red list category code
ex6 <- rl_assessment_extract(lst, c("taxon", "red_list_category__code"),
                             format = "df", flatten = TRUE)
} # }
```
