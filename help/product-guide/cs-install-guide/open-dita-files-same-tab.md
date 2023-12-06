---
title: Aprire un argomento DITA o mappare i file nella stessa scheda
description: Scopri come aprire un argomento DITA o mappare i file nella stessa scheda
exl-id: 466cbea4-c75a-488e-bde2-465cf2c184d5
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 0%

---

# Aprire un argomento DITA o mappare i file nella stessa scheda {#id223HH0301J3}

In alcuni flussi di lavoro, quando fai clic su un collegamento di un argomento o di un file di mappa, questo si apre in una nuova scheda. Questo potrebbe comportare l’apertura di molte schede nel browser, con un conseguente impatto sulla produttività. È possibile modificare questo comportamento di apertura di un file argomento o mappa in una nuova scheda e forzarne l&#39;apertura nella scheda corrente.

Utilizzare le istruzioni fornite in [Sostituzioni configurazione](download-install-additional-config-override.md#) per creare il file di configurazione. Nel file di configurazione, fornisci i seguenti dettagli \(property\) per aprire un file argomento o mappa in una nuova scheda:

| PID | Chiave proprietà | Valore proprietà |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.openinsametab` | Booleano \(true/false\). <br> **Valore predefinito**: `false` |

Questa impostazione ha effetto sui seguenti punti da cui è possibile accedere ai file argomento o mappa:

- Crea argomento DITA \(alla fine del flusso di lavoro, quando si fa clic su **Apri argomento** button\)

- Crea mappa DITA \(alla fine del flusso di lavoro, quando si fa clic su **Apri mappa** button\)

- Scheda Argomenti nella console Mappa DITA

- Scheda Baseline nella console delle mappe DITA

- Scheda Rapporti nella console delle mappe DITA


**Argomento padre:**[ Personalizza editor web](conf-web-editor.md)
