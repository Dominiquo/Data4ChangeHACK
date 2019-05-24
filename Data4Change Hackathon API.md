# Data4Change Hackathon API
##### May 25 and 26, 2019

This is a simple REST API to get relevant Township development indicator information for this hackathon. This API was built according to the taxonomy from the data [shared here](https://drive.google.com/drive/folders/1eLy31lg2H_0LRys4_I94bGGl75EKPtbC?fbclid=IwAR0Cgr2D6bvejfWGNHxnzLw2cKeRi6Zxn8p6rAuKdFpX169TFKHYhJ4HQgM) via Google Drive.

The files are sorted into folders and subfolders. Each subfolder contains several files. Here is an example of the first folder to the first leaves (files):
```
+-- 01_Development/
|    +-- Development/
        +-- NTL9218TS_20190514.csv
        +-- NTL9218TS_20190514.xlsx
        +-- ...etc
|    +-- Health/
        +-- ...etc
|    +-- Standard of Living/
        +-- ...etc        
```

Therefore, we have a clear tree structure. Each `folder` has `subfolders` and each `subfolder` has `files`.

### `folder`
- String indicating the available folder names

### `subfolder`
- String indicating the available subfolder names for a given folder 

### `file`
- `package_name`: 
- `format`: 
- `url`:
- `filename`: 
- `folder_name`:
- `subfolder_name`:
- `id`:

# `GET`  /list_folders
Parameters:
 - None

Returns: 
 - JSON: ```{'folders': [Folder1, Folder2, .., FolderN]}```

# `GET` /list_subfolders
Parameters:
 - fields: `{'folder': '<Folder1 String>'}`

Returns: 
 - JSON: ```{'data': [SubFolder1, SubFolder2, .., SubFolderN]}```

# `GET` /get_files
Parameters:
 - `folder`: zero to multiple folder strings seperated by commas (NO spaces)
 - `subfolder`: zero to multiple subfolder strings seperated by commas (NO spaces)
 - `format`: zero or more format types serarated by commas (may be one of listed string values: `['csv', 'xlsx', 'txt', 'pdf', 'jpg']`)

Returns: 
JSON: 
```
 {'files': [file1, File1, ..., FileN],
     'file_count': int_val
 }
 ```
 
 # `GET` /get_file_by_id
 Parameters:
 - `id`: file id string that can be found when calling files via `get_files`
 Returns:
- single `file` object
