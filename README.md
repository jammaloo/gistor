## gistor

A simple CLI tool which could let you manage gist easily.

## Usage
Install gistor using npm  
```
npm install -g gistor
```

First setup your authorization information.  
```
gistor --login --user {USERNAME} --pass {PASSWORD}
```
It will call github [Authorization](http://developer.github.com/v3/oauth/#create-a-new-authorization) and create new one. If it success, will save return value to `.gistor` in your home directory. Then you can start using gistor to manage your gist right now!

### create
```
gistor --create [--desc] {DESC} [files...]
```
Create a gist contains the files you given. You can also write the description using `--desc`.

### update
```
gistor --update [gist-id] -e
```
Use `-e` will open your default editor and load your file automatically. Edit it and save it then gistor will update your file to gist.

### delete
```
gistor --remove [gist-id]
```
Delete the specific gist based on specific id.

### list
```
gistor --list
```
It will list your gist, including Id and description. (Id is necessary in following action)

### search
```
gistor --search [keyword]
```
Search gist by keyword. Cause Github did not provide search API, parse the serach page right now. It will return the first 10 results just as gist searching page. The display format will just like follow:
```
=====
Author - Gist Name
Gist link
-----
File Content
```

### folk
```
gistor --folk [gist-id]
```
Folk the target gist, also return the url of your folk gist.

### get
```
gistor --get [gist-url || gist-id] [--file FILENAME]
```
Download target gist to current location, gistor will use filename as default, but you can replace with a new filename, using `--file`.
