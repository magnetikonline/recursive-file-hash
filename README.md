# Recursive file hash
Python utility to recursively walk a given directory and generate an ordered list of files alongside their filesize and SHA-1 hash.

- [Usage](#usage)
- [Example](#example)

## Usage

```
usage: recursivefilehash.py [-h] [--progress] [--result-file RESULT_FILE]
                            scandir

Recursively walk directory and generate ordered list of file path, filesize
and SHA-1 hash.

positional arguments:
  scandir               source directory for scanning

optional arguments:
  -h, --help            show this help message and exit
  --progress            display activity during processing
  --result-file RESULT_FILE
                        send results to file, rather than stdout
```

## Example
Scan directory `/path/to/files`, displaying progress as processing and output results to `/tmp/my-results`:

```sh
$ ./recursivefilehash.py \
	--progress \
	--result-file /tmp/my-results \
		-- /path/to/files

$ cat /tmp/my-results
1a7c22b9611d57584a202d94bac1570cefd492d7	  987758	/path/to/files/first
e182acd96094417cbd22399b09282ea5f2175a5e	 1008844	/path/to/files/second
380ed0ce37a2bdf762201a023e244a29068f38d8	  911319	/path/to/files/third
f1dc7800602667461c116447c2afcbfd0e451670	  907618	/path/to/files/fourth
# and so on...
```
