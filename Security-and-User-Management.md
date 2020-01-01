# Security and User Management
Since the TinyFileManager is able to manipulate files on your server, it is necessary to secure safely your application.

## Configuration
Default username/password: 
* admin/admin@123 
* user/12345

**Warning**: Please set your own username and password in `$auth_users` before use. password is encrypted with password_hash(). to generate new password hash here

To enable/disable authentication set `$use_auth` to `true` or `false`.
```php
// Auth with login/password 
// set true/false to enable/disable it
// Is independent from IP white- and blacklisting
$use_auth = true;

// Login user name and password
// Users: array('Username' => 'Password', 'Username2' => 'Password2', ...)
// Generate secure password hash - https://tinyfilemanager.github.io/docs/pwd.html
$auth_users = array(
    'admin' => '$2y$10$/K.hjNr84lLNDt8fTXjoI.DBp6PpeyoJ.mGwrrLuCZfAwfSAGqhOW', //admin@123
    'user' => '$2y$10$Fg6Dz8oH9fPoZ2jJan5tZuv6Z4Kp7avtQ9bDfrdRntXtPeiMAZyGO', //12345
    'guest' => '$2y$10$a.DMI5sRjAnvhb.8rFAXY.XPSEO/eatVb4qCMmTc2YcxTDKp9xMyC' //guest
);
```

## Password
 Password is encrypted with password_hash(). to generate new password hash [here](https://tinyfilemanager.github.io/docs/pwd.html)

If not able to generate password or facing any issue, than generate password using tinyfilemanager itsef on `tinyfilemanager > settings > Generate new password hash` or alternative password generator [here](http://www.passwordtool.hu/php5-password-hash-generator)

or you can use directly set password hash using `password_hash()` method
```php
$auth_users = array(
    'username' => password_hash('password here', PASSWORD_DEFAULT)
);
```

## Readonly users
Set user role as readonly permission and thay don't have permission to create, edit, delete and upload files
```php
// Readonly users 
// e.g. array('users', 'guest', ...)
$readonly_users = array(
    'user',
    'guest'
);
```

## User Specific Directories

Since users can upload, download, delete and change permissions on most files in the directories they have access to, it is often necessary to create an specific directories that is limited in which directories it can access. That way you can give an user access to one part of a Directory.

Limited access users can also be useful if you want to make it possible for someone to upload files, but you don’t necessarily want to give them access to the entire directory.

```php
// user specific directories
// array('Username' => 'Directory path', 'Username2' => 'Directory path', ...)
$directories_users = array(
    'user' => 'root/user-folder',
    'guest' => 'root/guest/temp'
);
```