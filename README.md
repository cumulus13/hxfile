# HXfile
--------------------
    
Hxfile Unofficial API
    
    
## requirements
-------------------
- pip    
    - unidecode
    - configset
    - parserheader
    - requests
    - bs4
    - bitmath
    - clipboard

- for development:
    - pydebuger
    - jsoncolor

- for notification:
    - xnotify
    
## usage
----------------
    
all functions same as on [api documentation](https://hxfile.docs.apiary.io/) plus downloader `download1`, `download2`, `generate`

```bash
usage: hxfile [-h] [-d [DOWNLOAD ...]] [-m METHOD] [-p DOWNLOAD_PATH] [-n SAVE_AS] [-i INFO] [-I] [-S ACCOUNT_STAT] [-u UPLOAD]
              [-l] [-L LIST_FOLDER] [-r RENAME_FILE RENAME_FILE] [-R RENAME_FOLDER RENAME_FOLDER] [-c CLONE] [-M MOVE MOVE]
              [-C MKDIR MKDIR] [-sd] [--api-key API_KEY] [--api-key-temp API_KEY_TEMP] [-g [GENERATE ...]] [--clip]

optional arguments:
  -h, --help            show this help message and exit
  -d [DOWNLOAD ...], --download [DOWNLOAD ...]
                        Download by given url or id/filecode, you can change use method "1" or "2" with -m/--method, default
                        method is "2"
  -m METHOD, --method METHOD
                        Download/Generate method: "2" download/generate url without API_KEY needed, but you must still input
                        API_KEY to config file "hxfile.ini" for other function requirement, "1" download/generate with API_KEY
                        flow check your file --> if not exists --> clone --> generate direct_link
  -p DOWNLOAD_PATH, --download-path DOWNLOAD_PATH
                        Save download action file to directory
  -n SAVE_AS, --save-as SAVE_AS
                        Download save as
  -i INFO, --info INFO  Get File info
  -I, --account-info    Get Account Info
  -S ACCOUNT_STAT, --account-stat ACCOUNT_STAT
                        Get Account Info Statistics
  -u UPLOAD, --upload UPLOAD
                        Upload file
  -l, --list-file       List all files
  -L LIST_FOLDER, --list-folder LIST_FOLDER
                        List all folder
  -r RENAME_FILE RENAME_FILE, --rename-file RENAME_FILE RENAME_FILE
                        Rename file
  -R RENAME_FOLDER RENAME_FOLDER, --rename-folder RENAME_FOLDER RENAME_FOLDER
                        Rename folder
  -c CLONE, --clone CLONE
                        Clone/Copy file from public link as youre file
  -M MOVE MOVE, --move MOVE MOVE
                        Move file to folder
  -C MKDIR MKDIR, --mkdir MKDIR MKDIR
                        Create new Folder
  -sd, --show-deleted   Show files delete along for x days
  --api-key API_KEY     set API_KEY
  --api-key-temp API_KEY_TEMP
                        set API_KEY as temporary key
  -g [GENERATE ...], --generate [GENERATE ...]
                        Generate link/id as direct download link
  --clip                Copy direct download url to clipboard
```
    
* example:
```bash
    hxfile --api-key-temp 4534wit9lvakdohxjdv6 -i m13uao5l10rt
    hxfile --api-key-temp 4534wit9lvakdohxjdv6 -i https://hxfile.co/m13uao5l10rt
```
```python
>>> from hxfile import Hxfile
>>> id = "m13uao5l10rt" # or https://hxfile.co/m13uao5l10rt
>>> Hxfile.file_info(id) # or
>>> h = Hxfile()
>>> h.file_info(id) # or
>>> Hxfile().file_info(id)
>>> # direct download without API_KEY
>>> Hxfile.download1(id)
>>> # direct download with API_KEY requirement
>>> Hxfile.download2(id)
>>> #generate only, not download
>>> Hxfile.generate(id)
```

downloader support 'idm' (windows), 'wget/aria2c/persepoli' (linux), if error then downloader use `pywget` (all)
    
## author
---------
[cumulus13](mailto:cumulus13@gmail.com)
    