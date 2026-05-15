---
title: Imposta l'Editor mappe avanzato come predefinito
description: Scopri come impostare l’Editor mappe avanzato come predefinito
exl-id: 365264ab-f990-42c1-ab79-61a40ecea42f
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/xTRMho5Nhc9KScSAzQIXy5Z6bMAe-ERLjhZMItRyj4k
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 298
ht-degree: 0%

---

# Imposta l&#39;Editor mappe avanzato come predefinito {#id181AI0003PN}

>[!NOTE]
>
> L’Editor mappe di base, precedentemente disponibile in Experience Manager Guides, è stato dichiarato obsoleto a partire dalle versioni 4.3 e 2307. Non è possibile accedere all&#39;Editor mappe di base per creare e gestire mappe DITA.
>Si consiglia di utilizzare l’Editor di mappe avanzato. Advanced Map Editor offre funzioni avanzate e migliori opzioni di personalizzazione. Ulteriori informazioni su come utilizzare [Editor mappe avanzato](../user-guide/map-editor-advanced-map-editor.md).

Per le versioni precedenti alla 4.3 e 2307, Experience Manager Guides viene fornito con un Basic Map Editor e un Advanced Map Editor. Basic Map Editor offre tutte le funzioni necessarie per creare il file di mappa. L’Editor mappe avanzato è molto più ricco di funzioni ed è integrato all’interno dell’Editor web. Advanced Map Editor consente agli autori di creare e modificare file di mappe DITA con un&#39;interfaccia di facile utilizzo.

Per impostazione predefinita, ogni volta che viene creato un nuovo file mappa, questo viene aperto nell&#39;Editor mappa di base. È possibile modificare questo comportamento abilitando l’impostazione per aprire l’Editor mappe avanzato per impostazione predefinita.

Utilizza le istruzioni fornite in [Sostituzioni configurazione](download-install-additional-config-override.md#) per creare il file di configurazione. Nel file di configurazione, fornisci i seguenti dettagli \(property\) per abilitare Basic Map Editor:

| PID | Chiave proprietà | Valore proprietà |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | ``fmdita.hide.oldmapeditor`` | Booleano \(true/false\). Se si desidera utilizzare l&#39;Editor mapping avanzato per impostazione predefinita, impostare questa proprietà su true.<br> **Valore predefinito**: false |

>[!NOTE]
>
> Per impostazione predefinita, quando un autore crea un file di mappa e sceglie di aprirlo per la modifica, viene avviato Basic Map Editor. Quando l’opzione Modifica è selezionata per un file di mappa dall’interfaccia utente di Assets, viene aperta anche nell’editor di mappe di base.

**Argomento padre:**&#x200B;[&#x200B; Personalizza editor Web](conf-web-editor.md)
