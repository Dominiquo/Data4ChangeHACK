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

# `GET`  /list_folders
Parameters:
 - None

Returns: 
 - JSON: ```{'data': [Folder1, Folder2, .., FolderN]}```

# `GET` /list_subfolders
Parameters:
 - fields: `{'folder': '<Folder1>'}`

Returns: 
 - JSON: ```{'data': [SubFolder1, SubFolder2, .., SubFolderN]}```

# `GET` /get_files
Parameters:
 - fields: `{'folder': '<Folder1>'}`

Returns: 
 - JSON: ```{'data': [SubFolder1, SubFolder2, .., SubFolderN]}```