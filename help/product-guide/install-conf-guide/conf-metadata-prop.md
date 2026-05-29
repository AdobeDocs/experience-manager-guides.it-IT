---
title: Configurare l’elenco da ignorare delle proprietà dei metadati
description: Scopri come configurare l’elenco da ignorare per le proprietà dei metadati in AEM Guides.
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 8e8b24bea8504ad9fcca1117bd9e7b400e757dff
workflow-type: tm+mt
source-wordcount: '251'
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

**Argomento padre:**[ Personalizza editor Web](customize-overview.md)
