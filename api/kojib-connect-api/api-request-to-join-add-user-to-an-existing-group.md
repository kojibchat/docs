# API request to join/add user to an existing Group

```php
<?php
$url = 'https://kojib.com/connect/';
$ch = curl_init($url);
$data = array(
    'key' => 'kojib Connect Secret Key',
    'do' => 'joingroup',
    'groupid' => 'groupid',//Specify the groupid (You will find group id in gr_options table id column)
    'userid' => 'user@email.com',
    'role' => 0,
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
