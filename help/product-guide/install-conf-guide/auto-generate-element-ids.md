---
title: Genera automaticamente ID elemento
description: Scopri come generare automaticamente gli ID degli elementi
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 1%

---

# Genera automaticamente ID elemento {#id20CIL40016I}

AEM Guides genera un ID documento per ogni nuovo documento creato. Ad esempio, quando si crea una mappa DITA, all&#39;ID della mappa viene assegnato un ID come `map.ditamap_random_digits`. Puoi anche definire gli elementi ai quali viene generato e assegnato automaticamente un ID.

AEM Guides fornisce semplici impostazioni di configurazione, in cui devi definire gli elementi sui quali viene generato automaticamente un ID e un pattern per l’ID. Per impostazione predefinita, alcuni elementi come `section`, `table`, `ul`, `ol` sono configurati per la generazione automatica dell&#39;ID. Puoi aggiungere altri elementi a questo elenco in modo che, ogni volta che questi elementi vengono inseriti in un documento, AEM Guides generi e assegni un ID in base al modello specificato.

Le seguenti schede forniscono istruzioni per configurare gli elementi in modo che abbiano un ID generato automaticamente in base alla configurazione di Experience Manager Guides: Cloud Service o On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

Utilizza le istruzioni fornite in [Sostituzioni configurazione](download-install-config-override.md#) per creare il file di configurazione. Nel file di configurazione, fornisci i seguenti dettagli di \(property\) per configurare gli ID degli elementi generati automaticamente:

| PID | Chiave proprietà | Valore proprietà |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.classes` | Specifica un elenco di elementi separati da virgole. <br> **Valore predefinito**: `"topic, section, table, simpletable, fig, image, ul, ol"` |

Per configurare un pattern per l’ID generato automaticamente, crea un file di configurazione con le seguenti proprietà:

| PID | Chiave proprietà | Valore proprietà |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.pattern` | Il valore predefinito per questo campo è `${elementName}_${id}`. Il valore `${elementName}` viene sostituito con il nome dell&#39;elemento. La variabile `${id}` genera un numero sequenziale per l&#39;elemento. Ad esempio, se assegni all&#39;elemento paragrafo gli ID generati automaticamente, il primo paragrafo dell&#39;argomento o del documento otterrà un ID come p\_1, il paragrafo successivo otterrà p\_2 e così via. Tuttavia, in un documento diverso, il processo di generazione ID viene riavviato. Ciò significa che in un documento diverso, gli ID come p\_1 e p\_2 possono essere assegnati agli elementi di paragrafo. **Valore predefinito**: ``${elementName}_${id}`` |

>[!TAB On-Premise]

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e fai clic sul bundle **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.

1. Nelle impostazioni *XmlEditorConfig*, specifica uno o più elementi nel campo **Generazione automatica ID per tag elemento**.

   >[!NOTE]
   >
   > I tag elemento sono i nomi degli elementi DITA come `body`, `title`, `codeblock` e così via. Per specificare più elementi, separa i nomi con una virgola.

1. Nel campo **Pattern per la generazione di ID**, specifica un pattern per la generazione di un ID.

   Il valore predefinito per questo campo è `${elementName}_${id}`. Il valore `${elementName}` viene sostituito con il nome dell&#39;elemento. La variabile `${id}` genera un numero sequenziale per l&#39;elemento. Ad esempio, se assegni all&#39;elemento paragrafo gli ID generati automaticamente, il primo paragrafo dell&#39;argomento o del documento otterrà un ID come p\_1, il paragrafo successivo otterrà p\_2 e così via. Tuttavia, in un documento diverso, il processo di generazione ID viene riavviato. Ciò significa che in un documento diverso, gli ID come p\_1 e p\_2 possono essere assegnati agli elementi di paragrafo.

   Se il documento contiene già ID nel modello specificato, il processo di generazione automatica non assegna tali ID ai nuovi elementi.

1. Fai clic su **Salva**.

>[!ENDTABS]

**Argomento padre:**&#x200B;[&#x200B; Personalizza editor Web](customize-overview.md)
