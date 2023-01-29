# API request to create a new group

```php
<?php
$url = 'https://kojib.com/connect/';
$ch = curl_init($url);
$datas = array(
    'key' => 'Kojib Connect Secret Key',
    'do' => 'creategroup',
    'name' => 'Group Name',
    'password' => 0, //Specify password for password protected group
    'visibility' => true, //Specify false for Secret Group
    'sendpermission' => 0, // Specify adminonly for granting send messages permission only to Group Admins & Moderators
    'unleavable' => 0,// Specify unleavable for creating Group which once joined cannot be unjoined or left
);
curl_setopt($ch, CURLOPT_POSTFIELDS, $data);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
$res = curl_exec($ch);
curl_close($ch);
$res = json_decode($res);
if ($res->result) {
    return $res->groupid; //Returns Group ID - gr_options database table
} else {
    return $res->error;
}
?>
```
