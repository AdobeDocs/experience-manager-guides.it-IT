---
title: Configurare l’opzione da modificare in Ossigeno
description: Scopri come configurare l’opzione da modificare nel plug-in del connettore ossigeno.
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 41ecbbb2-81c3-473d-b48b-7370a74a6474
source-git-commit: cc73b81787a3c3dbe8390d93e558064327e59965
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 1%

---

# Configurare l’opzione da modificare in Ossigeno per Cloud Service

AEM Guides consente inoltre agli utenti di modificare gli argomenti e le mappe DITA nel plug-in del connettore ossigeno.

Utilizza le istruzioni fornite in [Sostituzioni configurazione](download-install-config-override.md#) per creare il file di configurazione. Nel file di configurazione, fornisci i seguenti dettagli (proprietà) per configurare l&#39;opzione **Modifica in ossigeno**:



| PID | Chiave proprietà | Valore proprietà |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.editinoxygen` | Booleano \(true/false\). **Valore predefinito**: false |

>[!NOTE]
>
> Questa configurazione è disabilitata per impostazione predefinita e l’opzione non è disponibile nell’editor.

**Argomento padre:**[ Personalizza editor](customize-overview.md)
