# filespherapy
A simple and powerful python library for file path construction and manipulation.

Definitions and Naming

* Filepath
  - A string that describes the directory location and filename, including file extension.

* Dirname
  - The part of a filepath that identifies the directory context of a file.

* Basename
  - The part of a filepath that names the file, including its extension.

* Rootname
  - The part of a basename that precedes the last '.' (the filename segment delimiter).

* Extname
  - The part of a basename that comes after the last filename segment delimiter (the first '.').

Examples

```
>>> from filespherapy.tools import Filesphere
>>>
>>> # create sphere A from filepath
... fsphA = Filesphere(filepath='/my/dir/name/A/mystemnameA.myextnameA')
>>> print fsphA

                  extname: .myextnameA
                 basename: mystemnameA.myextnameA
                  dirname: /my/dir/name/A
                 stemname: mystemnameA
                 filepath: /my/dir/name/A/mystemnameA.myextnameA

>>>
>>> fsphA.show_filepath()
/my/dir/name/A/mystemnameA.myextnameA
>>> fsphA.show_dirname()
/my/dir/name/A
>>> fsphA.show_basename()
mystemnameA.myextnameA
>>> fsphA.show_stemname()
mystemnameA
>>> fsphA.show_extname()
.myextnameA
>>>
>>> # create sphere B from dirname, basename
... fsphB = Filesphere(dirname='/my/dir/name/B', basename='mystemnameB.myextnameB')
>>> print fsphB

                  extname: .myextnameB
                 basename: mystemnameB.myextnameB
                  dirname: /my/dir/name/B
                 stemname: mystemnameB
                 filepath: /my/dir/name/B/mystemnameB.myextnameB

>>>
>>> # create sphere C from dirname, stemname, extname
... fsphC = Filesphere(dirname='/my/dir/name/C', stemname='mystemnameC', extname='myextnameC')
>>> print fsphC

                 basename: mystemnameC.myextnameC
                  dirname: /my/dir/name/C
                 filepath: /my/dir/name/C/mystemnameC.myextnameC
                 stemname: mystemnameC
                  extname: myextnameC

>>>
>>> # update the dirname of A
... fsphA.update(dirname='/my/new/dir/name')
>>> print fsphA

                  extname: .myextnameA
                 basename: mystemnameA.myextnameA
                  dirname: /my/new/dir/name
                 stemname: mystemnameA
                 filepath: /my/new/dir/name/mystemnameA.myextnameA

>>>
>>> # update the basename of B
... fsphB.update(basename='mynew.basename')
>>> print fsphB

                  extname: .basename
                 basename: mynew.basename
                  dirname: /my/dir/name/B
                 stemname: mynew
                 filepath: /my/dir/name/B/mynew.basename

>>>
>>> # update the stemname of C
... fsphC.update(stemname='newroot')
 my new stemname: newroot
 tmp_basename: mystemnameC.myextnameC
 tmp_extname: .myextnameC
>>> print fsphC

                 basename: mystemnameC.myextnameC
                  dirname: /my/dir/name/C
                 filepath: /my/dir/name/C/newroot.myextnameC
                 stemname: newroot
                  extname: myextnameC

>>>
>>> # also update the extname of C
... fsphC.update(extname='newext')
 my new extname: newext
 basename: newroot.myextnameC
 stemname: newroot
>>> print fsphC

                 basename: mystemnameC.myextnameC
                  dirname: /my/dir/name/C
                 filepath: /my/dir/name/C/newroot.newext
                 stemname: newroot
                  extname: newext

>>>
>>> # filepath with multiple filename segment delimiters ('.')
... fsphD = Filesphere(filepath='/my/dir/name/D/stemname.D.extname')
>>> print fsphD

                  extname: .extname
                 basename: stemname.D.extname
                  dirname: /my/dir/name/D
                 stemname: stemname.D
                 filepath: /my/dir/name/D/stemname.D.extname

>>>
```
