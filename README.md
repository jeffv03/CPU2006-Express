SPEC CPU2006 GCC
================

This is for SPEC CPU2006 on Linux with either an Intel or ARM processor.


Contents:
---------

+ [Structure](#structure)
+ [Usage](#useage)
+ [Troubleshooting](#troubleshooting)
+ [Optimizing GCC Process](#process-for-optimizing-gcc)


Structure:
----------

The assumed file structure is as follows:

```
.
|
+-- /
|
+-- /SPECCPU.tar
|
`-- /benchmarking.sh
```

Usage:
------

Change to directory where files are, then start benchmarking by issuing the following 
command:

```bash
./benchmarking.sh
```


Workflow:
---------

1. CPU detection
2. Distribution detection
3. Using CPU and distribution detection, select config file
4. Install CPU2006, if needed
5. RUNSPEC using config file for GCC
6. Consolidate scores into simple sysout


Troubleshooting:
================

If you are getting a `Permission denied` response, make sure you're running as root. 
If you are still getting the message, try using the following command:

```bash
chmod +x benchmarking.sh
```


Process for optimizing GCC:
===========================

1. Get GCC capable flags: `gcc -march=native -Q --help=target` or `echo "int main {return 0;}" | gcc [OPTIONS] -x c -v -Q -`

2. For Intel processors, go to [MARK](http://mark.intel.com/) to get CPU information and fill in hw_* information. Else, search for the hardware information on the Web.

3. Check [SPEC CPU2006](http://www.spec.org/cgi-bin/osgresults?conf=rint2006) for submitted results.

4. Trial and error.
