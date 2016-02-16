# Git flow

## Vytvoření lokálního projektu a napojení na vzdálený repositář 

V adresáři, kde bude náš web:

(git clone (níže) uděláte to samé:)
1. git init # začne projekt
2. git remote add origin git@github.com:TomasVotruba/git-demo.git


## Fork
 
1. Vaše vlastní verze původního repositáře
2. git clone https://github.com/<vase-jmeno>/git-demo.git
    liší se v tom, že tenhle už existuje
    defaultně se jmenuje "origin" a v 99 % se nebude jmenovat jinak
    kdyby tě to náhodou zajímalo, tak stačí zavolat: "git remote"
    ten vypíše všechny remote názvy
    
3. Uprav soubor README.md
4. Přidej ho:
    git add README.md

    # můžeš i více souborů či složek
    git add README.md tests.yml
    git add /src /tests
    
    # nebo úplně vše
    git add .
    
    4.1: více změnených souborů, ale chceme jen nějaké
        - 10 souborů máš změněných
        - 3 chceš dát do commitu
        - git add .
    
5. Vytvoříme commit nad přidanými soubory/složkami:
    git commit -m "added title"
    
6. Pushenem online všechny neodeslané commity:
    git push origin master
    # git push <kam-někde> <odkud-lokalně>

7. Pak připravíme Pull-request do hlavního repositáře
8. Následuje Code review a pak merge
    8.1. Bez konfliktů - tlačítkem :)
    8.2. S konflikty
    
    
 ## Práce s větvemi
  
 Nikdy byste neměli dělat na "master", ale na vlastní větvi.
 
 1. git checkout -B <nazev-vetve>
 2. commity do nové větvě


## Vrácení změn do původního stabu

1. git checkout Readme.md

## Přepínání mezi větvemi

1. git checkout master
2. git checkout moje-vetev


## Přidej všechno a commitni

git commit -am "vše změněno :)"


## Synchronizace po mergování (~= svn update)

1. git checkout master
2. git pull origin master # stáhnu všechny změny
3. git checkout moje-vetev
4. moje-vetev musí mít commitnuté změny

## Synchronizace s hlavní větví

1. přidat si hlavní větev mezi svá připojení: git remote add upstream https://github.com/TomasVotruba/git-demo.git
2. git fetch upstream
3. git merge upstream/master => zkouší mergovat, pokud vznikne konflikt, je potřeba ho pořešit

## PRO VLASTNÍKY RŮŽOVÝCH TRIČEK S JEDNOROŽCEM

```
                 .-.   _                __
                `  )`'-,`\        .-''``.-'
   _.-''-.      _.'       `'--._.' ,-'  /
   `\    _`'--'`                      .'
     '._ _`-       .--.   .--.      (`
        `.'       /    '.'    \      '.
       .'         \  0  |  0  /        '.
      /   _        '._.---._.'      _    \
      /    `'-.      (     )    .-'`     \
      / .---'_.   .   `-,-`  .  ._'---.  \
      |   -'`   .       |      .  `'-    |
      /_       .   '   /;\  '    .     ,_\
        '-.     '-..-`( ' )`-..-'     /
           '._         '-'         _.'
              '-..,__       __,..-'
                     `'---'`
