# File descriptions.

This folder contains datasets for the GLW workload. After transfering these .XMIT files to zOS LPAR using FTP to defined PDS datasets, we will use JCLs/GLWINST to unpack/terse them. 

## 1. SGLWCFG:  sample JCLs to set up and run the workload. These JCLs are from the SGLWSAMP and customized for the test environment. This set up uses the default values

	* CRTSG : sample JCL to create store group GLW01.   
	
	* GLWBUILD  : sample JCL to create database and objects for the GLW workload.   
	
	* GLWDEFDS  : sample JCL to define all xmit and trs dataset to prepare to receive files from FTP process.
	
	* GLWDROP   : sample JCL to drop objects created for the GLW workload.
	
	* GLWD001   : DDL to create optional usage tracking tables.
	
	* GLWINST   : sample JCL to receive data from xmit datasets and unterse the TRS datasets.   
	
	* GLWLDALL  : sample JCL to load data into GLW tables, in case of a WLMU has not been set up.
	
	* GLWPARM0  : sample parameter files. Needs to be customized for your environment.
	
	* GLWRSTAT  : sample JCL to perform runstats on GLW tablespaces.
	
	* GLWRUN    : sample JCL to run the workload.
	
	* GLWDDL    : DDL for the GLW workload.   
	
	* GLWSTART  : this EXEC needs to be customized for your environment if you plan to add GLW to ISPF.
	
	* GLWTBSEL  : sample JCL to select row count from GLW table to verify the load process.
	
	* README    : original readme file from the original authors.
	
	* WLMSAMP   : sample WLM environment definition.
	
2. 	SGLWDBRM : DBRM  for the GLW workload.

3. SGLWEXEC : REXX modules for the GLW workload. 

	* CRTSPCAT  : REXX module to creare stored procedure code.
	
	* DB2LOCK1  : REXX module to lock a Db2 table for a time interval.
	
	* GLW       : REXX EXEC to act as an interface to the GLW.
	
	* GLWBUILD  : REXX module to build environment for the GLW, called by GLWRUN.
	
	* GLWDB2LV  : REXX function to find the current level of Db2 subsystem.
	
	* GLWRUN    : REXX module to drive the workload.
	
	* SLEEP     : REXX function to wait x seconds.
	
4. SGLWLOAD : LOAD modules for the GLW workload.

5. SGLWMLIB : library for the GLW workload to display error messages.

6. SGLWSAMP : sample JCL to run the workload. These JCLs are copied to SGLWCFG  then customized for the running environment. For description, please see SGLWCFG section above.

7. SGLWSLIB : library for the GLW workload.

8. SGLWSRCC : DDL to create stored procedures ( in C language )used by the GLW workload.

9. SGLWSRCN : DDL to create stored procedures ( Native stored procedure ) used by the GLW workload.

10. SGLWTABD: DDL to load some data into tables of the GLW workload.



The .TRS files are data files  to be used to load into GLW tables.