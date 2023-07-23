## ඕනිම_කෙනෙක්_Track_කරමු.

අපි මේක කරන්නෙ සම්පූර්ණයෙන්ම php programming language එක හරහා. මුලින්ම ඔයාලට host එකක් ඕනි free host එකක් හරි කමක් නෑ හදාගන්න
 --------------------------------------------------------------------------
අපි විස්තර ගන්න කලින් දිනයයි වෙලාවයි අරන් ඉමුකො එතකොට ලේසීනෙ හොයා ගන්න හැබැයි මේ ලංකාවේ වෙලාව නම් නෙවෙයි.

 $datetime = date("F j, Y, g:i a"); 

--------------------------------------------------------------------------

මුලින්ම බලමු track කරන්න ඕනි කෙනාගෙ #Devise_details ටිකක් ගන්න කෝඩ් එක,

$useragent = $_SERVER['HTTP_USER_AGENT'];

මේ කෝඩ් එක හරහා ඔයාට track කරන්න ඕනි කෙනාගෙ,
      * device name එක
      *operating system එක
      *browser එක 
      *browser එකේ වර්ගය ඇතුලු තවත් විස්තර කිහිපයක් ගන්න පුළුවන්.
--------------------------------------------------------------------------

ඊලගට අපි #screen_size එක ගමු. screen size එකේ වැදගත්කම කියන්න ඕනි නෑනෙ දන්නව ඇති කියලා හිතනවා 😉

session_start();
if(isset($_SESSION['screen_width']) AND isset($_SESSION['screen_height'])){
    $s= 'User resolution: ' . $_SESSION['screen_width'] . 'x' . $_SESSION['screen_height'];
    echo $s;
    
} else if(isset($_REQUEST['width']) AND isset($_REQUEST['height'])) {
    $_SESSION['screen_width'] = $_REQUEST['width'];
    $_SESSION['screen_height'] = $_REQUEST['height'];
    header('Location: ' . $_SERVER['PHP_SELF']);
} else {
    echo '<script type="text/javascript">window.location = "' . $_SERVER['PHP_SELF'] . '?width="+screen.width+"&height="+screen.height;</script>';
}

--------------------------------------------------------------------------
ඊලගට අපි track කරන්න ඕනි කෙනාගෙ #real_IP එක ගමු  

function shapeSpace_get_ip() {
 
 $address = $_SERVER['REMOTE_ADDR'];
 
 if (array_key_exists('HTTP_X_FORWARDED_FOR', $_SERVER) && !empty($_SERVER['HTTP_X_FORWARDED_FOR'])) {
 
 $address = $_SERVER['HTTP_X_FORWARDED_FOR'];
 
 } elseif (array_key_exists('HTTP_CLIENT_IP', $_SERVER) && !empty($_SERVER['HTTP_CLIENT_IP'])) {
 
 $address = $_SERVER['HTTP_CLIENT_IP'];
 
 }
 
 if (strpos($address, ",") > 0) {
 
 $ips = explode(",", $address);
 
 $address = trim($ips[0]);
 
 }
 
 return $address;
 
}
$ip=shapeSpace_get_ip();
echo $ip;

--------------------------------------------------------------------------
හරි අපි දැන් ip එකේ #country එක ගමු. මේක අපි කරන්නෙ 3rd party විදියට. 

$ip=your ip;
$ipdat = @json_decode(file_get_contents("http://www.geoplugin.net/json.gp?ip=" . $ip));
$contry= $ipdat->geoplugin_countryName; 

--------------------------------------------------------------------------
දැන් අපි මේව සේව් කරගන්නෙ කොහොමද ?
අපිට ෆයිල් එකකට සේව් කරගන්නත් පුළුවන් මේල් එකකට ගන්නත් පුළුවන් . මම කරන්න හදන්නෙ ෆයිල් එකකට සේව් කරගන්න 

