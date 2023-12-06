---
title: Amministrazione degli utenti e sicurezza
description: Scopri come funzionano l’amministrazione degli utenti e la sicurezza
exl-id: 1269a652-5261-413d-9ea0-b4f75003e9d8
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '718'
ht-degree: 10%

---

# Amministrazione degli utenti e sicurezza {#id181AED00G5Z}

Per accedere e configurare le funzioni nelle guide AEM, devi creare degli utenti. A questi utenti possono quindi essere assegnate le autorizzazioni di accesso a tutte o a funzioni specifiche nelle guide AEM. Scopri come configurare e mantenere l’autorizzazione degli utenti e anche come funziona l’autenticazione e l’autorizzazione in AEM.

I seguenti argomenti nella documentazione AEM ti aiuteranno a comprendere l’amministrazione degli utenti e i concetti e le funzionalità relativi alla sicurezza:

- [Utenti e gruppi in AEM](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/security.html#UsersandGroupsinAEM)

- [Autorizzazioni in AEM](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/security.html#PermissionsinAEM)

- [Gestione di utenti e gruppi](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/security.html#ManagingUsersandGroups)

- [Gestione delle autorizzazioni](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/security.html#ManagingPermissions)


## Gruppi di utenti creati da Guide AEM {#id181TF0K0MHT}

Le guide AEM forniscono tre gruppi predefiniti per gestire diverse attività in un progetto DITA. Tali gruppi sono: *Autori*, *Revisori*, e *Editori*. A seconda del gruppo a cui è associato un utente, questi può eseguire attività specifiche. Ad esempio, un’attività di pubblicazione può essere eseguita solo da un editore, ma non da un autore o un revisore. Analogamente, un autore può creare un nuovo argomento e un revisore può solo esaminare un argomento.

>[!TIP]
>
> Consulta la *Autorizzazioni* sezione nella guida alle best practice per le best practice sull’impostazione delle autorizzazioni utente.

Nella tabella seguente sono elencate le varie attività e i gruppi che possono eseguirle:

| Attività | Autori | Revisori | Editori |
|----|-------|---------|----------|
| Crea argomento DITA | Sì |   | Sì |
| Crea mappa DITA | Sì |   | Sì |
| Mappare le raccolte | Sì |   | Sì |
| Crea attività di revisione | Sì |   | Sì |
| Rivedi argomento[1](#fntarg_1) | Sì | Sì | Sì |
| Risoluzione chiave | Sì |   | Sì |
| Apri nel FrameMaker | Sì |   | Sì |
| Check-out/check-in | Sì |   | Sì |
| Modifica argomento | Sì |   | Sì |
| Sposta argomento | Sì |   | Sì |
| Modifica proprietà argomento | Sì |   | Sì |
| Copiare | Sì |   | Sì |
| Eliminare | Sì |   | Sì |
| Condividi | Sì |   | Sì |
| **Stato documento** |
| Crea/modifica profilo stato documento |   |   | Sì |
| Cambia stato documento[2](#fntarg_2) | Sì | Sì | Sì |
| **Funzioni disponibili nella console delle mappe DITA \(scheda Predefiniti di output\)** |
| Genera |   |   | Sì |
| Modifica |   |   | Sì |
| Duplica |   |   | Sì |
| Creare |   |   | Sì |
| Elimina predefinito |   |   | Sì |
| **Funzioni disponibili nella console delle mappe DITA \(scheda Output\)** |
| Visualizza output generato | Sì |   | Sì |
| **Funzioni disponibili nella console delle mappe DITA \(scheda Argomenti\)** |
| Crea attività di revisione | Sì |   | Sì |
| Modifica | Sì |   | Sì |
| **Funzioni disponibili nella console delle mappe DITA \(scheda Baseline\)** |
| Creare |   |   | Sì |
| Modifica |   |   | Sì |
| Duplica |   |   | Sì |
| Rimuovi |   |   | Sì |
| Console mappe DITA \(scheda Rapporti\) | Sì |   | Sì |
| **Funzioni disponibili nella console delle mappe DITA \(Predefiniti condizione\)** |
| Crea/modifica predefinito condizione |   |   | Sì |

## Note aggiuntive sui gruppi di utenti

Il seguente elenco contiene alcuni consigli e punti relativi ai gruppi di utenti e alle autorizzazioni corrispondenti:

- Se desideri che un utente avvii il flusso di lavoro di traduzione o revisione, accertati che sia membro del gruppo *Editori* e *gruppo projects-administrator*.

- Gli utenti devono disporre delle autorizzazioni di lettura, creazione, eliminazione e modifica disponibili nelle cartelle della lingua di origine e di destinazione su cui devono lavorare.

- Se crei un progetto, ne sei il proprietario con *Editori* autorizzazioni. Affinché gli altri utenti di un progetto possano vedere i membri del team, creare attività o creare flussi di lavoro, è necessario che dispongano dell&#39;accesso in lettura a `/home/users` e `/home/groups` nodi. Un modo per dare accesso in lettura a `/home/users` e `/home/groups` mediante il conferimento dell&#39;accesso in lettura al `projects-users` gruppo.

- *Revisori* Puoi accedere e aggiungere commenti di revisione su un argomento in revisione dalla console Progetto o dal collegamento di notifica nella casella in entrata. Inoltre, questo accesso è disponibile solo fino al momento in cui l’attività di revisione è aperta.

- Per impostazione predefinita, *Editori* dispongono dell’accesso e delle autorizzazioni per le seguenti cartelle in DAM:

   - ``/var/dxml``-\> Lettura e scrittura

   - `/content/dam/fmdita-outputs` -\> Lettura e scrittura

   - `/content/output/sites` -\> Lettura e scrittura

  Se utilizzi una posizione diversa da quelle di pubblicazione predefinite sopra indicate, devi assegnare all’editore autorizzazioni di lettura e scrittura esplicite.

- Tutti gli utenti in *Autori*, *Revisori*, e *Editori* i gruppi dispongono dell’accesso in lettura a tutto il contenuto in DAM.

- Le autorizzazioni a livello di cartella devono essere assegnate agli utenti tramite la pagina di amministrazione degli utenti.

- Se desideri che gli utenti possano eseguire operazioni di ricerca in DAM, devi renderli membri di *dam-users* gruppo.

- Se desideri assegnare i diritti di amministratore a qualsiasi utente, puoi farlo consentendo l’accesso tramite i gruppi basati sugli standard AEM come *amministratori*, *projects-administrator*, o configurazione OSGI \(console Felix\).

- Per assegnare a un utente i diritti per modificare lo stato di un documento, assicurarsi di aggiungere l&#39;utente nella sezione relativa alla transizione dello stato del profilo di stato del documento.

[1](#fnsrc_1) Se *Autori* e *Editori* sono invitati a una revisione.[2](#fnsrc_2) A seconda dei diritti assegnati all&#39;utente nel profilo dello stato del documento.
