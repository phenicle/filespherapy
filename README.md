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
  - The part of a basename that precedes the first '.' (the filename segment delimiter).

* Extname
  - The part of a basename that comes after the first filename segment delimiter (the first '.').

Examples

```
	print
	print "create sphere A from filepath"
	fsphA = Filesphere(filepath='/my/dir/name/A/myrootnameA.myextnameA')
	fsphA.show()
	print

	print "create sphere B from dirname, basename"
	fsphB = Filesphere(dirname='/my/dir/name/B', basename='myrootnameB.myextnameB')
	fsphB.show()
	print

	print "create sphere C from dirname, rootname, extname"
	fsphC = Filesphere(dirname='/my/dir/name/C', rootname='myrootnameC', extname='myextnameC')
	fsphC.show()
	print

	print "update the dirname of A"
	fsphA.update(dirname='/my/new/dir/name')
	fsphA.show()
	print

	print "update the basename of B"
	fsphB.update(basename='mynew.basename')
	fsphB.show()
	print

	print "update the rootname of C"
	fsphC.update(rootname='newroot')
	fsphC.show()
	print

	print "finally, also update the extname of C"
	fsphC.update(extname='newext')
	fsphC.show()
	print
```