$file = fopen("log","a");
echo fwrite($file,"\n");
echo fwrite($file,"IP Address>>>");
echo fwrite($file,"\n");
echo fwrite($file,$ipa);
echo fwrite($file,"\n");
echo fwrite($file,"IP>>> ");
echo fwrite($file,"\n");
echo fwrite($file,$ip);
echo fwrite($file,"\n");
echo fwrite($file,"Date & Time>>> ");
echo fwrite($file,"\n");
echo fwrite($file,$datetime);
echo fwrite($file,"\n");
echo fwrite($file,"UserAgent>>> ");
echo fwrite($file,"\n");
echo fwrite($file,$useragent);
echo fwrite($file,"\n");
echo fwrite($file,"country>>> ");
echo fwrite($file,"\n");
echo fwrite($file,$contry);
echo fwrite($file,"\n");
echo fwrite($file,"\n");
--------------------------------------------------------------------------

හරි අපි දැන් උඩ කියපු හැම එකක්ම එකතු කරලා එක script එකක් ලියමු.

<?php
$datetime = date("F j, Y, g:i a");
$useragent = $_SERVER['HTTP_USER_AGENT'];
session_start();
if(isset($_SESSION['screen_width']) AND isset($_SESSION['screen_height'])){
    $s= 'User resolution: ' . $_SESSION['screen_width'] . 'x' . $_SESSION['screen_height'];
    $file = fopen("log","a");

    echo fwrite($file,"\n");
    echo fwrite($file,"\n");
    echo fwrite($file,$s);
    
} else if(isset($_REQUEST['width']) AND isset($_REQUEST['height'])) {
    $_SESSION['screen_width'] = $_REQUEST['width'];
    $_SESSION['screen_height'] = $_REQUEST['height'];
    header('Location: ' . $_SERVER['PHP_SELF']);
} else {
    echo '<script type="text/javascript">window.location = "' . $_SERVER['PHP_SELF'] . '?width="+screen.width+"&height="+screen.height;</script>';
}
function shapeSpace_get_ip() {
 
 $address = $_SERVER['REMOTE_ADDR'];
 
 if (array_key_exists('HTTP_X_FORWARDED_FOR', $_SERVER) && !empty($_SERVER['HTTP_X_FORWARDED_FOR'])) {
 
 $address = $_SERVER['HTTP_X_FORWARDED_FOR'];
 
 } elseif (array_key_exists('HTTP_CLIENT_IP', $_SERVER) && !empty($_SERVER['HTTP_CLIENT_IP'])) {
 
 $address = $_SERVER['HTTP_CLIENT_IP'];
 
 }
 
 if (strpos($address, ",") > 0) {
 
 $ips = explode(",", $address);
 
 $address = trim($ips[0]);
 
 }
 
 return $address;
 
}
$ip=shapeSpace_get_ip();
echo $ip;
$ipdat = @json_decode(file_get_contents("http://www.geoplugin.net/json.gp?ip=" . $ip));
$contry= $ipdat->geoplugin_countryName; 

$file = fopen("log","a");
echo fwrite($file,"\n");
echo fwrite($file,"IP Address>>>");
echo fwrite($file,"\n");
echo fwrite($file,$ipa);
echo fwrite($file,"\n");
echo fwrite($file,"IP>>> ");
echo fwrite($file,"\n");
echo fwrite($file,$ip);
echo fwrite($file,"\n");
echo fwrite($file,"Date & Time>>> ");
echo fwrite($file,"\n");
echo fwrite($file,$datetime);
echo fwrite($file,"\n");
echo fwrite($file,"UserAgent>>> ");
echo fwrite($file,"\n");
echo fwrite($file,$useragent);
echo fwrite($file,"\n");
echo fwrite($file,"country>>> ");
echo fwrite($file,"\n");
echo fwrite($file,$contry);
echo fwrite($file,"\n");
echo fwrite($file,"\n");
?>

හරි දැන් මේ script එක ඔයාගෙ host එකේ file එකක් හදලා සේව් කරගන්න මතක ඇතුව ෆයිල් extention එක .php දෙන්න. ඊට පස්සෙ ඒකෙ ලින්ක් එක ඔයාගෙ victim ට යවන්න. victim ලින්ක් එක open කරපු ගමන් log කියලා ෆයිල් එකක් හැදිලා ඔයාට ඕන විස්තර ටික සේව් වෙයි. 
උඩ script එකේ 
$file = fopen("log","a"); 👈 මෙන්න මෙතන log වෙනුවට කැමති නමක් දෙන්න ඒ නමින් ෆයිල් එකක් හැදිලා විස්තර ටික සේව් වෙනවා.
