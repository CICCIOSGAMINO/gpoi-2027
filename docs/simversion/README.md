Simversion 
==========
[TOC]

Official website (Manifesto e Linee Guida)
https://simversion.github.io/

Simversion è uno standard ormai di riferimento per la gestione del numero di versione di un progetto software. Il suo obiettivo è quello di fornire un sistema semplice e coerente per la gestione delle versioni, che consente agli sviluppatore di gestire nei vari strumenti di gestione del codice sorgente (Git, GitHub, GitLab, ...) e servizi di Continuous Integration (CI) e Continuous Deployment (CD) il numero di versione del software.

# Linee guida per la gestione del numero di versione
Il numero di versione di un progetto software è composto da tre parti principali: Major, Minor e Patch. Queste parti sono separate da punti e rappresentano rispettivamente le modifiche significative, le modifiche minori e le correzioni di bug. Ad esempio, una versione 1.2.3 indica che il progetto ha subito una modifica significativa (Major), due modifiche minori (Minor) e tre correzioni di bug (Patch).

## Major
La parte Major del numero di versione viene incrementata quando vengono apportate modifiche significative al progetto, come l'aggiunta di nuove funzionalità o la rimozione di funzionalità esistenti. L'incremento della parte Major indica che il progetto ha subito un cambiamento significativo e che potrebbe non essere compatibile con le versioni precedenti.

## Minor
La parte Minor del numero di versione viene incrementata quando vengono apportate modifiche minori al progetto, come l'aggiunta di nuove funzionalità che non compromettono la compatibilità con le versioni precedenti. L'incremento della parte Minor indica che il progetto ha subito un cambiamento minore e che è compatibile con le versioni precedenti.

## Patch
La parte Patch del numero di versione viene incrementata quando vengono apportate correzioni di bug o miglioramenti minori al progetto. L'incremento della parte Patch indica che il progetto ha subito una correzione di bug o un miglioramento minore e che è compatibile con le versioni precedenti.