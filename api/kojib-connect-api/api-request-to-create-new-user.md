# API request to create new user

```php
<?php
$url = 'https://kojib.com/connect/';
$ch = curl_init($url);
$data = array(
    'key' => 'Kojib Connect Secret Key',//You will find this in Grupo Settings
    'do' => 'createuser',
    'name' => 'Full Name',
    'user' => 'username',
    'email' => 'user@email.com',
    'pass' => 'password',
    'avatar' => 'https://imageurlgoeshere',
    'cf_identifier' => 'customfieldvalue',//Check edit custom field area for custom field Identifier
    'role' => '3',
);
curl_setopt($ch, CURLOPT_POSTFIELDS, $data);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
$res = curl_exec($ch);
curl_close($ch);
$res = json_decode($res);
if ($res->result) {
    return $res->userid; //returns User ID (gr_users database table ID column)
} else {
    return $res->error;
}
?>
```
