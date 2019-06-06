# IBM Db2 Workload Generator

This is the repository for the IBM Db2 Workload Generator created by Mike Bracey and Steve Speller.

This workload was designed for Db2 v7 and modified to work up to Db2V10 by the original authors. Since there are customers requested to enhance this workload to work on the latest Db2 version, we removed the code for V10 and below, and enhance it to work on Db2 V11 and above. 

To install this workload onto your LPAR, you need to get the XMIT files and TRS files to your working LPAR, unpack the datasets, and customize the scripts/JCLs for your environment.

Here are steps to install this workload onto your lpar:

1. Clone or download all files onto your work station.

1. Get files onto your LPAR.
	After cloning this repository or downloading files onto your work station, you need to customize the helper files in folder FILES before executing those helper batch scripts.
	
	The hostname, userID, and password in the sample Windows batch scripts need to be changed for your environment if you plan to use these Windows batch files to automate the process. 
	
	You also need to update the [HLQ] for dataset name in GLWDEFDS.JCL, UPLOAD.TXT, and  UNPAK.JCL. These JCLs are for defining datasets for XMIT/TRS files, FTPing files to zOS LPAR, and unpacking the XMIT/TRS datasets into PDS datasets.
	
	To execute the helper batch scripts, you just run the following command at Windows command prompt: ftp -s:windowbatchscript. Here are example commands
	
		a. ftp -s:define.txt   : to submit JCL to define datasets for XMIT/TRS files.
		
		b. ftp -s:upload.txt   : to ftp downloaded files to the predefined datasets for XMIT/TRS files.
		
		c. ftp -s:unpak.txt    : to submit JCL to unpack the XMIT datasets and unterse the TRS datasets. 	
	
1. After getting files onto your LPAR, besides the XMIT and TRS datasets, you should have the following datasets:

		[HLQ].GLW.SGLWDBRM

		[HLQ].GLW.SGLWEXEC

		[HLQ].GLW.SGLWLOAD

		[HLQ].GLW.SGLWMLIB

		[HLQ].GLW.SGLWSAMP

		[HLQ].GLW.SGLWSLIB

		[HLQ].GLW.SGLWSRCC

		[HLQ].GLW.SGLWSRCN

		[HLQ].GLW.SGLWTABD
		
		[HLQ].GLW.SGLWCFG

		[HLQ].SGLWDATA.GLWLD5K.GLWTDPT

		[HLQ].SGLWDATA.GLWLD5K.GLWTEMP

		[HLQ].SGLWDATA.GLWLD5K.GLWTPRJ

		[HLQ].SGLWDATA.GLWLD5K.GLWTPJA

		[HLQ].SGLWDATA.GLWLD5K.GLWTEPA

	For description of members in those PDS datasets, please see Files/README.MD.

1. 	NOTE:
	
	1. Since GLW uses a predefined storage group GLWG01, you could use the sample JCL GLW.SGLWCFG(CRTSG) to define one for your environment.
	
	1. By default, the workload uses schema GLWSAMP so if you plan to use a different schema, then please replace GLWSAMP by your schema name for:

		* GLW.SGLWCFG/SGLSAMP: members GLWBUILD, GLWDDL, GLWDROP, GLWLDALL, GLWPARM0, and GLWRUN.
	
		* All members in GLW.SGLWSRCC, GLW.SGLWSRCN, and GLW.SGLWTABD.
	
1. Steps to build and run the GLW workload

	1. 
	
	
	
