---
title: Genera automaticamente ID elemento
description: Scopri come generare automaticamente gli ID degli elementi
exl-id: a651db7f-228e-4de5-b569-3f1b4f86c418
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 1%

---

# Genera automaticamente ID elemento {#id20CIL40016I}

AEM Guides genera un ID documento per ogni nuovo documento creato. Ad esempio, quando si crea una mappa DITA, all&#39;ID della mappa viene assegnato un ID come `map.ditamap_random_digits`. Puoi anche definire gli elementi ai quali viene generato e assegnato automaticamente un ID.

AEM Guides fornisce semplici impostazioni di configurazione, in cui devi definire gli elementi sui quali viene generato automaticamente un ID e un pattern per l’ID. Per impostazione predefinita, alcuni elementi come `section`, `table`, `ul`, `ol` sono configurati per la generazione automatica dell&#39;ID. È possibile aggiungere altri elementi a questo elenco in modo che, ogni volta che questi elementi vengono inseriti in un documento, AEM Guides generi e assegni un ID in base al modello specificato

Utilizza le istruzioni fornite in [Sostituzioni configurazione](download-install-additional-config-override.md#) per creare il file di configurazione. Nel file di configurazione, fornisci i seguenti dettagli di \(property\) per configurare gli ID degli elementi generati automaticamente:

| PID | Chiave proprietà | Valore proprietà |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.classes` | Specifica un elenco di elementi separati da virgole. <br> **Valore predefinito**: `"topic, section, table, simpletable, fig, image, ul, ol"` |

Per configurare un pattern per l’ID generato automaticamente, crea un file di configurazione con le seguenti proprietà:

| PID | Chiave proprietà | Valore proprietà |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.pattern` | Il valore predefinito per questo campo è `${elementName}_${id}`. Il valore `${elementName}` viene sostituito con il nome dell&#39;elemento. La variabile `${id}` genera un numero sequenziale per l&#39;elemento. Ad esempio, se assegni all&#39;elemento paragrafo gli ID generati automaticamente, il primo paragrafo dell&#39;argomento o del documento otterrà un ID come p\_1, il paragrafo successivo otterrà p\_2 e così via. Tuttavia, in un documento diverso, il processo di generazione ID viene riavviato. Ciò significa che in un documento diverso, gli ID come p\_1 e p\_2 possono essere assegnati agli elementi di paragrafo. **Valore predefinito**: ``${elementName}_${id}`` |

**Argomento padre:**&#x200B;[ Personalizza editor Web](conf-web-editor.md)
