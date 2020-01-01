Include file manager in another script. Just define FM_EMBED and other necessary constants.

```php
class SomeController
{
    public function actionIndex()
    {
        define('FM_EMBED', true);
        define('FM_SELF_URL', UrlHelper::currentUrl()); // must be set if URL to manager not equal PHP_SELF
        require 'path/to/tinyfilemanager.php';
    }
}
```
OR
```php
define('FM_EMBED', true);
define('FM_SELF_URL', $_SERVER['PHP_SELF']);
require 'path/tinyfilemanager.php';
```