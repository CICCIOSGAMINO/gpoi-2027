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

### Merging 2 branches
L'operazione di merge consente di unire le modifiche apportate in un branch con un altro branch (tipicamente il main). Il merge può essere eseguito sia in locale (git) che in remoto (github) attraverso una pull request, la seconda soluzione permette la review delle modifiche e di ricordare le modifiche apportate dalla fusione dei due branch.

```markdown
main:     A --- B --- C
                       \
feature:                D --- E
```

**Fast-forward merge**: (no divergence) Il branch main non ha subito modifche dopo la creazione del branch secondario, quindi il merge può essere eseguito senza conflitti.

```markdown
main:     A --- B --- C --- D --- E
```

**Merge commit**: (divergence) Il branch main ha subito modifiche dopo la creazione del branch secondario (modificato a sua volta), quindi il merge richiede un commit di merge per unire le modifiche dei due branch.

```markdown
main:     A --- B --- C --- M
                       \   /
feature:                D-E
```

#### Push branch (Github Push Request)
Utilizziamo il comando "git push" per inviare le modifiche locali del branch secondario al repository remoto su Github.

```bash
# switch on the branch you want to push and merge
git checkout <nome-branch>

# push the branch to the reomote repository on Github
git push origin <nome-branch>
```

Ora che le modifiche del branch secondario sono presenti sul repository remoto su Github, possiamo creare una pull request per richiedere la fusione del branch secondario con il branch principale. La pull request consente agli altri membri del team di rivedere le modifiche, discutere eventuali problemi e approvare la fusione del nuovo codice nel branch principale.

1. Go to the repo on github.com.
2. GitHub shows a banner: "<nome-branch> had recent pushes — Compare & pull request". Click it.
3. Or: Pull requests → New pull request.
4. Set base = main, compare = <nome-branch>
5. Add a title and description, then click Create pull request.
6. Review the Files changed tab (that's the diff).
7. Click Merge pull request → choose a merge strategy → Confirm merge.

#### The Local Method
Il procedimento di merge può essere portato a termine anche in locale, senza utilizzare la piattaforma Github, su sui arriveranno solo le modifiche finali del branch main.

```bash
# go to the main branch (or the branch you want to merge into)
git checkout main

# make sure the main branch is up to date with the remote repo
git pull origin main

# merge the feature branch into the main branch
git merge <nome-branch>

# push the changes to the remote repository on Github
git push origin main
```

#### Conflicts
In alcuni casi, durante il merge di due branch, possono verificarsi conflitti se le modifiche apportate in entrambi i branch riguardano le stesse righe di codice o file. In questi casi, Git non può determinare automaticamente quale versione del codice mantenere e richiede l'intervento manuale dello sviluppatore per risolvere il conflitto. I conflitti devono essere risolti manualmente modificando i file interessati, rimuovendo i marcatori di conflitto e scegliendo quale versione del codice mantenere. Una volta risolti i conflitti, è necessario eseguire un commit per salvare le modifiche e completare il merge.

```text
your version on main
their version on feature
```

Edita il file rimuovendo i marcatori di conflitto e scegliere quale versione del codice in conflitto mantenere.

```text
your version on main
```

```bash
# add the file to the staging area 
git add <file-in-conflitto>
git commit -m "Risolto conflitto tra main e <nome-branch>"
git push origin main

# remove the feature branch if no longer needed
git branch -d <nome-branch>
```

#### Rebase
Il rebase è un'operazione avanzata in git che permette di riportare il repository a uno stato precedente, riscrivendo la cronologia dei commit. Il rebase può essere utilizzato per integrare le modifiche di un branch in un altro branch, mantenendo una cronologia lineare e pulita. Tuttavia, il rebase può essere rischioso se non viene utilizzato correttamente, poiché può causare la perdita di commit o la creazione di conflitti complessi. È importante comprendere le implicazioni del rebase e utilizzarlo con cautela, soprattutto quando si lavora in team.

```bash
# switch to the branch you want to rebase
git checkout <nome-branch>

# rebase the branch onto the main branch
git rebase main
```

