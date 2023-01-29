# API request to login or generate login link

```php
<?php
$url = 'https://kojib.com/connect/';
$ch = curl_init($url);
$data = array(
    'key' => 'Kojib Connect Secret Key',
    'do' => 'login',
    'user' => 'user@email.com',//username or email address
    'redirect' => '',//You can specify URL to load after login (optional)
);
curl_setopt($ch, CURLOPT_POSTFIELDS, $data);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
$res = curl_exec($ch);
curl_close($ch);
$res = json_decode($res);
if ($res->result) {
    return $res->loginlink; //Login Link - Visiting this URL will auto login user specified
} else {
    return $res->error;
}
?>
```
