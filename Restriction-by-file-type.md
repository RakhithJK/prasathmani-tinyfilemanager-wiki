There is ways to restrict upload regarding file extension with a logic similar to [Apache access control](http://httpd.apache.org/docs/2.2/howto/access.html).

* allowed upload extensions are listed as an array into `$allowed_upload_extensions` variable
* allowed create and rename file extensions are listed as an array into `$allowed_file_extensions` variable

```php
// Allowed file extensions for create and rename files
// e.g. 'txt,html,css,js'
$allowed_file_extensions = 'txt,html,js,css,scss';

// Allowed file extensions for upload files
// e.g. 'gif,png,jpg,html,txt'
$allowed_upload_extensions = 'jpg,jpeg,gif,txt,mp4';
```