---
title: Tradurre i contenuti nelle guide AEM
description: Scopri come tradurre i contenuti
exl-id: 0d3a909c-3499-4ef4-b033-02e412dae959
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '707'
ht-degree: 9%

---

# Tradurre il contenuto {#id181GB0400UI}

Automatizza la traduzione di contenuti di pagina, risorse e contenuti generati dall&#39;utente per creare e gestire siti web multilingue. Per automatizzare i flussi di lavoro di traduzione, puoi integrare fornitori di servizi di traduzione con AEM e creare progetti per la traduzione dei contenuti in più lingue. AEM supporta flussi di lavoro di traduzione umana e automatica.

- Traduzione umana: il contenuto viene inviato al tuo provider di traduzioni e tradotto da traduttori professionisti. Una volta completato, il contenuto tradotto viene rinviato e importato in AEM. Quando il fornitore di traduzione è integrato con l&#39;AEM, i contenuti vengono scambiati automaticamente tra l&#39;AEM e il fornitore di traduzione

- Traduzione automatica: il servizio di traduzione automatica traduce immediatamente il contenuto


La traduzione del contenuto prevede i seguenti passaggi:

1. Connettere l’AEM con il [fornitore di servizi di traduzione](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-tic.html#ConnectingtoaTranslationServiceProvider) e creare [configurazioni framework integrazione traduzione](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-tic.html#CreatingaTranslationIntegrationConfiguration).

1. Associa le pagine della lingua master con [servizi di traduzione e configurazioni framework](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-tic.html#ConfiguringPagesforTranslation).

1. Identificare il tipo di [contenuto da tradurre](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-rules.html).

1. [Prepara il contenuto per la traduzione](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-prep.html) creando la lingua master e le pagine root delle copie in lingua.

1. Crea [progetti di traduzione](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-manage.html) per raccogliere il contenuto da tradurre e preparare il processo di traduzione.

1. Utilizza i progetti di traduzione per [gestire la traduzione dei contenuti](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-manage.html) processo.


Se il fornitore di servizi di traduzione non fornisce un connettore per l’integrazione con l’AEM, l’AEM supporta l’esportazione e l’importazione manuale dei contenuti tradotti in formato XML.

>[!TIP]
>
> Consulta la *Traduzione* s sezione nella guida alle best practice per le best practice sulla traduzione dei contenuti.

## Configurare la scheda Traduzione nel dashboard delle mappe DITA

L&#39;opzione Nascondi scheda di traduzione non è attivata per impostazione predefinita ed è necessario attivarla da configMgr. Per nascondere la scheda Traduzione nel dashboard delle mappe DITA, effettuare le seguenti operazioni:

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e fai clic su **com.adobe.fmdita.config.ConfigManager** pacchetto.

1. Seleziona la **Nascondi scheda traduzione** per nascondere la scheda traslazione nel dashboard mappa.

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

1. Cerca e fai clic su **com.adobe.fmdita.config.ConfigManager** pacchetto.

1. Configurare **Flusso di lavoro di traduzione DITA basato su componenti** in base alla configurazione:

   - Se utilizzi la traduzione umana, allora *Disattiva* il **Flusso di lavoro di traduzione basato su componenti** opzione.

   - Se utilizzi la traduzione automatica, allora *Abilita* il **Flusso di lavoro di traduzione basato su componenti** opzione.

   >[!NOTE]
   >
   > Se utilizzi un connettore di traduzione, accertati di averlo configurato come descritto in *[Configurazione del framework di integrazione della traduzione](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-tic.html)* argomento nella documentazione AEM.

1. Fai clic su **Salva**.


>[!IMPORTANT]
>
> Dopo aver impostato le configurazioni di traduzione, accertati di impostare la configurazione cloud appropriata nelle cartelle delle lingue.

## Configurare la post-elaborazione di copie per lingua temporanee

Quando avvii il flusso di lavoro di traduzione, il sistema crea copie temporanee in lingua del contenuto sorgente. Puoi scegliere di abilitare o disabilitare l’operazione di post-elaborazione su questi file temporanei. Nell’operazione di post-elaborazione, i riferimenti in entrata e in uscita dai file vengono risolti, lo stato del documento viene impostato, insieme ad altre operazioni. Se abiliti la post-elaborazione in questi file temporanei, il completamento del processo di traduzione potrebbe richiedere più tempo. Pertanto, si consiglia di mantenere disabilitata l’opzione di post-elaborazione.

Per impostazione predefinita, l’opzione di post-elaborazione dei file temporanei è disabilitata. Per configurare questa opzione, effettua le seguenti operazioni:

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e fai clic su **com.adobe.fmdita.config.ConfigManager** pacchetto.

1. Configurare **Copie per lingua post-elaborazione** in base alla configurazione:

   - \(*Predefinito*\) Se non si desidera eseguire l&#39;operazione di post-elaborazione sui file temporanei, *Disattiva* il **Copie per lingua post-elaborazione** opzione.

   - Se si desidera eseguire l&#39;operazione di post-elaborazione sui file temporanei, *Abilita* il **Copie per lingua post-elaborazione** opzione.

1. Fai clic su **Salva**.
