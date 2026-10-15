---
title: Collegamento di AEM Guides con Knowledge AI di Guides
description: Scopri come collegare AEM Guides con la Knowledge AI di Guides
feature: Introduction
role: Admin
level: Experienced
source-git-commit: 05976e2a408e57256a454f181bb93d900dc091ab
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 1%
---

# Connettere Adobe Experience Manager Guides con la Knowledge AI di Guides (Beta)

>[!IMPORTANT]
>
> Questa funzione è disabilitata per impostazione predefinita. Per abilitare la funzione IA per la Knowledge Base delle Guide, contatta il team Customer Success.

Questo articolo fornisce agli amministratori e ai tecnici dei contenuti il processo end-to-end per configurare l’accesso a Knowledge AI delle guide e caricare i contenuti Experience Manager Guides da utilizzare in Knowledge AI.

## Panoramica del processo

| Passaggio | Come procedere |
|---|---|
| 1 | Crea un account di servizio in Adobe Developer Console e configuralo per il tuo ambiente. |
| 2 | Recupera l’e-mail dell’account tecnico dal file delle credenziali dell’account di servizio. |
| 3 | Concedi all’account di servizio l’accesso in Knowledge AI creando un ruolo e aggiungendo l’utente. |
| 4 | Configura un predefinito di output di IA per la Knowledge Base in Experience Manager Guides e carica il contenuto. |


## Prerequisiti

Prima di iniziare, assicurati di disporre dei seguenti diritti di accesso e autorizzazioni:

| Requisito | Scopo |
|---|---|
| Console per sviluppatori di Adobe | Crea l’account di servizio e scarica le relative credenziali JSON. |
| Adobe Experience Manager Guides | Creare contenuti e configurare il predefinito di output per Knowledge AI. |
| [IA per la Knowledge Base](https://guidesai.adobe.io/) | Gestisci ruoli e utenti e ricevi i contenuti caricati. |
| Autorizzazione: Crea account di servizio | Richiesto in Adobe Developer Console per creare un account di servizio. |
| Autorizzazione: gestire utenti e ruoli in Knowledge AI | Necessario per concedere all’account di servizio l’accesso in Knowledge AI. |

## Creare un account di servizio

Knowledge AI utilizza un account di servizio per l’autenticazione sicura e l’accesso ai contenuti.

1. Segui le istruzioni riportate in [Configurazione IMT di Microsoft Services](https://experienceleague.adobe.com/it/docs/experience-manager-guides/using/knowledge-base/kb-articles/publishing/configure-microservices-imt-config).

1. Crea un nuovo account di servizio e scarica il file di credenziali JSON generato.

1. Configura le impostazioni di ambiente richieste utilizzando le credenziali scaricate.

Al termine, l’account di servizio deve essere associato correttamente all’ambiente.

>[!NOTE]
>
> Se hai già creato e configurato un account di servizio per il tuo ambiente, puoi procedere al passaggio successivo.


## Recuperare l’e-mail dell’account tecnico

Per concedere l’accesso a Knowledge AI, identifica l’account del servizio.

1. Aprire il file JSON dell&#39;account del servizio scaricato.
1. Cercare il nome del campo `technical_account_email`. Visualizza un valore simile al seguente:

   ```json
   {
   "technical_account_email": "a1b2c3d4e5f6@techacct.adobe.com"
   }
   ```

1. Copia l&#39;indirizzo e-mail associato a `technical_account_email`. Nel passaggio successivo utilizzerai questo indirizzo e-mail.

## Concedere l’accesso in Knowledge AI

Per consentire all’account di servizio di gestire e caricare il contenuto, aggiungilo a Knowledge AI con le autorizzazioni appropriate.

1. Apri [Knowledge AI](https://guidesai.adobe.io/).
1. Passa a **Protezione > Ruoli** e crea un ruolo con le autorizzazioni minime richieste.
1. Passa a **Protezione > Utenti > Aggiungi utente**. Aggiungi un nuovo utente utilizzando `technical_account_email` copiato dal JSON dell&#39;account del servizio, seleziona i domini dal menu a discesa **Domini** e assegna il ruolo creato nel passaggio precedente.

L’account di servizio è ora autorizzato a eseguire le operazioni di amministrazione e caricamento dei contenuti.

## Configurare il predefinito di IA per la Knowledge Base e caricare il contenuto

Per pubblicare i contenuti in Knowledge AI, configura Experience Manager Guides dopo aver impostato le autorizzazioni.

1. Apri la **console Mappa** in Experience Manager Guides.
1. Passare alla scheda **Predefiniti di output**.
1. Seleziona l’icona + per creare un predefinito di output.
1. Seleziona **Knowledge AI** dal menu a discesa **Type** nella finestra di dialogo **New output preset**. Immetti un **Nome** e seleziona **Aggiungi al profilo della cartella corrente** per creare un predefinito di output nel profilo della cartella corrente.

   ![creazione di predefiniti di ia per la conoscenza](assets/knowledge-ai-preset.png)

1. Seleziona **Aggiungi**. Viene creato il predefinito di IA per la Knowledge Base.
1. Apri il predefinito di Knowledge AI configurato.
1. Selezionare il dominio per il quale è stato concesso il ruolo a `technical_account_email`, quindi selezionare **Carica contenuto**. Questo attiva il flusso di lavoro di caricamento dei contenuti in Knowledge AI. Attendi il completamento del processo di caricamento.

   ![dominio di intelligenza artificiale](assets/knowledge-ai-domain.png)

1. Al termine del caricamento, selezionare **Apri in Knowledge AI**. Viene aperta la chat di IA per la Knowledge Base all’interno del dominio, utilizzando il contenuto caricato.

   ![knowledge-ai-open](assets/open-knowledge-ai.png)

L’account di servizio è stato configurato, sono state assegnate le autorizzazioni necessarie e il contenuto Experience Manager Guides è stato reso disponibile in Knowledge AI. Ogni volta che desideri pubblicare contenuti aggiornati, crea un nuovo predefinito di Knowledge AI e segui i passaggi descritti in [configurare il predefinito di Knowledge AI e caricare il contenuto](#configure-knowledge-ai-preset-and-upload-content) nella sezione precedente.



