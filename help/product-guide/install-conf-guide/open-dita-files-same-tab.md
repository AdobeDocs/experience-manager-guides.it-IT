---
title: Aprire un argomento DITA o mappare i file nella stessa scheda
description: Scopri come aprire un argomento DITA o mappare i file nella stessa scheda
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 1%

---

# Aprire un argomento DITA o mappare i file nella stessa scheda {#id223HI0P202H}

In alcuni flussi di lavoro, quando fai clic su un collegamento di un argomento o di un file di mappa, questo si apre in una nuova scheda. Questo potrebbe comportare l’apertura di molte schede nel browser, con un conseguente impatto sulla produttività. È possibile modificare questo comportamento di apertura di un file argomento o mappa in una nuova scheda e forzarne l&#39;apertura nella scheda corrente.

Le schede seguenti forniscono istruzioni per aprire un argomento DITA o un file di mappa nella stessa scheda in base alla configurazione di Experience Manager Guides: Cloud Service o On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

Utilizza le istruzioni fornite in [Sostituzioni configurazione](download-install-config-override.md#) per creare il file di configurazione. Nel file di configurazione, fornisci i seguenti dettagli \(property\) per aprire un file argomento o mappa in una nuova scheda:

| PID | Chiave proprietà | Valore proprietà |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.openinsametab` | Booleano \(true/false\). <br> **Valore predefinito**: `false` |

>[!TAB On-Premise]

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e fai clic sul bundle **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.

1. Selezionare l&#39;opzione **Apri argomento/mappa DITA nella stessa scheda**.

1. Fai clic su **Salva**.

>[!ENDTABS]

Questa impostazione ha effetto sui seguenti punti da cui è possibile accedere ai file argomento o mappa:

- Crea argomento DITA \(alla fine del flusso di lavoro, quando si fa clic sul pulsante **Apri argomento**\)

- Crea mappa DITA \(alla fine del flusso di lavoro, quando si fa clic sul pulsante **Apri mappa**\)

- Scheda Argomenti nella console Mappa DITA

- Scheda Baseline nella console delle mappe DITA

- Scheda Rapporti nella console delle mappe DITA

**Argomento padre:**&#x200B;[&#x200B; Personalizza editor Web](customize-overview.md)
