---
title: Genera automaticamente ID elemento
description: Scopri come generare automaticamente gli ID degli elementi
exl-id: a651db7f-228e-4de5-b569-3f1b4f86c418
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/xnUjt33qyeXgxwIH3L2t08FShHaicDSVVvXQQNGytI4
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 291
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

**Argomento padre:**&#x200B;[&#x200B; Personalizza editor Web](conf-web-editor.md)
