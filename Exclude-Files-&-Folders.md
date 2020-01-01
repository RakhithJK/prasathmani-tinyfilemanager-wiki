you can specify files or directories that you'd like to exclude from the listing using configuration, in case same name file/folder in multiple place also excluded.

```php
// Files and folders to excluded from listing
// e.g. array('myfile.html', 'personal-folder', '*.php', ...)
$exclude_items = array(
    'my-folder',
    'secret-files',
    'tinyfilemanger.php',
    '*.php',
    '*.js'
);
```