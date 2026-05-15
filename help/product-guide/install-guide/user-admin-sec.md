---
title: Amministrazione degli utenti e sicurezza
description: Scopri come funzionano l’amministrazione degli utenti e la sicurezza
exl-id: 1269a652-5261-413d-9ea0-b4f75003e9d8
feature: User Management
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/Che13Q87qddeS5u48gPSfCqfIyunmBshHlq5pB-HjGk
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: b1210526-416b-4ef6-bcc0-1692e99f30e9
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
  - id: d90290ec-3e61-4ebd-8649-bcafe0836803
  - id: e88e74c7-6080-446a-8eb0-496f1ac5f7e6
subfeature_v2:
  - id: a7a242db-c88c-4e44-818b-bfb4ef92efdf
  - id: c837a922-f95c-4da0-83b2-0cfe7038c5d6
  - id: c8841798-1a28-4264-a46a-984860f8e6f6
  - id: f7774ebe-aec9-42b6-97e4-5002acdc712e
  - id: f9dbea21-a714-40dd-bc90-080d8046c93f
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 758
ht-degree: 10%

---

# Amministrazione degli utenti e sicurezza {#id181AED00G5Z}

Per accedere e configurare le funzioni di AEM Guides, devi creare degli utenti. A questi utenti possono quindi essere assegnate le autorizzazioni per accedere a tutte o a funzioni specifiche di AEM Guides. Scopri come configurare e mantenere l’autorizzazione utente e anche come funziona l’autenticazione e l’autorizzazione in AEM.

I seguenti argomenti nella documentazione di AEM sono utili per comprendere l’amministrazione degli utenti e i concetti e le funzioni relativi alla sicurezza:

- [Utenti e gruppi in AEM](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/security.html#UsersandGroupsinAEM)

- [Autorizzazioni in AEM](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/security.html#PermissionsinAEM)

- [Gestione di utenti e gruppi](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/security.html#ManagingUsersandGroups)

- [Gestione delle autorizzazioni](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/security.html#ManagingPermissions)


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
| Apri in FrameMaker | Sì |   | Sì |
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

   - ``/var/dxml``-\> Lettura e scrittura

   - `/content/dam/fmdita-outputs` -\> Lettura e scrittura

   - `/content/output/sites` -\> Lettura e scrittura

  Se utilizzi una posizione diversa da quelle di pubblicazione predefinite sopra indicate, devi assegnare all’editore autorizzazioni di lettura e scrittura esplicite.

- Tutti gli utenti dei gruppi *Autori*, *Revisori* e *Editori* hanno accesso in lettura a tutti i contenuti in DAM.

- Le autorizzazioni a livello di cartella devono essere assegnate agli utenti tramite la pagina di amministrazione degli utenti.

- Se desideri che gli utenti possano eseguire operazioni di ricerca in DAM, devi renderli membri del gruppo *dam-users*.

- Se desideri assegnare i diritti di amministratore a qualsiasi utente, puoi concedergli l&#39;accesso tramite i gruppi standard di AEM come *amministratori*, *amministratori di progetti* o la configurazione OSGI \(console Felix\).

- Per assegnare a un utente i diritti per modificare lo stato di un documento, assicurarsi di aggiungere l&#39;utente nella sezione relativa alla transizione dello stato del profilo di stato del documento.

[1](#fnsrc_1) Se *Autori* e *Editori* sono invitati a una revisione.[2](#fnsrc_2) A seconda dei diritti assegnati all&#39;utente nel profilo dello stato del documento.
