---
title: Best practice per impostare la struttura delle cartelle
description: Scopri le best practice per impostare la struttura di cartelle quando utilizzi i contenuti di apprendimento e formazione in Experience Manager Guides.
feature: Authoring
role: Admin
level: Experienced
source-git-commit: 64adc89966e60823f6b46fb062b7659ed150cfc3
workflow-type: tm+mt
source-wordcount: '602'
ht-degree: 0%

---

# Procedure consigliate per la configurazione della struttura di cartelle

Questo articolo fornisce i passaggi essenziali e le best practice per consentire agli amministratori di impostare le strutture di cartelle in Adobe Experience Manager Guides. Una gerarchia di cartelle ben organizzata garantisce flussi di lavoro di authoring, pubblicazione e traduzione fluidi per i contenuti di apprendimento e formazione.

## Configurare la struttura delle cartelle

Per consentire l’accesso a varie funzioni di authoring, pubblicazione e traduzione di Experience Manager Guides, accertati di impostare le cartelle nella gerarchia corretta, come spiegato di seguito.

**Crea una cartella a livello di radice**

Per iniziare, crea una cartella principale per la tua organizzazione. Funge da base per tutte le cartelle a livello di reparto e le risorse condivise di frequente.

Esempio: `/content/dam/ABC-Corp/`

All’interno di questa cartella principale, crea una cartella dedicata per gestire le risorse che verranno utilizzate in più dipartimenti. Ad esempio, crea una cartella **Common** per includere risorse condivise come immagini, video e altro ancora.

![](assets/root-level-folder.png)

**Creare cartelle a livello di reparto**

Creare cartelle separate per ciascun reparto, ad esempio Risorse umane, Finanze e Legali, in modo che possano gestire i propri contenuti.

![](assets/department-level-folders.png)
*Didascalia: struttura di cartelle separata creata per il reparto HR all&#39;interno della cartella principale*

**Procedure consigliate per l&#39;impostazione di cartelle a livello di reparto**

- Crea una cartella **Common** > **assets** dedicata in ciascun reparto per le risorse comuni a livello di reparto (se necessario).
- Se desideri condividere il contenuto per la traduzione, crea cartelle specifiche per la lingua (ad esempio en, de, fr). Gli autori devono creare o aggiornare il contenuto solo nella cartella della lingua di origine (come en), in quanto il contenuto esterno alla cartella della lingua di origine non è incluso nel flusso di lavoro di traduzione. Le cartelle delle altre lingue possono essere mantenute vuote come segnaposto. Ulteriori informazioni su [traduzione contenuto](../user-guide/translation.md).
- Le autorizzazioni possono essere utilizzate per limitare l’accesso di specifici reparti o utenti alla struttura di cartelle appena creata. Ad esempio, assegna le autorizzazioni per garantire che solo gli utenti del reparto HR possano creare o modificare il contenuto all’interno della cartella designata.

Ripeti la stessa struttura per altri dipartimenti come quello finanziario, legale, ecc.

## Impostare la struttura delle cartelle di output

La cartella `fm-ditaoutputs` funge da percorso di archiviazione predefinito per gli output generati dai contenuti di apprendimento e formazione. Questi output in genere includono pacchetti SCORM (file ZIP) nella cartella **alm** e PDF nella cartella **pdf**. Se necessario, è possibile modificare questo percorso di output predefinito a livello di predefinito dalla **console Mappa**.

![](assets/fmdita-output-lc.png)

Quando si lavora con più reparti, è consigliabile creare cartelle specifiche del reparto all&#39;interno della struttura di cartelle `fm-ditaoutputs` per garantire agli utenti di un reparto specifico l&#39;accesso alle cartelle di output pertinenti.

## Creare utenti e assegnarli ai gruppi appropriati

Una volta stabilita la gerarchia delle cartelle, puoi iniziare a creare gli utenti e aggiungerli ai gruppi in modo che possano accedere alle funzioni rilevanti in Experience Manager Guides. Experience Manager Guides fornisce tre gruppi predefiniti: Autori, Revisori e Editori. A seconda del gruppo a cui è associato un utente, questi può eseguire attività specifiche. Ad esempio, un’attività di pubblicazione può essere eseguita solo da un editore, ma non da un autore.

Per creare nuovi utenti e aggiungerli ai gruppi, passa a **Strumenti** > **Sicurezza** > **Utenti**.

Nella pagina Gestione utenti, selezionare **Crea** per creare un nuovo utente. Aggiungi i dettagli utente e assegnali a un gruppo.

![](assets/create-users-page.png)

Per ulteriori dettagli, visualizzare [Amministrazione utente e sicurezza](../cs-install-guide/user-admin-sec.md)


## Assegna autorizzazioni a ogni gruppo di utenti

Dopo aver aggiunto gli utenti ai gruppi appropriati, configura le autorizzazioni a livello di gruppo per garantire che abbiano accesso alle cartelle di authoring e output corrette nell’archivio.

Per assegnare le autorizzazioni, passa a **Strumenti** > **Sicurezza** > **Autorizzazioni**.

Queste autorizzazioni garantiscono che gli utenti possano creare o modificare il contenuto solo all’interno delle cartelle specificate.

Per ulteriori dettagli, visualizzare [Autorizzazioni in AEM](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/security/security#permissions-in-aem).

