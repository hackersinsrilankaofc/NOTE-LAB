## HTTP


hypertext transfer protocol (http) 

protocol කියන්නෙ electronic device අතර සන්නිවේදනය කිරීමට සැකසූ සම්මත නීති මාලාවක්. 

එතකොට මේ http කියන්නෙ server එකයි clint එකයි අතර සන්නිවේදනය සක්‍රීය කරන්න හදපු protocol එකක්. clint ගෙන් server එකට යවන request (ඉල්ලීම්) ඒ වෙත යැවීම සහ server එකෙන් clint වෙත එන response (ප්‍රතිචාර) clint වෙත යැවීමත් මේ protocol එකේ වගකීමක්. 

server = සේවාව ලබා දෙන්නා
clint    = සේවාව ලබා ගන්නා

මෙහෙම කිව්වට ගොඩක් අයට නොතේරෙන්න ඇති ඒ නිසා අපි උදාහරණයක් ගමු. 

හිතන්න ඔයා ඔයාගෙ browser එකට ගිහින් url එකක් type කරනවා www.example.com කියලා. එතකොට මෙතනදි clint තමයි ඔයාගෙ browser එක එතකොට example.com කියන site එක තමයි server එක. හරි දැන් ඔයාගෙ ඉල්ලීම http හරහා යවලා බලනවා example.com කියලා එකක් තියෙනවාද තියෙනවා නම් ඔයාට ඒක බලන්න අවසර තියෙනවාද කියලා. එහෙම අවසර තියෙනවා නම් ඔයාට request එකක් එවනවා 200 කියලා. මේ request වලට කියන්නෙ #http_request කියලා. 200 කියන්නෙ ok කියන එක ඒ කියන්නෙ example.com එක ඔයාට දැන් බලන්න පුළුවන්. එහෙම site එකක් නැත්තන් ඔයාට එවන්නෙ 404 කියන http request එක. ඒ කියන්නෙ not found එහෙම එකක් හොයන්න නෑ. මේ වගේ http request ගණනාවක් තියෙනවා.
403 = fobhidden
400 = bad request 

හරි ඊලගට අපි කතා කරමු http method ගැන.

server එකක තියෙන data ගන්න හරි clint එකෙන් data server එකට යවන්න හරි පාවිච්චි කරන්නෙ http methods

http methods
    ~GET
    ~POST
    ~PUT
    ~HEAD
    ~DELETE
    ~PATCH
    ~OPTION

අපි ඔතනින් ප්‍රධානම method දෙකක්වන GET සහ POST method ගැන කතා කරමු.

#GET_Method

මේක පාවිච්චි කරන්නෙ නිශ්චිත දත්තයක් ලබා ගන්න. username , password වගේ සංවේදී දත්ත එක්ක වැඩ කරන්න මේ method එක ආරක්ෂිත නෑ. 

හිතන්න ඔයා වෙබ් page එකකට යනවා www.example.com/name.php කියලා

මේකෙ input field එකක් තියෙනවා ඔයාගෙ නම දෙන්න. 

<form action='#' method='get'>
       <input type='text' name='uname'>
</form>

මේ input field එකේ නම uname action එක වෙන්නෙ මේ පේජ් එකෙන්මයි. action එක එහෙමත් නැත්නම් ක්‍රියාව තමයි අපේ නම අරගෙන නමේ තියෙන characters ගාන පෙන්නවන එක. මම Griffin කියලා නම දුන්නොත් 7 කියලා output එනවා වගේම www.example.com/name.php?uname=Griffin කියලා වෙනස් වෙලා තියෙනවා බලන්න පුළුවන්. ඉතින් අපිට පුළුවන් input field එකක් නැතුව උනත් url එකේ අගට ?uname= කියලා ගහලා අන්තිමට කැමති නමක් දාලා output එක ගන්න. හැබැයි අපි input name එක දැනගන්න ඕනි. 

name සහ age කියලා input 2ක් ගන්නවා නම් url එක වෙනස් වෙන්නෙ ?uname=&age= 
' = ' ලකුණට ඉදිරියෙන් value එක දෙන්න තියෙන්නෙ.

ඉතින් මේක ඇයි ආරක්ෂිත නෑ කියන්නෙ.

*අපි දෙන දත්ත url එකේ පෙන්නවා.
*මේවා browser history වල හිටිනවා.
*catch වල තැම්පත් වෙනවා. 

ඒ නිසා මේ ක්‍රමයෙන් සංවේදී දත්ත ලබා දෙන්න හොද නෑ. 

#POST_Method

දත්ත ලබා දෙන්න තමයි මේක පාවිච්චි කරන්නෙ. සංවේදී දත්ත ලබා දෙන්න මේ ක්‍රමය ආරක්ශිතයි. මොකද මේ දත්ත ලබා දෙන්න පුළුවන් html form එකක් හරහා 

<?php
$user=$_POST['uname'];
$pass=$_POST['pass'];
echo "$user\n$pass";
?>

උඩ script එක තියෙන page එකට data input කරනවා නම් අපිට url එකෙන් data input කරන්න බෑ. get method එකෙන් වගේ මේකට html form එකක් හදාගන්න ඕනි. උඩ script එක තියෙන url එක www.example.com/post.php කියලා හිතන්න. 

<form action='https://www.example.com/post.php' method='post'>
     <input type='text' name='uname'>
     <input type='text' name='pass'>
</form>

මේ විදියට html form එකක් හරහා post method එකෙන් data input කරන්න පුළුවන්. 
මෙතනදි html form එක තියෙන page එකයි post.php page එකයි එකම සයිට් එකේ තියෙනවා නම් form action එකට post.php කියල දැන්මම ඇති. අපි වෙනම එකක් හදලා කරනව නම් උඩ විදියට.

මේකෙදි history වලට catch වලට අහුවෙන්නෙ නෑ ඉතින් මේ ක්‍රමය ආරක්ශිතයි.


