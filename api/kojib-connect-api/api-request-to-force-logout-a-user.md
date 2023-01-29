# API request to force logout a user

```php
<?php
$url = 'https://kojib.com/connect/';
$ch = curl_init($url);
$data = array(
    'key' => 'Kojib Connect Secret Key',
    'do' => 'logout',
    'user' => 'user@email.com',//username or email address
);
curl_setopt($ch, CURLOPT_POSTFIELDS, $data);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
$res = curl_exec($ch);
curl_close($ch);
$res = json_decode($res);
if ($res->result) {
} else {
    return $res->error;
}
?>
```
