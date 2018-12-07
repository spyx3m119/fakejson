Serving JSON data to test cURL functionality.

Use this server url: https://my-json-server.typicode.com/spyx3m119/fakejson

Example:
<code>
<?php 

$qry_str = "?method=find_reservation";

$ch = curl_init();

curl_setopt($ch, CURLOPT_HEADER, 0);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
//curl_setopt($ch, CURLOPT_URL, 'https://caamarketing.issportals.com/wp-content/plugins/conklin-media-navistar/test-data.php' . $qry_str);
curl_setopt($ch, CURLOPT_URL, 'https://my-json-server.typicode.com/spyx3m119/fakejson/db');
curl_setopt($ch, CURLOPT_FOLLOWLOCATION, 1);
curl_setopt($ch, CURLOPT_VERBOSE, 0);
curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, false);
//curl_setopt($ch, CURLOPT_POSTFIELDS, $data);

$content = curl_exec($ch);
if (curl_error($ch)) {
    $error_msg = curl_error($ch);
}
curl_close($ch);

if (isset($error_msg)) {
    var_dump($error_msg);
}

$data = json_decode( $content, true ); 
$student_data = $data['register']['0']; 
//var_dump($student_data['last_name']);
?>
</code>
