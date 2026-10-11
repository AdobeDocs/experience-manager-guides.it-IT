---
title: Configurare l’elenco da ignorare delle proprietà dei metadati
description: Scopri come configurare l’elenco da ignorare per le proprietà dei metadati in AEM Guides.
feature: Web Editor Configuration
role: Admin
level: Experienced
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
    internal-label: Web Editor configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 0%
---
# Configurare l’elenco da ignorare delle proprietà dei metadati

Quando si modifica un file, eventuali modifiche ai campi di metadati disponibili in **Proprietà file** o applicate nel back-end attivano l&#39;asterisco (*) nella versione del documento. Per evitare che gli aggiornamenti dei metadati generati dal sistema influiscano su questo indicatore, gli amministratori possono configurare un elenco da ignorare per le proprietà dei metadati.

>[!BEGINTABS]

>[!TAB Cloud Service]

Utilizza le istruzioni fornite in [Sostituzioni configurazione](download-install-config-override.md#) per creare il file di configurazione. Nel file di configurazione, fornisci i seguenti dettagli (proprietà) per configurare l&#39;opzione **Ignora proprietà metadati per versione dirty**.


| PID | Chiave proprietà | Valore proprietà |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.dirtychecker.ignoremetadata` | `<comma-separated list / array of metadata properties>` |

>[!TAB On-Premise]

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e fai clic sul bundle **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.

1. Nelle impostazioni *XmlEditorConfig*, passa all&#39;opzione **Ignora proprietà metadati per versione dirty**.

   Rivedi l’elenco delle proprietà dei metadati predefinite attualmente configurate per essere ignorate.

1. Aggiungi o rimuovi le proprietà dei metadati in base ai requisiti.
1. Seleziona **Salva** per salvare la configurazione aggiornata.


>[!ENDTABS]

## Proprietà metadati predefinite nell&#39;elenco da ignorare

AEM Guides include un set predefinito di proprietà dei metadati nell’elenco da ignorare. Puoi modificare questo elenco per aggiungere o rimuovere le proprietà dei metadati in base alle esigenze.

* &quot;jcr:mixinTypes&quot;,
* &quot;jcr:primaryType&quot;,
* &quot;jcr:frozenMixinTypes&quot;,
* &quot;jcr:frozenPrimaryType&quot;,
* &quot;jcr:frozenUuid&quot;,
* &quot;jcr:uuid&quot;,
* &quot;dam:extracted&quot;,
* &quot;jcr:lastModified&quot;,
* &quot;jcr:lastModifiedBy&quot;,
* &quot;dc:modified&quot;,
* &quot;dam:sha1&quot;,
* &quot;dam:size&quot;,
* &quot;guide:wordCount&quot;,
* &quot;dam:scene7UploadTimeStamp&quot;,
* &quot;dam:scene7LastModified&quot;

Solo le proprietà dei metadati non incluse nell&#39;elenco da ignorare vengono considerate per contrassegnare la versione di un documento come non valida.

**Argomento padre:**[ Personalizza editor](customize-overview.md)
