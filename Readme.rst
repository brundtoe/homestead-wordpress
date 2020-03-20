Opdateret 25. januar 2018
=========================

Migrering er foretaget fra Homestead Wordpress installation

Opdater wordpress 
-----------------
- login med wp.local/wp-admin 
   - user bent 
   - password (cDqU@uV9AaAi^JqSH

- opdater wordpress, themes og alle plugins

Migrering med duplicator
------------------------
- skriv usernavn og password ned

- lav en backup med duplicator
- download installer.php og zipfilen
- vagrant halt
- vagrant destroy
- vagrant up
- slet mappen sourcecode/wordpress
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
- nu kan der logges in med usernavn **bent** og pwd fra den gamle installation 
(cDqU@uV9AaAi^JqSH

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


