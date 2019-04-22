Opdateret 25. januar 2018
=========================

Migrering er foretaget fra Homestead Wordpress installation

Migrering med duplicator
------------------------
- skriv usernavn og password ned

- lav en backup med duplicator
- lav det nye environment uden selve wordpress pakken
- kopier backup filerne installer og zip filen til mappen som skal være wordpress roden
- start browseren med http://wp.local/installer.php
- følg dialogen
- nu kan der logges in med usernavn **bent** og pwd fra den gamle installation (cDqU@uV9AaAi^JqSH

- Der kan under installationen efter indlæsning af daabasen under options oprettes en ny admin bruger

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
    - map: /home/bent/sourcecode/wordpress
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


