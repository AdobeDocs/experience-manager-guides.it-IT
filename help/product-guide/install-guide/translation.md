---
title: Tradurre il contenuto in AEM Guides
description: Scopri come tradurre i contenuti
exl-id: 0d3a909c-3499-4ef4-b033-02e412dae959
feature: Translation
role: Admin
level: Experienced
source-git-commit: ea3083542e955a56c27cd833600370a7962c6b8d
workflow-type: tm+mt
source-wordcount: '854'
ht-degree: 8%

---

# Tradurre il contenuto {#id181GB0400UI}

Automatizza la traduzione di contenuti di pagina, risorse e contenuti generati dall&#39;utente per creare e gestire siti web multilingue. Per automatizzare i flussi di lavoro di traduzione, puoi integrare fornitori di servizi di traduzione con AEM e creare progetti per la traduzione dei contenuti in più lingue. AEM supporta flussi di lavoro di traduzione umana e automatica.

- Traduzione umana: il contenuto viene inviato al tuo provider di traduzioni e tradotto da traduttori professionisti. Una volta completato, il contenuto tradotto viene rinviato e importato in AEM. Quando il fornitore di traduzione è integrato con l&#39;AEM, i contenuti vengono scambiati automaticamente tra l&#39;AEM e il fornitore di traduzione

- Traduzione automatica: il servizio di traduzione automatica traduce immediatamente il contenuto


La traduzione del contenuto prevede i seguenti passaggi:

