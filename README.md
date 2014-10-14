HackThis
========
https://www.hackthis.co.uk

#Main
##Level 1
regarder le source de la page. dans la partie head, remarquer :
```html
<!-- username: in, password: out -->
```

##Level 2
regarder le source de la page. le formulaire contient les information dans des balises span de la couleur du fond d'écran
```html
<label for="user">Username:</label> <span style="color: #000000">resu</span>
<label for="user">Password:</label> <span style="color: #000000">ssap</span>
```
##Level 3
regarder le source de la page. Elle contient une fonction javascript permettant de valider les informations du formulaire
```javascript
$(function(){ $('.level-form').submit(function(e){ if(document.getElementById('user').value == 'heaven' && document.getElementById('pass').value == 'hell') { } else { e.preventDefault(); alert('Incorrect login') } })})
```
##Level 4
regarder le source de la page. le formulaire contient un champ caché :
```html
<input type="hidden" name="passwordfile" value="extras/ssap.xml">
```
regarder le contenu du fichier https://www.hackthis.co.uk/levels/extras/ssap.xml
##Level 5
regarder le source de la page. la saisie du mot de passe et sa vérification sont faite en javascript.
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
le source montre un champ caché dans le formulaire
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
##Level 5
##Level 6
##Level 7
