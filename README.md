# IBM Db2 Workload Generator

This is the repository for the IBM Db2 Workload Generator created by Mike Bracey and Steve Speller.

This workload was designed for Db2 v7 and modified to work on up to Db2V10. Since there are customers requested to enhance this workload to work on the latest Db2 version
, we removed the code for V10 and below, and enhance it to work on Db2 V11 and above. 

Here are steps to install this workload onto your lpar:

1. Download GLWDEFDS and GLWINST from folder JCLs and put them on your LPAR. These JCL are sample JCLS to define all datasets for XMIT and TRS files, so you need to customize them with [HLQ] for your environment.
Alternately, we provide a sample JCL  FILES/DEF.JCL and FILES/UNPACK.JCL so you can submit them from your Windows workstation to define datasets and unpack the received datasets by executing the following command on Windows command prompt
ftp -s:define.txt to execute the JCL to define datasets for GLW.

1. Download files from folder Files and FTP them on your LPAR. File upload.txt is the sample ftp script to upload the datasets to your LPAR. Please customize them for your environment.
After uploading dataset onto zOS LPAR,  you need to either run the GLWINST from your LPAR or execute ftp -s:UNPACK.TXT to unpack the XMIT files and TRS files to datasets.
	
1. After excecuting above steps install GLW onto your LPAR.  You should have the following datasets:

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

		[HLQ].SGLWDATA.GLWLD5K.GLWTDPT.TRS

		[HLQ].SGLWDATA.GLWLD5K.GLWTEMP.TRS

		[HLQ].SGLWDATA.GLWLD5K.GLWTPRJ.TRS

		[HLQ].SGLWDATA.GLWLD5K.GLWTPJA.TRS

		[HLQ].SGLWDATA.GLWLD5K.GLWTEPA.TRS

	For description of members in those PDS datasets, please see README.MD file.

1. By default, the workload uses schema GLWSAMP so if you plan to use a different schema, then please replace GLWSAMP by your schema name in the following datasets:
	* 
	*
	
