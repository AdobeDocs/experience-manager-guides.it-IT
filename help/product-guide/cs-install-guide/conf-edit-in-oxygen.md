---
title: Configurare l’opzione da modificare in Ossigeno
description: Scopri come configurare l’opzione da modificare nel plug-in del connettore ossigeno.
exl-id: 96081a6d-39cf-4697-8b43-6494543ea187
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 1%

---

# Configurare l’opzione da modificare in Ossigeno

Le guide AEM consentono inoltre agli utenti di modificare gli argomenti e le mappe DITA nel plugin del connettore ossigeno.

Utilizzare le istruzioni fornite in [Sostituzioni configurazione](download-install-additional-config-override.md#) per creare il file di configurazione. Nel file di configurazione, fornisci i seguenti dettagli (proprietà) per configurare **Modifica in ossigeno** opzione:



| PID | Chiave proprietà | Valore proprietà |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.editinoxygen` | Booleano \(true/false\). **Valore predefinito**: false |

>[!NOTE]
>
> Questa configurazione è disabilitata per impostazione predefinita e l’opzione non è disponibile nell’editor web.

**Argomento padre:**[ Personalizza editor web](conf-web-editor.md)
