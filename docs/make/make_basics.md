# The basics of make

This page will go over the basics of the `make` command using examples from
neuroimaging.

## Examples

`Makefile`
<hr noshade>
```
.PHONY: all clean

all: bold.nii.gz

bold_brain.nii.gz: bold.nii.gz
    bet bold bold_brain -m -R

clean:
    rm -f bold_brain.nii.gz bold_brain_mask.nii.gz
```
<hr noshade>
