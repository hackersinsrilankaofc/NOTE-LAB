## Admin Log In Bypass.

authentication  නැතුව වෙබ් අඩවියකට ඇතුල් වෙන එක Web Application සමහරුන්ගෙ හීනයක්. අද මෙ ගෙනාවේ ඒ හීනෙට තවත් අත්වැලක්. මේක Wordpress Site වලට සීමා වෙච්ච එකක් නම් නෙවෙයි. ඒ්ත් ලෝකප්‍රසිද්ධ CMS එක්ක නිසයි Wordpress Target කරන්නෙ.👌😋☺👉

සරලවම කිව්වොත් මේකෙදි වෙන්නෙ Security දැම්ම Page එකට යද්දි  Cookie header තුල Session Token තියනවද පරීක්ෂා කරලා  ඒවා  නැත්තම්  Login Page එකට Redirect වෙනවා . මේකට පාවිච්චි වෙන්නෙ 302 HTTP Response එකයි. ඒ විදියට Redirect වීම නවත්තලා Protected Page එකට ඇතුල් වෙන්න අපිට පුලුවන්. 🤞😁

Exploiting Improper Redirection in  PHP Web Applications 🖖

මුලින්ම FireFox Browser එක Open කරගෙන NoRedirect කියන Addon එක Download කරලා Install කරගන්න.(Old Versions 47.0)

ඊට පස්සෙ Google Dork පාවිච්චි කරලා Attack කරන්න SIte එකක් හොයාගන්න.     
         ex- inurl:wp-admin/login.php site: in

දැන් URL එකකට යන්න. ඒක Copy කරගන්න. 

https://www. example .com/wp-admin/login.php

දැන් Right ALT Button එක Press කරලා Tool bar එක Open වෙනවා. එතනදි Tool වලට ගිහින් NoRedirect කියන තැන Option එක දෙන්න.

හරි දැන් Copy කරපු Url එක Add කරන්න.

අවසාන වැ‌‌ඩේ දැන් තියෙන්නෙ. අර URL එක අගට තියන login.php කියන කොටස අයින් කරලා Enter කරන්න.. දැන් වැඩේ හරි..


Recommended solutions
'302' HTTp response එකේ url එකට hyperlink එකක් සමග Short hypertext note එකක් ඇතුල් කරන්න...
PHP Script Execute වීම Redirection Line එකෙන් අවසාන කරන්න..

