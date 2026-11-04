---
title: Configurazione di GitLab per Edge Delivery Services
description: Scopri come configurare archivi GitLab, accedere a token, Cloud Manager, webhook e Bring Your Own Git per pubblicare contenuti da Experience Manager Guides a Edge Delivery Services.
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 97620587a9e736e0886ea4d7158af330814e6392
workflow-type: tm+mt
source-wordcount: '1256'
ht-degree: 3%
---

# Configurazione di GitLab per Edge Delivery Services

Per pubblicare contenuti da Experience Manager Guides a Edge Delivery Services (EDS) utilizzando GitLab, connetti un archivio GitLab al tuo sito EDS tramite la funzionalità *Bring Your Own Git* (BYOG) di Cloud Manager. Questo articolo elenca i passaggi in sequenza. Per informazioni dettagliate su ciascun passaggio, consulta la documentazione collegata.

## Come funziona

- Un archivio **GitHub** crea il sito EDS tramite l&#39;app AEM Code Sync.
- Un repository **GitLab** memorizza il contenuto pubblicato da Experience Manager Guides.
- **Cloud Manager** collega i due eventi tramite la ricezione di eventi push GitLab (webhook) e la loro sincronizzazione con il sito EDS.

## Prerequisiti

- Accesso a GitHub e GitLab (GitLab.com o self-hosted) per creare archivi e token.
- Accesso a Cloud Manager, con un ruolo che consente di aggiungere archivi (Responsabile della distribuzione o Proprietario business).
- Amministratore di sistema o sviluppatore API nella tua organizzazione Adobe per creare l’integrazione API di Cloud Manager.
- Organizzazione `aem.live` registrata nel servizio di configurazione. Ulteriori informazioni sono disponibili in [Configurazione del servizio](https://www.aem.live/docs/config-service-setup).

## Sequenza di configurazione

1. [Creare il sito EDS tramite GitHub](#1-create-the-eds-site-using-github-create-eds-site)
2. [Creare l’archivio GitLab](#2-create-the-gitlab-repository)
3. [Configurare l’URL del punto di montaggio](#3-configure-the-mountpoint-url)
4. [Creare token di accesso GitLab](#4-create-gitlab-access-tokens)
5. [Aggiungere l’archivio GitLab a Cloud Manager](#5-add-the-gitlab-repository-to-cloud-manager)
6. [Generare una chiave API Cloud Manager](#6-generate-a-cloud-manager-api-key)
7. [Configurare il webhook GitLab](#7-configure-the-gitlab-webhook)
8. [Aggiungere il sito EDS a Cloud Manager](#8-add-the-eds-site-to-cloud-manager)
9. [Connettere l’archivio utilizzando Porta il tuo Git](#9-connect-the-repository-using-bring-your-own-git)
10. [Configurare il sito EDS per l&#39;utilizzo di Cloud Manager](#10-configure-the-eds-site-to-use-cloud-manager)
11. [Sincronizza e verifica](#11-sync-and-verify)
12. [Pubblica da Experience Manager Guides](#12-publish-from-experience-manager-guides)

### &#x200B;1. Creare il sito EDS tramite GitHub {#create-eds-site}

Crea un archivio GitHub dalla piattaforma standard AEM Guides e installa su di esso l’app AEM Code Sync. Salva l&#39;**URL live** (`https://<branch>--<github-repo>--<github-username>.aem.live`) generato per dopo.

Per i passaggi, visualizzare [Creare un archivio GitHub per EDS](./configure-eds.md#create-a-github-repository-for-eds) e [Connettere GitHub ad Adobe tramite AEM Code Sync](./configure-eds.md#connect-github-to-adobe-via-aem-code-sync).

>[!IMPORTANT]
>
> Non creare il sito EDS con l&#39;opzione di un clic in Cloud Manager. I siti creati in questo modo non ti concedono le autorizzazioni di amministratore necessarie per i passaggi successivi. Ulteriori informazioni in [Preparare il sito Edge Delivery Services](https://www.aem.live/developer/byo-git#1.-prepare-your-edge-delivery-services-site).

### &#x200B;2. Creare l’archivio GitLab

Creare un archivio GitLab separato (ad esempio, `my-eds-gitlab`) dalla stessa piattaforma standard di AEM Guides. Experience Manager Guides pubblica l’output generato in questo archivio. EDS richiede un ramo `main`.

Per creare l&#39;archivio, creare un progetto vuoto e inviarvi il contenuto di [aem-guides-boilerplate](https://github.com/adobe/aem-guides-boilerplate) oppure importare la boilerplate in un nuovo progetto. Per i passaggi, visualizza [Crea un progetto](https://docs.gitlab.com/user/project/) e [Importa il progetto da GitHub a GitLab](https://docs.gitlab.com/user/project/import/github/) nella documentazione di GitLab.

### &#x200B;3. Configurare l’URL del punto di montaggio

Nell&#39;archivio GitHub, aggiornare `fstab.yaml` in modo che l&#39;origine di contenuto punti all&#39;archivio GitLab e confermare la modifica in `main`.

```text
https://<worker URL>/gitlab/<git acc domain>/<git username>/<git repo>/main/docs
```

| Parametro | Descrizione |
|---|---|
| `<worker URL>` | URL del nodo di lavoro fornito da Adobe. |
| `<git acc domain>` | Dominio GitLab, ad esempio `gitlab.com`, o dominio con hosting autonomo. |
| `<git username>` | Nome utente GitLab. |
| `<git repo>` | Nome dell’archivio GitLab. |
| `main` / `docs` | Ramo e cartella principale. Valori predefiniti per Experience Manager Guides. |

### &#x200B;4. Creare token di accesso GitLab

Crea i token di accesso necessari per:

- **Cloud Manager**, per convalidare e accedere all&#39;archivio. Ulteriori informazioni in [Aggiungere archivi esterni in Cloud Manager](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-manager/content/managing-code/external-repositories).
- **Profilo pubblicazione Experience Manager Guides**, per eseguire il commit dell&#39;output pubblicato. Crea un token di accesso al progetto GitLab con il ruolo **Sviluppatore** e l&#39;ambito `api`. Ulteriori informazioni sono disponibili nella [documentazione GitLab](https://docs.gitlab.com/ee/user/project/settings/project_access_tokens.html).

>[!NOTE]
>
> Rinnovare i token prima della scadenza. La pubblicazione non riesce se il token nel profilo di pubblicazione è scaduto. Per aggiornare un token utilizzato da Cloud Manager, visualizzare [Gestisci token di accesso per archivi esterni](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-manager/content/managing-code/manage-access-tokens).

### &#x200B;5. Aggiungere l’archivio GitLab a Cloud Manager

In Cloud Manager, vai a **Archivi** > **Aggiungi archivio**, seleziona **Archivio privato** e convalida la proprietà utilizzando il token di accesso. Attendere che lo stato dell&#39;archivio sia **Pronto**. L’opzione BYOG è disponibile solo dopo che almeno un archivio esterno è pronto.

Per i passaggi, visualizza [Aggiungi archivi esterni in Cloud Manager](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-manager/content/managing-code/external-repositories).

### &#x200B;6. Generare una chiave API Cloud Manager

Creare un&#39;integrazione API in Adobe Developer Console (**API Cloud Manager**, **Server-to-Server OAuth**) e copiare il **ID client (chiave API)**.

Per i passaggi, visualizzare [Creazione di un progetto di integrazione API](https://developer.adobe.com/experience-cloud/cloud-manager/guides/getting-started/create-api-integration).

### &#x200B;7. Configurare il webhook GitLab

In Cloud Manager, selezionare **Webhook di configurazione** per l&#39;archivio e copiare l&#39;**URL del webhook** e il **segreto**. Aggiungere la chiave API all&#39;URL (`<webhook URL>&api-key=<CLIENT_ID>`). In GitLab, vai a **Impostazioni** > **Webhook**, aggiungi l&#39;URL e il segreto, seleziona il ramo `main` e abilita **Eventi push**.

Per ulteriori dettagli, visualizzare [Configurare l&#39;archivio esterno in Cloud Manager](https://www.aem.live/developer/byo-git#2.-configure-your-external-repository-in-cloud-manager).

### &#x200B;8. Aggiungere il sito EDS a Cloud Manager

In Cloud Manager, vai a **Edge Delivery** > **Aggiungi sito Edge Delivery** e immetti l&#39;URL live salvato nel passaggio 1. Completare la convalida della proprietà.

Per i passaggi, visualizza [Aggiungi un sito Edge Delivery](https://experienceleague.adobe.com/it/docs/experience-manager-cloud-service/content/implementing/using-cloud-manager/edge-delivery-sites/add-edge-delivery-site).

### &#x200B;9. Connettere l’archivio utilizzando Porta il tuo Git

Nel sito EDS di Cloud Manager, seleziona **Porta il tuo Git (BYOG)**, scegli l&#39;archivio GitLab e conferma. Copia e archivia in modo sicuro il segreto generato. Viene visualizzato una sola volta e viene generato un nuovo segreto se riconfiguri il sito.

Per informazioni dettagliate, visualizza [Configura il tuo sito Edge Delivery in Cloud Manager](https://www.aem.live/developer/byo-git#3.-configure-your-edge-delivery-site-in-cloud-manager).

### &#x200B;10. Configurare il sito EDS per l&#39;utilizzo di Cloud Manager

Impostare l&#39;origine codice del sito EDS nel repository di Cloud Manager utilizzando l&#39;ID **programma** (`/program/<PROGRAM_ID>/`) e l&#39;ID **repository** (`/repo/<REPO_ID>/`) dall&#39;URL del webhook. Quindi creare un segreto denominato esattamente `cm-byog` con il segreto del passaggio 9.

Per le chiamate API amministratore, visualizza [Configura il tuo sito AEM per utilizzare Cloud Manager](https://www.aem.live/developer/byo-git#4.-configure-your-aem-site-to-use-cloud-manager).

### &#x200B;11. Sincronizza e verifica

In Cloud Manager, selezionare **Sincronizza codice** dal menu del sito e scegliere il ramo `main`. Quindi apri `https://main--<site>--<org>.aem.page` per verificare il sito.

Per ulteriori dettagli, visualizza [Attiva la prima sincronizzazione](https://www.aem.live/developer/byo-git#5.-trigger-your-first-sync) e [Verifica il tuo sito AEM](https://www.aem.live/developer/byo-git#6.-verify-your-aem-site).

### &#x200B;12. Pubblica da Experience Manager Guides

Creare un profilo di pubblicazione EDS con il tipo di account **Git** impostato su **GitLab**, utilizzando il token di accesso al progetto del passaggio 4. Quindi selezionate questo profilo in un predefinito di output EDS e generate l&#39;output. L&#39;output viene confermato nella cartella `docs` dell&#39;archivio GitLab.

Per i passaggi, visualizzare [Creare il profilo di pubblicazione EDS](./configure-eds.md#create-the-eds-publish-profile-for-github-or-gitlab) e [Creare un predefinito di output per EDS e generare l&#39;output](./configure-eds.md#create-an-output-preset-for-eds-and-generate-output).

## Risoluzione di problemi

- **Il sito visualizza contenuto precedente dopo un messaggio push:** Verificare che il webhook stia distribuendo eventi a Cloud Manager, quindi controllare lo stato del processo di sincronizzazione più recente.
- **Errore di sincronizzazione `Unable to fetch hlxignore: 401`:** Il segreto `cm-byog` non è corretto. Ricrea il segreto dal passaggio 9.
- **Archivio collegato a un altro sito:** Un archivio Cloud Manager può essere collegato a un solo sito alla volta. Per condividere un repository tra siti, utilizzare [Ripoless](https://www.aem.live/docs/repoless).

Per ulteriori dettagli, vedi [Risoluzione dei problemi in Porta il tuo Git](https://www.aem.live/developer/byo-git#troubleshooting).
