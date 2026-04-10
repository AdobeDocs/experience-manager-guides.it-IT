---
title: Configurare l’opzione da modificare in Ossigeno
description: Scopri come configurare l’opzione da modificare nel plug-in del connettore ossigeno.
exl-id: 96081a6d-39cf-4697-8b43-6494543ea187
feature: Web Editor Configuration
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 3aadc59f5034828cf319992b7acb32d5a88eaf93
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 1%

---

# Configurare l’opzione da modificare in Ossigeno

AEM Guides consente inoltre agli utenti di modificare gli argomenti e le mappe DITA nel plug-in del connettore ossigeno.

Utilizza le istruzioni fornite in [Sostituzioni configurazione](download-install-additional-config-override.md#) per creare il file di configurazione. Nel file di configurazione, fornisci i seguenti dettagli (proprietà) per configurare l&#39;opzione **Modifica in ossigeno**:



| PID | Chiave proprietà | Valore proprietà |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.editinoxygen` | Booleano \(true/false\). **Valore predefinito**: false |

>[!NOTE]
>
> Questa configurazione è disabilitata per impostazione predefinita e l’opzione non è disponibile nell’editor web.

**Argomento padre:**[ Personalizza editor Web](conf-web-editor.md)
