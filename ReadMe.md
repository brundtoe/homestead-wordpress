# HomeBox

I denne mappe findes definitionen af mine lokale HomesteadBoxe

ip adresser:
192.168.0.12 wordpress http://wp.local
192.168.0.14 php
192.168.0.15 javascript

## Wordpress
user brundtoe@outlook.dk
pwd  se KeePassXC

## Opdateret 2. marts 2021

bloggen itsupport.brundtoe.dk er slettet

## backup af wp.local

- vagrant up
- tag en backup med duplicator
- kopier backup til /wdmycloud/dokumenter/wordpress/wp-local/[wp-version]
- vagrant halt

## refresh af laravel/homestead

- tag som anført ovenfor en backup med duplicator
- vagrant destroy
- vagrant box prune

- https://github.com/laravel/homestead check versionsnummer
- cd laravel/Homebox/wordpress
- opdater composer.json med det nye versionsnummer
- composer update

- kopier backup til mappen sourcecode/wordpress
- vagrant up
- browser http://wp.local/installer.php


- vælg opret en ny database

- MySQL Server
  - host:       localhost
  - host port:  3306
  - Database:   wordpress
  - user:       homestead
  - password:   det sædvanlige for homestead

- Følg resten af dialogen 
- Login med user brundtoe@outlook.dk og password som for itsupport.brundtoe.dk

## Vigtigt: afslag på tredjepart cookies er aktiveret

**Tilbagekald må ikke aktiveres - så går instansen i stå**


