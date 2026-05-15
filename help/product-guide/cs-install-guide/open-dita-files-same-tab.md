---
title: Aprire un argomento DITA o mappare i file nella stessa scheda
description: Scopri come aprire un argomento DITA o mappare i file nella stessa scheda
exl-id: 466cbea4-c75a-488e-bde2-465cf2c184d5
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/futODy2B62sg-Epb4bnmxHVAOUVoGDoKg5WJWV-7bpM
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
  - id: d90290ec-3e61-4ebd-8649-bcafe0836803
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 207
ht-degree: 0%

---

# Aprire un argomento DITA o mappare i file nella stessa scheda {#id223HH0301J3}

In alcuni flussi di lavoro, quando fai clic su un collegamento di un argomento o di un file di mappa, questo si apre in una nuova scheda. Questo potrebbe comportare l’apertura di molte schede nel browser, con un conseguente impatto sulla produttività. È possibile modificare questo comportamento di apertura di un file argomento o mappa in una nuova scheda e forzarne l&#39;apertura nella scheda corrente.

Utilizza le istruzioni fornite in [Sostituzioni configurazione](download-install-additional-config-override.md#) per creare il file di configurazione. Nel file di configurazione, fornisci i seguenti dettagli \(property\) per aprire un file argomento o mappa in una nuova scheda:

| PID | Chiave proprietà | Valore proprietà |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.openinsametab` | Booleano \(true/false\). <br> **Valore predefinito**: `false` |

Questa impostazione ha effetto sui seguenti punti da cui è possibile accedere ai file argomento o mappa:

- Crea argomento DITA \(alla fine del flusso di lavoro, quando si fa clic sul pulsante **Apri argomento**\)

- Crea mappa DITA \(alla fine del flusso di lavoro, quando si fa clic sul pulsante **Apri mappa**\)

- Scheda Argomenti nella console Mappa DITA

- Scheda Baseline nella console delle mappe DITA

- Scheda Rapporti nella console delle mappe DITA


**Argomento padre:**&#x200B;[&#x200B; Personalizza editor Web](conf-web-editor.md)
