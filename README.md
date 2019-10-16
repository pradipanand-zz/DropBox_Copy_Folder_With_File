# DropBox_Copy_Folder_With_File
There are various code present in world but some are working and some are not, and everywhere only showing files being copied not for folder. 

1. Crete a folder in dropbox and generate access token, follow https://blogs.dropbox.com/developers/2014/05/generate-an-access-token-for-your-own-account/
and https://www.dropbox.com/developers/apps

2. Code is given below for folder copy

import dropbox,os
access_token = "abcd"

main_path               = os.getcwd() + '/'
output_path             = main_path + 'output'

file_from = r'C:\\output\Sep_2019\abcd.xlsx'  #//local directory file path
file_to   = '/test/abcd.xlsx'                 #// dropbox path, if test folder is not there then it will create

def upload_file(file_from, file_to):
    dbx = dropbox.Dropbox(access_token)
    f = open(file_from, 'rb')
    dbx.files_upload(f.read(), file_to, mode=dropbox.files.WriteMode("overwrite"))

upload_file(file_from,file_to)

#Raise a question through issue if you have any
