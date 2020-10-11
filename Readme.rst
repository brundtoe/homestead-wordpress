Opdateret 11. oktober 2020
==========================

Opgradering fra wp 5.3 til 5.5.1 foretaget jf

https://wordpress.org/support/article/upgrading-wordpress-extended-instructions/

Bruger  jackie
pwd     $YsEDG(Ii0R2Cq8E^X10X6Z3

Migrering er foretaget fra Homestead Wordpress installation

Opdater wordpress 
-----------------
- login med wp.local/wp-admin 
   - user jackie
   - password $YsEDG(Ii0R2Cq8E^X10X6Z3

- opdater wordpress, themes og alle plugins

Migrering med duplicator
------------------------

Backup af en instans

- skriv usernavn og password ned

- lav en backup med duplicator
- download installer.php og zipfilen
- vagrant halt
- vagrant destroy
- vagrant up
- slet mappen sourcecode/wordpress

Opret en ny instans

- opret den nye mappe spurcecode/wordpress
- kopier backup filerne installer og zip filen til mappen som skal være wordpress roden
- roden er sourcecode/wordpress (er også mappet nedenfor i Homestead/yaml)
- vagrant up
- start browseren med http://wp.local/installer.php
- følg dialogen
  - host wordpress
  - database wordpress
  - user homestead
  - pwd secret
- gå til wp.local/wp-admin
- nu kan der logges in med usernavn **jackie** og pwd fra den gamle installation 
$YsEDG(Ii0R2Cq8E^X10X6Z3

- Der kan under installationen efter indlæsning af databasen under options oprettes en ny admin bruger

Den anvendte homestead.yaml
---------------------------

ip: 192.168.10.12
memory: 2048
cpus: 1
provider: virtualbox
authorize: ~/.ssh/id_rsa.pub
keys:
    - ~/.ssh/id_rsa

folders:
    - map: /home/projects/sourcecode/wordpress
      to: /home/vagrant/code

sites:
    - map: wp.local
      to: /home/vagrant/code
      php: "7.2"

databases:
    - wordpress

name: wordpress

hostname: wordpress

----------------------------


