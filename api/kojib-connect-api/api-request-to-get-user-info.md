# API request to get User info

```php
<?php
$url = 'https://kojib.com/connect/';
$ch = curl_init($url);
$data = array(
    'key' => 'kojib Connect Secret Key',
    'do' => 'getinfo',
    'user' => 'user@email.com',//username or email address
);
curl_setopt($ch, CURLOPT_POSTFIELDS, $data);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
$res = curl_exec($ch);
curl_close($ch);
$res = json_decode($res);
if ($res->result) {
    return $res; //returns user information
} else {
    return $res->error;
}
?>
```
