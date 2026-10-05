Git & Github
============
[TOC]

Git
https://git-scm.com/

Github
https://github.com/

Commands & Cheatsheet
git-cheat-sheet-education.pdf

(Microsoft) Video Tutorials
https://youtu.be/9uGS1ak_FGg?si=mQ_wK7Fq7j2mZ38Y
https://www.youtube.com/watch?v=8JJ101D3knE

Git è un prodotto open-surce e gratuito per il controllo di versione distribuito, creato da Linus Torvalds nel 2005, progettato per gestire qualsiasi codice progetto da piccole a grandi dimensioni con velocità ed efficienza. 

Sistema di controllo distribuito significa che ogni sviluppatore ha una copia completa del repository e di tutta la cronologia del codice sul proprio computer, consentendo ad ogni componente del team di lavorare in modo indipendente e di sincronizzare le modifiche con gli altri membri del team quando necessario.

Github invece è la piattaforma cloud più popolare per fare hosting di progetti Git, fornendo spazio per i repository, strumenti di collaborazione, gestione dei progetti e integrazione con altri servizi esterni. Github permette agli sviluppatori di condividere il proprio codice, collaborare con altri, gestire le versioni del software e contribuire a progetti open-source.

Le principali pratiche di gestione del codice includono:
- **Branching**: Utilizzo di branch per lo sviluppo di nuove funzionalità, correzioni di bug, e versioni stabili <br>
- **Commit**: Messaggi di commit chiari e descrittivi per tracciare le modifiche <br>
- **Pull Requests**: Revisione del codice tramite pull requests prima della fusione nei branch principali <br>
- **Versioning**: Utilizzo di tag per marcare le versioni rilasciate del progetto <br>
- **Documentazione**: Mantenimento di una documentazione aggiornata nel repository, inclusi README e CHANGELOG <br>
- **Issue Tracking**: Utilizzo del sistema di issue di GitHub per tracciare bug, richieste di funzionalità, e attività di sviluppo <br><br>


# Getting Started
Per iniziare a utilizzare Git e Github, è necessario installare Git sul proprio computer e creare un account su Github. Una volta configurato, è possibile creare un nuovo repository, clonarlo sul proprio computer, apportare modifiche al codice, eseguire commit delle modifiche e sincronizzarle con il repository remoto su Github. Inoltre, è possibile collaborare con altri sviluppatori tramite pull request, gestire le versioni del software e contribuire a progetti open-source.

```bash
# verifica se Git è installato
git --version

# creare un nuovo repository nella cartella corrente
git init

# mostra lo stato del repository e le modifiche non ancora committate
git status

# inserire un file nuovo nel repository 
touch index.html
git status
```

## Commit del codice
Il commit del codice è un'operazione fondamentale in Git, che consente di salvare le modifiche apportate al codice nel repository locale. Ogni commit rappresenta un'istantanea del progetto in un determinato momento e include un messaggio descrittivo che spiega le modifiche apportate. I commit consentono di tenere traccia della cronologia del progetto, facilitando il ripristino di versioni precedenti del codice e la collaborazione con altri sviluppatori.

```bash
# mostra lo stato del repository e le modifiche non ancora committate
git status

# aggiunge i file modificati all'area di staging in preparazione al commit
git add <file1> <file2> ...
git add .  # aggiunge tutti i file modificati

# crea un nuovo commit con un messaggio descrittivo
git commit -m "Descrizione delle modifiche"

# mostra la cronologia dei commit con un formato compatto
git log --oneline

# rimuove un file dal repository e dall'area di staging
git rm <nome-file>

# ripristina un file modificato al suo stato precedente
git checkout -- <nome-file>
```

## Gestione dei Branch
I branch e la loro gestione sono una parte fondamentale del flusso di lavoro in Git e Github. I branch consentono agli sviluppatori di lavorare su nuove funzionalità o correzioni di bug senza influire sul codice principale, il branch principale (di solito chiamato "main" o "master").

Un nuovo branch (ad esempio "new-login") può essere creato per cambiare profondamente il sistema di login della nostra applicazione, può richiedere molto lavoro e cambiare più do un file del repository. Mentre il branch principale rimane stabile e funzionante, il nuovo branch può essere sviluppato e testato in modo indipendente. Una volta completate le modifiche, il branch può essere unito al branch principale tramite una "pull request", che consente agli altri membri del team di rivedere le modifiche prima della fusione del nuovo codice nel branch principale.

```bash
# mostra i branch e quello attivo
git branch

# crea un nuovo branch e spostati su di esso
git checkout -b <nome-branch>

# spostati su un branch esistente
git checkout <nome-branch>

# unisci il branch attivo con un altro branch
git merge <nome-branch>
```

## Connettere il repository locale con quello remoto su Github
Per connettere il repository locale con quello remoto su Github, è necessario aggiungere l'URL del repository remoto come "remote" nel repository locale. Questo consente di sincronizzare le modifiche tra il repository locale e quello remoto su Github, consentendo di condividere il codice con altri sviluppatori e di collaborare su progetti open-source. Una volta connesso, è possibile eseguire il push delle modifiche locali al repository remoto e il pull delle modifiche dal repository remoto al repository locale.

```bash
# mostra le configurazioni correnti di Git
git config --list

# configura le informazioni utente globali per Git
git config --global user.email "myemail@example.it"
git config --global user.name "mygithubusername"

# mostra i repository remoti configurati
git remote -v

# aggiunge un repository remoto con un nome specifico (ad esempio "origin")
git remote add origin <repository_url>
git remote -v
```

Se ora il repository remoto è stato aggiunto correttamente, è possibile lavorare sul repository locale e sincronizzare le modifiche con il repository remoto su Github. Per inviare le modifiche locali al repository remoto, è possibile utilizzare il comando "git push", mentre per recuperare le modifiche dal repository remoto al repository locale, è possibile utilizzare il comando "git pull".

```bash
# clone del repository remoto sul computer locale
git clone <repository_url>

# invia le modifiche locali al repository remoto
git push origin <nome-branch>

# recupera le modifiche dal repository remoto al repository locale
git pull origin <nome-branch>
```

