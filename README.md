niceLiftOver
============

niceLiftOver is a simple wrapper script to take an input file and liftOver the co-ordinates in place, leaving all other data in tact. 

It can be used with any file format and will try to guess the delimiter and which columns contain the chromosome, start and end positions.


Requirements
------------
niceLiftOver runs on the command line, so is best suited to unix environments.
It is written in Perl and uses the `strict`, `warnings`, `Getopt::Long` and `FindBin` packages. These are core packages and typically come with most Perl installations.

Installation
------------
niceLiftOver is best used when added to your `PATH` environment. It is suitable for use with environment modules.
If you are not using environment modules, you can install niceLiftOver by adding the following to the `.bashrc` file in your home directory: `export PATH="$PATH":<installation directory>/niceLiftOver`

Usage
-----
Typical useage for niceLiftOver is `niceLiftOver <chain ID> *.files`

niceLiftOver will look at the first line of the first file supplied and try to determine the delimeter between columns and then which column holds the chromosome and which hold the start and end positions. These can all be manually specified, see below.

liftOver needs a chain file. These are kept in `<installation directory>/chainfiles/`. Available chain files can be seen by running `niceLiftOver --listchains`

Additional chain files can be downloaded from the [UCSC](http://hgdownload.cse.ucsc.edu/downloads.html)


Parameters
---------
* `--listchains`
	* List the available chain file IDs.
	* These are stored in `<installation directory>/chainfiles/`
	* Files must end in .over.chain

* `--skip <int>`
	* Skip `n` lines at the start of each file

* `--chr <int>`
	* Integer to specify which column should be used for the chromosome
	* 1 based index, eg. First column = 1 (not 0)
	* Defaults to searching the first line for the first occurance of "chr"

* `--start <int>`
	* Integer to specify which column should be used for the start position
	* 1 based index, eg. First column = 1 (not 0)
	* Defaults to searching the first line for the first occurance of "start"

* `--end <int>`
	* Integer to specify which column should be used for the end position
	* 1 based index, eg. First column = 1 (not 0)
	* Defaults to searching the first line for the first occurance of "end"

* `--delim <str>`
	* String delimiter to use to split columns
	* If not specified, niceLiftOver will try to split the first line using
	* tabs, commas and whitespace (in that order)

* `--repdomain`
	* Shortcut to specify repdomain.com file format

* `--version`
	* Print the version of the software

* `--help`
	* Print this help message.


Author
------
niceLiftOver was written by Phil Ewels at the Babraham Institute, Cambridge, UK


