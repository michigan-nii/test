# The basics of make

This page will go over the basics of the `make` command using examples from
neuroimaging.

## Examples

Here is a simple `Makefile` to do brain extraction using the `bet` command
from FSL.

```make
.PHONY: all clean

all: bold.nii.gz

bold_brain.nii.gz: bold.nii.gz
	bet bold bold_brain -m -R

clean:
    rm -f bold_brain.nii.gz bold_brain_mask.nii.gz
```
