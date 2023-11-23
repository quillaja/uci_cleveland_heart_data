# UCI Heart Disease Dataset

Just the Cleveland dataset with 303 instances. There are two versions, one with the original numeric encoding of the categorical fields, and one with text encoded categorical fields. Both have the same headers in the first row.

I replaced 6 no-data values indicated by `?` with `NULL` so pandas will recognize them as `NA`. Helpful descriptive information is in each dataset's matching markdown file.

Data source:
https://archive.ics.uci.edu/dataset/45/heart+disease

Accessed: 2023-11-22
