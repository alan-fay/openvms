
Install "md5sum" as a foreign command. Copy the executable:

	$ copy md5sum.exe sys$common[sysexe]md5sum.exe

and define the "md5sum" symbol as:

	$ md5sum :== $sys$common:[sysexe]md5sum.exe

	$ md5sum --help
	Usage: md5sum [OPTION] [FILE]...
	   or: md5sum [OPTION] --check [FILE]
	Print or check MD5 checksums.
	With no FILE, or when FILE is -, read standard input.
	
	  -b, --binary        read files in binary mode
	  -c, --check         check MD5 sums against given list
	  -o, --output        write output list to a given file
	  -p, --portable      read files in portable mode
	                      (produces same digest on /Windows/Unix/Mac/VMS)
	  -t, --text          read files in text mode (default)
	  -v, --version       display version
	  -f, --full          display full file specification
	
	The following two options are useful only when verifying checksums:
	  -s, --status        don't output anything, status code shows success
	  -w, --warn          warn about improperly formatted MD5 checksum lines
	
	  -h, --help          display this help and exit
	
	The sums are computed as described in RFC 1321.  When checking, the
	input should be a former output of this program.  The default mode is to
	print a line with checksum, a character indicating type (`*' for binary,
	`?' for portable, ` ' for text), and name for each FILE.
	
	$ 

