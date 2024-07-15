---
title: Imposta l'Editor mappe avanzato come predefinito
description: Scopri come impostare l’Editor mappe avanzato come predefinito
exl-id: 365264ab-f990-42c1-ab79-61a40ecea42f
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 0%

---

# Imposta l&#39;Editor mappe avanzato come predefinito {#id181AI0003PN}

AEM Guides viene fornito con un Editor di mappe di base e un Editor di mappe avanzato. Basic Map Editor offre tutte le funzioni necessarie per creare il file di mappa. L’Editor mappe avanzato è molto più ricco di funzioni ed è integrato all’interno dell’Editor web. Advanced Map Editor consente agli autori di creare e modificare file di mappe DITA con un&#39;interfaccia di facile utilizzo.

Per impostazione predefinita, ogni volta che viene creato un nuovo file mappa, questo viene aperto nell&#39;Editor mappa di base. È possibile modificare questo comportamento abilitando l’impostazione per aprire l’Editor mappe avanzato per impostazione predefinita.

Utilizza le istruzioni fornite in [Sostituzioni configurazione](download-install-additional-config-override.md#) per creare il file di configurazione. Nel file di configurazione, fornisci i seguenti dettagli \(property\) per abilitare Basic Map Editor:

| PID | Chiave proprietà | Valore proprietà |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | ``fmdita.hide.oldmapeditor`` | Booleano \(true/false\). Se si desidera utilizzare l&#39;Editor mapping avanzato per impostazione predefinita, impostare questa proprietà su true.<br> **Valore predefinito**: false |

>[!NOTE]
>
> Per impostazione predefinita, quando un autore crea un file di mappa e sceglie di aprirlo per la modifica, viene avviato Basic Map Editor. Quando l’opzione Modifica è selezionata per un file di mappa dall’interfaccia utente di Assets, viene aperta anche nell’editor di mappe di base.

**Argomento padre:**[ Personalizza editor Web](conf-web-editor.md)
