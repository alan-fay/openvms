

Install "shasum" as a foreign command. Copy the executable:

	$ copy shasum.exe sys$common[sysexe]shasum.exe

and define the "shasum" symbol as:

	$ shasum :== $sys$common:[sysexe]shasum.exe

	$ shasum --help
	Usage: shasum [OPTION] [FILE]...
	   or: shasum [OPTION] --check [FILE]
	Print or check SHA checksums.
	With no FILE, or when FILE is -, read standard input.
	
	  -a, --algorithm     1 (default), 224, 256, 384, 512
	  -b, --binary        read files in binary mode
	  -c, --check         check SHA sums against given list
	  -o, --output        write output list to a given file
	  -p, --portable      read files in portable mode
	                      (produces same digest on /Windows/Unix/Mac/VMS)
	  -t, --text          read files in text mode (default)
	  -v, --version       display version 
	  -f, --full          display full file specification
	
	The following two options are useful only when verifying checksums:
	  -s, --status        don't output anything, status code shows success
	  -w, --warn          warn about improperly formatted SHA checksum lines
	
	  -h, --help          display this help and exit
	
	The sums are computed as described in FIPS PUB 180-2.  When checking, the
	input should be a former output of this program.  The default mode is to
	print a line with checksum, a character indicating type (`*' for binary,
	`?' for portable, ` ' for text), and name for each FILE.
	
	$ 
	
