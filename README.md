# gohashID
Identify a hash type.


gohashID is written in Go. 
It takes a hash, calculates the length, and compares the length against the [hashcat example hashes](https://hashcat.net/wiki/doku.php?id=example_hashes)

*Notes: 
..*Hash is provided in a file to clean up whitespace and prevent interpolation.
..*Only 1 hash can be provided at a time in a file. 
..*Remove any usernames, domain information, etc. from the raw hash provided. This tool compares hashes by length so usernames with varying length sizes will not match the examples in hashcatexamples.csv
..*The next upgrade will address some of these limitations.

Usage
------------
go run gohashID.go -file <<Filename>> [default: hash.txt] 

Example: go run gohashID.go -file hash.txt

or build

env GOOS=windows GOARCH=386 go build -v gohashID.go
env GOOS=linux GOARCH=amd64 go build -v gohashID.go

hashcatexamples.csv file is required


|Parameter     |Description  |
|-----------|-------------------------------------------------------|
|-file      |inpute file with hash <<Filename>> [default: hash.txt] |
|-h, --help |show help message and exit                             |



Screenshot
----------

    $ go run gohashID.go -file hash.txt
	gohashID v0.6          Pat Flanigan
	=========================================

	NetNTLMv1 / NetNTLMv1+ESS [-m 5500]


    $ cat hash.txt
    338d08f8e26de93300000000000000000000000000000000:9526fb8c23a90751cdd619b6cea564742e1e4bf33006ba41:cb8086049ec4736c
    

Resources
---------

-  https://hashcat.net/wiki/doku.php?id=example_hashes
