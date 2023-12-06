---
title: Imposta l'Editor mappe avanzato come predefinito
description: Scopri come impostare l’Editor mappe avanzato come predefinito
exl-id: 365264ab-f990-42c1-ab79-61a40ecea42f
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 0%

---

# Imposta l&#39;Editor mappe avanzato come predefinito {#id181AI0003PN}

AEM Guides è dotato di un Basic Map Editor e di un Advanced Map Editor. Basic Map Editor offre tutte le funzioni necessarie per creare il file di mappa. L’Editor mappe avanzato è molto più ricco di funzioni ed è integrato all’interno dell’Editor web. Advanced Map Editor consente agli autori di creare e modificare file di mappe DITA con un&#39;interfaccia di facile utilizzo.

Per impostazione predefinita, ogni volta che viene creato un nuovo file mappa, questo viene aperto nell&#39;Editor mappa di base. È possibile modificare questo comportamento abilitando l’impostazione per aprire l’Editor mappe avanzato per impostazione predefinita.

Utilizzare le istruzioni fornite in [Sostituzioni configurazione](download-install-additional-config-override.md#) per creare il file di configurazione. Nel file di configurazione, fornisci i seguenti dettagli \(property\) per abilitare Basic Map Editor:

| PID | Chiave proprietà | Valore proprietà |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | ``fmdita.hide.oldmapeditor`` | Booleano \(true/false\). Se si desidera utilizzare l&#39;Editor mapping avanzato per impostazione predefinita, impostare questa proprietà su true.<br> **Valore predefinito**: false |

>[!NOTE]
>
> Per impostazione predefinita, quando un autore crea un file di mappa e sceglie di aprirlo per la modifica, viene avviato Basic Map Editor. Quando l’opzione Modifica è selezionata per un file di mappa dall’interfaccia utente Assets, viene aperta anche nell’editor di mappe di base.

**Argomento padre:**[ Personalizza editor web](conf-web-editor.md)
