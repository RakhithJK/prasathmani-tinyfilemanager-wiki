## I get an error uploading some files
This is probably a file size upload limit issue. `MAX_UPLOAD_SIZE` config option allow you to set the file limit for transfer. But server settings (`upload_max_filesize` and `post_max_size` in php.ini) may overwrite this value. 

## File Permissions
refer https://serverfault.com/questions/962790/php-script-and-correct-permissions-for-user-to-change-everything