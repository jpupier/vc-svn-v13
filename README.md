# VC_SVN v13

## Description

The VC_SVN component extends the [VC_Framework](https://github.com/4D/vc-framework) component by implementing the necessary "devhook" methods in order to support the standard actions:

* VC_DEVHOOK_Create
* VC_DEVHOOK_Update
* VC_DEVHOOK_Delete

In particular VC_SVN does the following:

* VC_DEVHOOK_Create - execute "svn add" for the indicated method.
* VC_DEVHOOK_Update - returns True
* VC_DEVHOOK_Delete - execute "svn delete" for the inidcated methdod.

Along with VC_Framework, the VC_SVN component facilitates automatic export of all methods in a [4D](http://www.4d.com) host database to text files on disk.  If the host database is under revision control with subversion, these text files are appropriately managed. The VC_SVN component is designed to have zero impact on the host database.  There is no startup code to install and nothing to configure. *IMPORTANT NOTE:* svn command line tools must be installed. Placing the 'svn' executable on the system path is advised as well. SVN 1.7+ is *required*.

## Contents

* The [components](https://github.com/4D/vc-svn/tree/master/Components) folder contains the "VC_SVN.4dbase" component suitable for installation in any [4D v13](http://www.4d.com/products/4dv13.html) database.
* The [matrix](https://github.com/4D/vc-svn/tree/master/matrix) folder contains the component source code.
* The [doc](https://github.com/4D/vc-svn/tree/master/doc) may contain documentation about the component...or I may use the Wiki...haven't decided yet :)

## Usage

Install both [VC_Framework](https://github.com/4D/vc-framework) and "VC_SVN.4dbase" in a 4D database Components folder. Launch the host database in 4D. Open any method if one is not open.

*IMPORTANT NOTE:* [VC_Framework](https://github.com/4D/vc-framework) is REQUIRED, VC_SVN does nothing without it.

*IMPORTANT NOTE:* svn command line tools must be installed. Placing the 'svn' executable on the system path is advised as well. SVN 1.7+ is *required*.

If you modify the matrix database, you should build a new component.  To build a new component, execute the VC_BLD_Build method from the matrix database (the matrix database uses the ["BLD.4dbase" component](https://github.com/4D/interpreted-build)).
