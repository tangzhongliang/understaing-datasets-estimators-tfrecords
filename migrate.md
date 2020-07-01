### not modify

It is still possible to run 1.X code, unmodified (except for contrib), in TensorFlow 2.0:
```
import tensorflow.compat.v1 as tf
tf.disable_v2_behavior()
```
### Automatic conversion script
```
tf_upgrade_v2 -h
usage: tf_upgrade_v2 [-h] [--infile INPUT_FILE] [--outfile OUTPUT_FILE]
                     [--intree INPUT_TREE] [--outtree OUTPUT_TREE]
                     [--copyotherfiles COPY_OTHER_FILES] [--inplace]
                     [--no_import_rename] [--reportfile REPORT_FILENAME]
                     [--mode {DEFAULT,SAFETY}] [--print_all]

Convert a TensorFlow Python file from 1.x to 2.0

Simple usage:
  tf_upgrade_v2.py --infile foo.py --outfile bar.py
  tf_upgrade_v2.py --infile foo.ipynb --outfile bar.ipynb
  tf_upgrade_v2.py --intree ~/code/old --outtree ~/code/new

optional arguments:
  -h, --help            show this help message and exit
  --infile INPUT_FILE   If converting a single file, the name of the file to
                        convert
  --outfile OUTPUT_FILE
                        If converting a single file, the output filename.
  --intree INPUT_TREE   If converting a whole tree of files, the directory to
                        read from (relative or absolute).
  --outtree OUTPUT_TREE
                        If converting a whole tree of files, the output
                        directory (relative or absolute).
  --copyotherfiles COPY_OTHER_FILES
                        If converting a whole tree of files, whether to copy
                        the other files.
  --inplace             If converting a set of files, whether to allow the
                        conversion to be performed on the input files.
  --no_import_rename    Not to rename import to compact.v2 explicitly.
  --reportfile REPORT_FILENAME
                        The name of the file where the report log is
                        stored.(default: report.txt)
  --mode {DEFAULT,SAFETY}
                        Upgrade script mode. Supported modes: DEFAULT: Perform
                        only straightforward conversions to upgrade to 2.0. In
                        more difficult cases, switch to use compat.v1. SAFETY:
                        Keep 1.* code intact and import compat.v1 module.
  --print_all           Print full log to stdout instead of just printing
                        errors
```
