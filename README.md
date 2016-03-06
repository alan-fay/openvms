
## OpenVMS df - Disk Free 

I know there are other versions of this Linux command
out there for OpenVMS as DCL scripts, etc.

I'd like to add a version which I have written for VAX
and Alpha which I have found to be quite useful (I don't
have access to an IA64 system).

The default display is "df -b" display 512-byte blocks
for example, on my small Alpha:

	$ df
	Device Name         Blocks        Used       Avail Capacity  Volume Label
	ALPHA$DKB100:     71833096    15939784    55893312    22%    ALPHASYS
	ALPHA$DKB200:     71833096    17662162    54170934    24%    DEVDISK1
	$

and the "df -h" human readable output:

	$ df -h
	Device Name         Size      Used     Avail Capacity  Volume Label
	ALPHA$DKB100:     34.2GB     7.6GB    26.6GB    22%    ALPHASYS
	ALPHA$DKB200:     34.2GB     8.4GB    25.8GB    24%    DEVDISK1
	$

The human readable units are true multiples of 1024
but the output will never display more than 999 of
any unit. No rounding is performed as I have found
that in doing so can result in nonsensical results.

If you want a true picture use "df" or "df -b" to
display the 512-byte blocks.

I have not tested this on bound-volume sets or any
large raid-arrays, so I don't know what the results
will be.

This is free software for anyone to use commercial
or non-commercial.

"df" has NO software dependencies and will run on any OpenVMS version.

These are available from:

https://github.com/alan-fay/openvms

The simplest way to download is to just "Download ZIP" and extract the files you want.

Install "df" as a foreign command. Copy the executable:

	$ copy df.exe sys$common[sysexe]df.exe

and define the "df" symbol as:

	$ df :== $sys$common:[sysexe]df.exe


Alan Fay

-----------------------------------------------------------------------

FreeWare: Free for anyone to use commercial/non-commercial.

This software is provided "as is" without warranty of any kind, express
or implied.  In no event shall the author or any contributors be held
liable for any direct, indirect, incidental, special or consequential
damages arising out of the use of or inability to use this software.

-----------------------------------------------------------------------