1. Connetti AEM al tuo [fornitore di servizi di traduzione](https://helpx.adobe.com/it/experience-manager/6-5/sites/administering/using/tc-tic.html#ConnectingtoaTranslationServiceProvider) e crea [configurazioni del framework di integrazione della traduzione](https://helpx.adobe.com/it/experience-manager/6-5/sites/administering/using/tc-tic.html#CreatingaTranslationIntegrationConfiguration).

1. Associa le pagine della lingua master con il [servizio di traduzione e le configurazioni del framework](https://helpx.adobe.com/it/experience-manager/6-5/sites/administering/using/tc-tic.html#ConfiguringPagesforTranslation).

1. Identificare il tipo di [contenuto da tradurre](https://helpx.adobe.com/it/experience-manager/6-5/sites/administering/using/tc-rules.html).

1. [Prepara il contenuto per la traduzione](https://helpx.adobe.com/it/experience-manager/6-5/sites/administering/using/tc-prep.html) creando la lingua master e le pagine root delle copie in lingua.

1. Crea [progetti di traduzione](https://helpx.adobe.com/it/experience-manager/6-5/sites/administering/using/tc-manage.html) per raccogliere il contenuto da tradurre e preparare il processo di traduzione.

1. Utilizza i progetti di traduzione per [gestire il processo di traduzione del contenuto](https://helpx.adobe.com/it/experience-manager/6-5/sites/administering/using/tc-manage.html).


Se il fornitore di servizi di traduzione non fornisce un connettore per l’integrazione con l’AEM, l’AEM supporta l’esportazione e l’importazione manuale dei contenuti tradotti in formato XML.

>[!TIP]
>
> Consulta la sezione *Traduzione* s nella guida alle best practice per le best practice sulla traduzione dei contenuti.

## Configurare la scheda Traduzione nel dashboard delle mappe DITA

L&#39;opzione Nascondi scheda di traduzione non è attivata per impostazione predefinita ed è necessario attivarla da configMgr. Per nascondere la scheda Traduzione nel dashboard delle mappe DITA, effettuare le seguenti operazioni:

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e fai clic sul bundle **com.adobe.fmdita.config.ConfigManager**.

1. Selezionare l&#39;opzione **Nascondi scheda di traduzione** per nascondere la scheda di traduzione nel dashboard delle mappe.

   >[!NOTE]
   >
   > Questa proprietà è disabilitata per impostazione predefinita e la scheda di traduzione è disponibile nel dashboard delle mappe.

1. Fai clic su **Salva**.

## Configurare il flusso di lavoro di traduzione basato su componenti

Se il connettore per il fornitore di traduzione non supporta il contenuto DITA, è necessario abilitare il flusso di lavoro di traduzione basato su componenti. Una volta abilitato, il contenuto traducibile viene inviato come metadati della risorsa. Tuttavia, affinché questo flusso di lavoro funzioni, il connettore deve supportare la traduzione dei metadati delle risorse.

In base al flusso di lavoro di traduzione utilizzato nella configurazione, l’opzione del flusso di lavoro di traduzione basato su componenti deve essere configurata come segue:

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e fai clic sul bundle **com.adobe.fmdita.config.ConfigManager**.

1. Configura l&#39;opzione **Flusso di lavoro di traduzione DITA basato su componenti** in base alla configurazione:

   - Se utilizzi una traduzione umana, *Disattiva* l&#39;opzione **Flusso di lavoro di traduzione basato su componenti**.

   - Se utilizzi la traduzione automatica, *Abilita* l&#39;opzione **Flusso di lavoro di traduzione basato su componenti**.

   >[!NOTE]
   >
   > Se utilizzi il connettore di traduzione, accertati di averlo configurato come descritto nell&#39;argomento *[Configurazione del framework di integrazione della traduzione](https://helpx.adobe.com/it/experience-manager/6-5/sites/administering/using/tc-tic.html)* nella documentazione AEM.

1. Fai clic su **Salva**.

>[!IMPORTANT]
>
> Dopo aver impostato le configurazioni di traduzione, accertati di impostare la configurazione cloud appropriata nelle cartelle delle lingue.

## Configurare il flusso di lavoro di traduzione legacy

>[!IMPORTANT]
> 
> Per prestazioni avanzate, si consiglia di utilizzare il flusso di lavoro di traduzione più recente, disponibile in AEM Guides 4.6.0 e versioni successive. Tuttavia, se hai abilitato una personalizzazione nel processo di traduzione e questo è influenzato dal nuovo flusso di lavoro, puoi considerare il ripristino del flusso di lavoro di traduzione legacy come soluzione alternativa.



Per impostazione predefinita, l’opzione del flusso di lavoro di traduzione legacy è disabilitata. Puoi configurare questa opzione eseguendo i seguenti passaggi:

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e fai clic sul bundle **com.adobe.fmdita.config.ConfigManager**.

1. Configura l’opzione del flusso di lavoro di traduzione legacy in base alla configurazione:

   - (*Predefinito*) Se desideri utilizzare il flusso di lavoro di traduzione più recente, disabilita l&#39;opzione **Esegui flusso di lavoro di traduzione legacy**.
   - Se desideri utilizzare il flusso di lavoro di traduzione legacy, abilita l&#39;opzione **Esegui flusso di lavoro di traduzione legacy**.

1. Fai clic su **Salva**.






<!---

This was added for 2406 CS IG

## Configure the legacy translation workflow 

It is recommended that you use the latest translation workflow, which provides enhanced performance. However, you can configure the legacy translation workflow if necessary.

Based on the translation workflow used in your setup, provide the following (property) details to configure the legacy translation workflow: the component-based translation workflow option should be configured as follows:

1.  Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ! Add the syntax of http as given in previous config

    Note: Configure htttp code as given in previous sample
    

1.  Search for and click on the **com.adobe.fmdita.config.ConfigManager** bundle.



1.  Configure the **Run legacy translation workflow** option as per your setup:

    -   If you use the latest translation workflow, then *Disable* \( `false`\) the **Run legacy translation workflow** option. The latest translation workflow is enabled by default. <br> 

    -   If you use the legacy translation, then *Enable \( `true`\)* the **Run legacy translation workflow** option.

1.  Click **Save**.


--->


## Configurare la post-elaborazione di copie per lingua temporanee

Quando avvii il flusso di lavoro di traduzione, il sistema crea copie temporanee in lingua del contenuto sorgente. Puoi scegliere di abilitare o disabilitare l’operazione di post-elaborazione su questi file temporanei. Nell’operazione di post-elaborazione, i riferimenti in entrata e in uscita dai file vengono risolti, lo stato del documento viene impostato, insieme ad altre operazioni. Se abiliti la post-elaborazione in questi file temporanei, il completamento del processo di traduzione potrebbe richiedere più tempo. Pertanto, si consiglia di mantenere disabilitata l’opzione di post-elaborazione.

Per impostazione predefinita, l’opzione di post-elaborazione dei file temporanei è disabilitata. Per configurare questa opzione, effettua le seguenti operazioni:

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e fai clic sul bundle **com.adobe.fmdita.config.ConfigManager**.

1. Configura l&#39;opzione **Copie per lingua post-elaborazione** in base alla configurazione:

   - \(*Predefinito*\) Se non si desidera eseguire l&#39;operazione di post-elaborazione sui file temporanei, *Disabilita* l&#39;opzione **Copie per lingua post-elaborazione**.

   - Se desideri eseguire l&#39;operazione di post-elaborazione sui file temporanei, *Abilita* l&#39;opzione **Copie per lingua post-elaborazione**.

1. Fai clic su **Salva**.
