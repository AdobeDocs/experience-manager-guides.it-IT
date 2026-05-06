---
title: Configurare l’elenco da ignorare delle proprietà dei metadati
description: Scopri come configurare l’elenco da ignorare per le proprietà dei metadati in AEM Guides.
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: f74c71d6a4a293bfbae55e9e57c62b7478d0a88a
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 1%

---

# Configurare l’elenco da ignorare delle proprietà dei metadati

Quando si modifica un file, eventuali modifiche ai campi di metadati disponibili in **Proprietà file** o applicate nel back-end attivano l&#39;asterisco (*) nella versione del documento. Per evitare che gli aggiornamenti dei metadati generati dal sistema influiscano su questo indicatore, gli amministratori possono configurare un elenco da ignorare per le proprietà dei metadati.

Utilizza le istruzioni fornite in [Sostituzioni configurazione](download-install-config-override.md#) per creare il file di configurazione. Nel file di configurazione, fornisci i seguenti dettagli (proprietà) per configurare l&#39;opzione **Ignora proprietà metadati per versione dirty**:


| PID | Chiave proprietà | Valore proprietà |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.dirtychecker.ignoremetadata` | `<comma-separated list / array of metadata properties>` |

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
