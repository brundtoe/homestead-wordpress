# HomeBox

I denne mappe findes definitionen af mine lokale HomesteadBoxe

ip adresser:
192.168.0.12 wordpress http://wp.local
192.168.0.14 php
192.168.0.15 javascript

## Wordpress
user brundtoe@outlook.dk
pwd  se KeePassXC


## Opdateret 12. februar 2021

Sitet kører på en kopi af itsupport.brundtoe.dk wp version 5.6.1

- opdateret til laravel/homestead kører nu ubuntu 20.04
- composer er opdateret til version 2.0.9
- sudo apt update && sudo apt upgrade 
- snapshot initialized er uden wordpress

Hentede ny kopi fra itsupport med Duplicator


Vigtigt: afslag på tredjepart cookies er aktiveret

**Tilbagekald må ikke aktiveres - så går instansen i stå**


## Nu anvendes en kopi af itsupport.brundtoe.dk

Genskabelse af Vagrant instansen

Processen er som følger

- Med **Duplicator** laves en kopi på itsupport

  MySQL Server
  - host:       localhost
  - host port:  3306
  - Database:   wordpress
  - user:       homestead
  
Vagrant instansens Homestead.yaml indeholder de samme oplysninger

- Download de to filer
- Slet mappen sourcecode/wordpress
- Opret mappen sourcecode/wordpress
- kopier de to filer til mappen wordpress

- Start vagrant instansen Homebox/wordpress
- gå til wp.local/installer.php
- følg dialogen for importen
- database oplysninger som ovenfor
- url i indlæg transformeres under import automatisk til wp.login

Login med user brundtoe@outlook.dk og password som for itsupport.brundtoe.dk

