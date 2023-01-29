# API request to edit existing user

<pre class="language-php"><code class="lang-php"><strong>&#x3C;?php
</strong><strong>$url = 'https://kojib.com/connect/';
</strong>$ch = curl_init($url);
$data = array(
    'key' => 'kojib Connect Secret Key',
    'do' => 'edituser',
    'changename' => 'Change Name',
    'changeusername' => 'Change Username',
    'changeemail' => 'changeemail@esmail.com',
    'changepass' => 'changepassword',
    'changeavatar' => 'https://imageurlgoeshere',
    'changerole' => '3',
    'cf_identifier' => 'customfieldvalue',//Check edit custom field area for custom field Identifier
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
</code></pre>
