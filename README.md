# IBM Db2 Workload Generator

This is the repository for the IBM Db2 Workload Generator created by Mike Bracey and Steve Speller.

This workload was designed for Db2 v7 and modified to work on up to Db2V10. Since there are customers requested to enhance this workload to work on the latest Db2 version
, we post this workload and create a branch for Db2 version 11 and above. 

Here are steps to install this workload onto your lpar:

1. Download files from folder DataFiles and XMITSFiles and put them on your LPAR.

1. Download GLWDEFDS and GLWINST from folder JCLs and put them on your LPAR. These JCL are sample JCLS to define all datasets for XMIT and TRS files, so you need to customize them for your environment.

1. Excecute above JCLs to install GLW onto your LPAR.  You should have the following datasets:

*.SGLWDATA.GLWLD5K.GLWTDPT.TRS

*.SGLWDATA.GLWLD5K.GLWTEMP.TRS

*.SGLWDATA.GLWLD5K.GLWTPRJ.TRS

*.SGLWDATA.GLWLD5K.GLWTPJA.TRS

*.SGLWDATA.GLWLD5K.GLWTEPA.TRS


4. Get the latest support datasets in NEW/SGLWEXEC and NEW/SGLWSAMP and replace the deprecicated version with these new ones.

5. Follow installation instruction in  README
