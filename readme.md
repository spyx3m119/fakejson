<h2>Serving JSON data to test cURL functionality.</h2>

Use this server url: https://my-json-server.typicode.com/spyx3m119/fakejson

Example:
<code>
$qry_str = "?method=find_reservation";

$ch = curl_init();

curl_setopt($ch, CURLOPT_HEADER, 0);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
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
$student_data = $data['register']['0']; </code>
