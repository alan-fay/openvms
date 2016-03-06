
OpenVMS FTPD - ftp server with support for UNIX file lists 
----------------------------------------------------------

The commands below show how to set the service to respond 
to requests on port 77:-  

	$ UCX SET SERV FTPD/PORT=77/INACT=5/LIMIT=10 -
	/PROCESS=FTPD/USER=SYSTEM -
	/SOCKET=(KEEP,RECEIVE:0,SEND:0) -
	/FILE=SYS$SYSDEVICE:[FTPD]FTPD_STARTUP.COM 
	$ !
	$ UCX ENABLE SERV FTPD
	$ EXIT

where the FTPD_STARTUP.COM file contains:-

	$ SAVE=5+2*f$getsyi("CLUSTER_NODES")
	$ PURGE/KEEP='save'
	$ DEFINE SYS$OUTPUT SYS$SYSDEVICE:[FTPD]FTPD.LOG
	$ DEFINE SYS$ERROR SYS$SYSDEVICE:[FTPD]FTPD.LOG
	$ RUN SYS$SYSDEVICE:[FTPD]FTPD.EXE
	$ !
	$ EXIT

From a VMS system type:-

	FTP> dir

for a complete list.

