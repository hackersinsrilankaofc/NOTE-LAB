-👨‍💻Nmap(Network Mapper)-
#Nmap

[+] Developed By:- Gordon Lyon (yodor Vaskovich)

[+] Initial Release :- September 1997 (24 years Ago)

[+] Written In:- Python, C, C++, Lua

[+] Type:- Network Security

[+] Website:- nmap.org


මම Kali Linux ගැන ලිව්ව post එකේ කිව්වනෙ Common use කරන වැදගත් tools කිහිපයක් ගැන කතා කරනවා කියලා...😇
ඉතින් අද අපි ඉතාම සරලව කතා කරමු Nmap(Network Mapper) ගැන...🔑🕵️‍♂️

මොකද්ද මේ Nmap කියන්නෙ ?
            Nmap කියන්නෙ free and Open-source , Network Scanning Tool එකක්...
            මේකෙන් අපිට පුලුවන් Systems වලට අදාල Networks වල Information Gathering කරන්න, එහෙමත් නැත්තන් තොරතුරු එක් රැස් කරන්න...
            ප්‍රධාන වශයෙන් port Scanning සඳහා Nmap use කරනවා...
            Computer Network එකකට Packets Send කර, නැවත පැමිණෙන Response Analyzing කර ඒවා තුල Run වෙන Services, ඒවගෙ Versions, System එකේ os එක , Ports Open ද Close ද යනවග ඇතුලු කරුනු විශාල ගණනක් අපිට Nmap හරහා හොයාගන්න පුලුවන්...


Nmap වල CLI version එකක් වගේම GUI එකක්ද ඇත. GUI version එක Zenmap ලෙස හඳුන්වනවා. ඔයාට windows වල වගේ Run කරන්න ඕනිනම් මේ GUI version එක nmap offical web එකෙන්ම download කරගන්න පුලුවන්... 
            
වැඩි විස්තර Google එකේ හොයන්න. 😋

 Nmap use කරන්නත් Command තියෙනවා...
 ඔයා CLI එකක(Kali Linux එකට අදාලව) Nmap use කරනවනම්,
nmap -h ලෙස  type කර Enter කළ පසු Nmap Use කරන්න අවශ්‍ය Commands සහ භාවිතා කරන විදිහ(Options) ඔයාටම බලාගන්න පුලුවන්...

 nmap [Scan Type(s)] [Options] {target specification} 

මම Nmap එකේ Options කිහිපයක් ඉතා සරලව කියන්නම්.
(Networking ගැන Basic knowledge එකවත් අරගෙන ඉන්න Nmap use කරන්න කලින්.😋)

 ____________________________________________________________
-iL <inputfilename>: Input from list of hosts/networks
මේ Command එකෙන් Host or Networks, List එකක් file එකක් විදිහට input කරලා scan කරගන්න පුලුවන්
Ex:
    nmap -iL hosts.txt (මෙහි host.txt file එකට hosts list එකක් ලෙස ලබා දෙන්න.) 
____________________________________________________________
 ____________________________________________________________
-iR <num hosts>: Choose random targets
මේ තුලින් internet එක තුලින් Randomly(අහඹු ලෙස) තෝරාගත් Hosts, ඔබ ලබා දෙන ගනනක් Scan කරයි.
Ex: 
    nmap -iR 5 (මෙහිදී hosts 5ක් Scan කරයි.) ____________________________________________________________

[අනෙකුත් Options Google or Youtube භාවිතයෙන් අධ්‍යනය කරන්න. Networking දැනුම අවශ්‍ය වේ.
Self Study කරන්න.]😎

