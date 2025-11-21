---
title: Amministrazione degli utenti e sicurezza
description: Scopri come funzionano l’amministrazione degli utenti e la sicurezza
exl-id: 10ab0f3c-97dc-4293-ab73-75b438c03d99
feature: User Management
role: Admin
level: Experienced
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '700'
ht-degree: 10%

---

# Amministrazione degli utenti e sicurezza {#id181AED00G5Z}

Per accedere e configurare le funzioni di AEM Guides, devi creare degli utenti. A questi utenti possono quindi essere assegnate le autorizzazioni per accedere a tutte o a funzioni specifiche di AEM Guides. Scopri come configurare e mantenere l’autorizzazione utente e anche come funziona l’autenticazione e l’autorizzazione in AEM.

I seguenti argomenti nella documentazione di AEM sono utili per comprendere l’amministrazione degli utenti e i concetti e le funzioni relativi alla sicurezza:

- [Utenti, gruppi e autorizzazioni di AEM](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/accessing/aem-users-groups-and-permissions.html)

- [Amministrazione utenti e sicurezza](https://experienceleague.adobe.com/docs/experience-manager-65/administering/security/security.html?lang=it)


## Gruppi di utenti creati da AEM Guides {#id181TF0K0MHT}

AEM Guides fornisce tre gruppi preconfigurati. Questi gruppi sono: *Autori*, *Revisori* e *Editori*. A seconda del gruppo a cui è associato un utente, questi può eseguire attività specifiche. Ad esempio, un’attività di pubblicazione può essere eseguita solo da un editore, ma non da un autore o un revisore. Analogamente, un autore può creare un nuovo argomento e un revisore può solo esaminare un argomento.

>[!TIP]
>
> Consulta la sezione *Autorizzazioni* nella guida alle best practice per le best practice sull&#39;impostazione delle autorizzazioni utente.

Nella tabella seguente sono elencate le varie attività e i gruppi che possono eseguirle:

| Attività | Autori | Revisori | Editori |
|----|-------|---------|----------|
| Crea argomento DITA | Sì |   | Sì |
| Crea mappa DITA | Sì |   | Sì |
| Mappare le raccolte | Sì |   | Sì |
| Crea attività di revisione | Sì |   | Sì |
| Rivedi argomento[1](#fntarg_1) | Sì | Sì | Sì |
| Risoluzione chiave | Sì |   | Sì |
| Check-out/check-in | Sì |   | Sì |
| Modifica argomento | Sì |   | Sì |
| Sposta argomento | Sì |   | Sì |
| Modifica proprietà argomento | Sì |   | Sì |
| Copia | Sì |   | Sì |
| Eliminare | Sì |   | Sì |
| Condividi | Sì |   | Sì |
| **Stato documento** |  |  |  |
| Crea/modifica profilo stato documento |   |   | Sì |
| Cambia stato documento[2](#fntarg_2) | Sì | Sì | Sì |
| **Funzioni disponibili nella console delle mappe DITA \(scheda Predefiniti di output\)** |  |  |  |
| Genera |   |   | Sì |
| Modifica |   |   | Sì |
| Duplica |   |   | Sì |
| Creare |   |   | Sì |
| Elimina predefinito |   |   | Sì |
| **Funzioni disponibili nella console delle mappe DITA \(scheda Output\)** |  |  |  |
| Visualizza output generato | Sì |   | Sì |
| **Funzioni disponibili nella console delle mappe DITA \(scheda Argomenti\)** |  |  |  |
| Crea attività di revisione | Sì |   | Sì |
| Modifica | Sì |   | Sì |
| **Funzioni disponibili nella console delle mappe DITA \(scheda Baseline\)** |  |  |  |
| Creare |   |   | Sì |
| Modifica |   |   | Sì |
| Duplica |   |   | Sì |
| Rimuovere |   |   | Sì |
| Console mappe DITA \(scheda Rapporti\) | Sì |   | Sì |
| **Funzionalità disponibili nella console delle mappe DITA \(Predefiniti condizione\)** |  |  |  |
| Crea/modifica predefinito condizione |   |   | Sì |

## Note aggiuntive sui gruppi di utenti

Il seguente elenco contiene alcuni consigli e punti relativi ai gruppi di utenti e alle autorizzazioni corrispondenti:

- Se desideri che un utente avvii il flusso di lavoro di traduzione o revisione, assicurati che l&#39;utente sia membro del gruppo *Editori* e *amministratori di progetti*.

- Gli utenti devono disporre delle autorizzazioni di lettura, creazione, eliminazione e modifica disponibili nelle cartelle della lingua di origine e di destinazione su cui devono lavorare.

- Se crei un progetto, sei il proprietario del progetto con le autorizzazioni *Editori*. Affinché gli altri utenti di un progetto possano visualizzare i membri del team, creare attività o creare flussi di lavoro, è necessario che dispongano dell&#39;accesso in lettura sui nodi `/home/users` e `/home/groups`. Un modo per concedere l&#39;accesso in lettura ai nodi `/home/users` e `/home/groups` consiste nel concedere l&#39;accesso in lettura al gruppo `projects-users`.

- *I revisori* possono accedere e aggiungere commenti di revisione su un argomento in revisione dalla console del progetto o dal collegamento di notifica della casella in entrata. Inoltre, questo accesso è disponibile solo fino al momento in cui l’attività di revisione è aperta.

- Per impostazione predefinita, a *Publishers* sono concessi l&#39;accesso e le autorizzazioni per le seguenti cartelle in DAM:

   - `/content/fmdita` -\> Lettura e scrittura

   - `/content/dam/fmdita-outputs` -\> Lettura e scrittura

   - `/content/output/sites` -\> Lettura e scrittura

  Se utilizzi una posizione diversa da quelle di pubblicazione predefinite sopra indicate, devi assegnare all’editore autorizzazioni di lettura e scrittura esplicite.

- Tutti gli utenti dei gruppi *Autori*, *Revisori* e *Editori* hanno accesso in lettura a tutti i contenuti in DAM.

- Le autorizzazioni a livello di cartella devono essere assegnate agli utenti tramite la pagina di amministrazione degli utenti.

- Se desideri che gli utenti possano eseguire operazioni di ricerca in DAM, devi renderli membri del gruppo *dam-users*.

- Se desideri assegnare i diritti di amministratore a qualsiasi utente, puoi concedergli l&#39;accesso tramite i gruppi standard di AEM come *amministratori*, *amministratori di progetti* o la configurazione OSGI \(console Felix\).

- Per assegnare a un utente i diritti per modificare lo stato di un documento, assicurarsi di aggiungere l&#39;utente nella sezione relativa alla transizione dello stato del profilo di stato del documento.

[1](#fnsrc_1) Se *Autori* e *Editori* sono invitati a una revisione.[2](#fnsrc_2) a seconda dei diritti assegnati all&#39;utente nel profilo dello stato del documento.
