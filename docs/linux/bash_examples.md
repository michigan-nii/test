# Bash examples

Here are some links to example scripts that show some of the things you can
do with shell scripts.

## Getting and unpacking data

Our first example will simply get some data from a public data source
and unpack it.

```
#!/bin/bash

# Data URL; extract just the file name
data_source='https://s3.amazonaws.com/openneuro'
data_source="$data_source/ds000008/ds000008_R2.0.0/compressed/ds008_R2.0.0_raw.tgz"
data_file=$(basename $data_source)

# Create a temporary directory into which to put our download; change there
# The command to the right of the && will run only if the one on the left
# succeeded
tmp_dir=$(mktemp -d openfmri.XXXXXXXX) && cd $tmp_dir

# Data checksum (you have to get this from somewhere. This script is for
# people to use as an example, so we provide the checksum. This lets us
# check that the file downloaded correctly. Put it into a file for later
# use
echo "0b7d0fb6ad56e3ecf8ae70433197e85f  $data_file" > data_md5

# We assume you have wget installed
wget $data_source

# Check it
md5sum -c data_md5
if [ $? -ne 0 ] ; then
    echo "The data file does not match the checksum.  Please investigate."
    exit 1
fi

if [ -d ~/Projects ] ; then
    tar -x -z -C ~/Projects -f $data_file
else
    echo "The ~/Projects folder does not exist.  Cleaning up and exiting."
    rm -r $tmp_dir
    exit 1
fi
```
