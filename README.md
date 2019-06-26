# php-library-sqldb-session

```php
if (session_status() == PHP_SESSION_NONE) {
    ini_set('session.use_cookies', '0');
    session_set_save_handler((new \Sinevia\SqlDbSessionHandler($MYPDO, $MYTABLE)), true);
    session_id(strip_tags($_REQUEST['PHPSESSID'] ?? \Sinevia\UidUtils::humanUuid()));
    session_start(['use_only_cookies' => 0, 'use_trans_sid' => 1]);
}
```