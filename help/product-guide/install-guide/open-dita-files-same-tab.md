---
title: Aprire un argomento DITA o mappare i file nella stessa scheda
description: Scopri come aprire un argomento DITA o mappare i file nella stessa scheda
exl-id: 81ad2e18-3ea7-4cc1-8387-d703d1038a18
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 0%

---

# Aprire un argomento DITA o mappare i file nella stessa scheda {#id223HI0P202H}

In alcuni flussi di lavoro, quando fai clic su un collegamento di un argomento o di un file di mappa, questo si apre in una nuova scheda. Questo potrebbe comportare l’apertura di molte schede nel browser, con un conseguente impatto sulla produttività. È possibile modificare questo comportamento di apertura di un file argomento o mappa in una nuova scheda e forzarne l&#39;apertura nella scheda corrente. A questo scopo, esegui le seguenti modifiche di configurazione:

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e fai clic su **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** pacchetto.

1. Seleziona la **Apri argomento/mappa DITA nella stessa scheda** opzione.

1. Fai clic su **Salva**.


Questa impostazione ha effetto sui seguenti punti da cui è possibile accedere ai file argomento o mappa:

- Crea argomento DITA \(alla fine del flusso di lavoro, quando si fa clic su **Apri argomento** button\)

- Crea mappa DITA \(alla fine del flusso di lavoro, quando si fa clic su **Apri mappa** button\)

- Scheda Argomenti nella console Mappa DITA

- Scheda Baseline nella console delle mappe DITA

- Scheda Rapporti nella console delle mappe DITA


**Argomento padre:**[ Personalizza editor web](conf-web-editor.md)
