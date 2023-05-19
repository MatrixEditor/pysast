.. _sast_scans:

======================
Performing a SAST Scan
======================

The ``pysast`` module can also be used as a command line utility. It provides a convenient
way to perform Static Application Security Testing (SAST) scans on one or more files or
directories. This comprehensive guide will walk you through the various options and
functionalities of ``pysast``, enabling you to leverage its power for effective code
analysis and vulnerability detection.

Command syntax
--------------

The general syntax for using pysast is as follows:

.. code:: shell

    pysast.py [-h] [-r] [-j] [-v] [-s SAST_RULES] [-S SAST_DIRS] [-rS] \
        [--disable-prefilter] [--enable-postfilter] [-M MAX_BYTES] [PATHS ...]

Let's explore the available options and their functionalities:

Positional Arguments
~~~~~~~~~~~~~~~~~~~~

- ``PATHS``:
    One or more files or directories to scan. Specify the path(s) to the file(s) or
    directory(ies) you want ``pysast`` to analyze.

Options
~~~~~~~

-h, --help
 Displays the help message and exits.

-r, --recursive
 Scan target directories recursively. This option enables pysast to scan
 files within the specified directories and their subdirectories.

-j, --json
 Dump JSON output instead of using pprint. Use this option if you prefer
 the scan results in JSON format.

-v, --verbose
 Specifies the verbosity for the next scan. You can use -v for verbose
 output and -vvv for more detailed and verbose output.

-s SAST_RULES, --sast-rule SAST_RULES
 Specifies the file path(s) to the SAST rules you want to import. You can
 provide one or more file paths separated by spaces. This option allows you
 to use custom SAST rules for the scan.

-S SAST_DIRS, --sast-dir SAST_DIRS
 Specifies one or more directories that store SAST rules. You can provide
 one or more directory paths separated by spaces. Use this option when your
 SAST rules are stored in directories instead of individual files.

-rS, --recursive-sast-dir
 Load rules from target directories recursively. When using this option,
 ``pysast`` will search for SAST rules in the specified directories and
 their subdirectories.

--disable-prefilter
 Disable prefiltering rules. By default, pysast applies a prefiltering
 step to improve the performance of the scan. Use this option if you want
 to disable the prefiltering step.

--enable-postfilter
 Enable postfiltering. This option allows pysast to apply additional filtering
 on the scan results, further refining the output.

-M MAX_BYTES, --max-bytes MAX_BYTES
 Skip files exceeding the specified maximum bytes. Use this option to set a
 threshold for the file size. Files larger than the specified maximum bytes
 will be skipped during the scan.


Usage Examples
--------------

Let's look at some examples of using pysast with different options:

- Scan a single file:

    .. code:: bash

        pysast.py path/to/file.py

- Scan multiple files:

    .. code:: bash

        pysast.py path/to/file1.py path/to/file2.py path/to/file3.py

- Scan a directory recursively:

    .. code:: bash

        pysast.py -r path/to/directory

- Scan a directory with custom SAST rules:

    .. code:: bash

        pysast.py -s path/to/rules.json path/to/directory

- Scan a directory with SAST rules stored in a directory:

    .. code:: bash

        pysast.py -S path/to/rules_directory path/to/directory

- Scan a directory with recursively loaded SAST rules:

    .. code:: bash

        pysast.py -rS path/to/rules_directory path/to/directory

- Scan with verbose output:

    .. code:: bash

        pysast.py -v path/to/file.py

- Scan with JSON output:

    .. code:: bash

        pysast.py -j path/to/file.py

- Scan with maximum file size limit:

    .. code:: bash

        pysast.py -M 10000 path/to/file.py

These examples demonstrate some common usage scenarios of pysast. You can
combine multiple options to tailor the scan according to your specific needs.