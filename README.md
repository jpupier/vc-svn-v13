# VC_SVN

## Description

The VC_SVN component extends the [VC_Framework](https://github.com/4D/VC_Framework) component by implementing the necessary "devhook" methods in order to support the standard actions:

* VC_DEVHOOK_Create
* VC_DEVHOOK_Update
* VC_DEVHOOK_Delete

In particular VC_SVN does the following:

* VC_DEVHOOK_Create - execute "svn add" for the indicated method.
* VC_DEVHOOK_Update - returns True
* VC_DEVHOOK_Delete - execute "svn delete" for the inidcated methdo.

Along with VC_Framework, The VC_SVN component facilitates automatic export of all methods in a [4D](http://www.4d.com) host database to text files on disk.  If the host database is under revision control with subversion, these text files are appropriately managed. The VC_SVN component is designed to have zero impact on the host database.  There is no startup code to install and nothing to configure. *IMPORTANT NOTE:* svn command line tools must be installed and on the system path.

## Contents

* The [components](https://github.com/4D/VC_SVN/tree/master/components) folder contains the interpreted component suitable for installation in any [4D v13](http://www.4d.com/products/4dv13.html) database.
* The [matrix](https://github.com/4D/VC_SVN/tree/master/matrix) folder contains the component source code.
* The [doc](https://github.com/4D/VC_SVN/tree/master/doc) folder contains documentation about the component.

## Usage

Install both [VC_Framework](https://github.com/4D/VC_Framework) and VC_GitHub in a 4D database Components folder. Open any method.

If you modify the matrix database, you should build a new component.  To build a new component, execute the VC_BLD_Build method from the matrix database.

## Known Issues

20120816 - Non-unique form object Object Names will cause [METHOD GET CODE](http://doc.4d.com/4Dv13.1/help/Command/en/page2591.html) to fail with the error -9768, "Invalid object path: {path}". 4D does not allow non-unique Object Names in a given form, but this issue can occur via conversion from older versions. The solution is to make all of the Object Names unique ([this can be automated](http://kb.4d.com/assetid=76640)). VC_SVN should take this into account but I'm not sure how yet. Right now this errror disables the export, which is not good. But I don't want to ignore -9768 either because it is a legitimate error. I have filed [a feature request](http://forums.4d.fr/Post/EN/11108706/1/11108707) for a unique error code in this situation.
