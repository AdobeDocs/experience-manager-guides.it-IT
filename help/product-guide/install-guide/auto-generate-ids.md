---
title: Genera automaticamente ID elemento
description: Scopri come generare automaticamente gli ID degli elementi
exl-id: 8d09ab89-4be5-49f1-9831-9f01c92dc472
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 0%

---

# Genera automaticamente ID elemento {#id20CIL40016I}

AEM Guides genera un ID documento per ogni nuovo documento creato. Ad esempio, quando si crea una mappa DITA, all&#39;ID della mappa viene assegnato un ID come `map.ditamap_random_digits`. Puoi anche definire gli elementi ai quali viene generato e assegnato automaticamente un ID.

AEM Guides fornisce semplici impostazioni di configurazione, in cui devi definire gli elementi sui quali viene generato automaticamente un ID e un pattern per l’ID. Per impostazione predefinita, alcuni elementi come `section`, `table`, `ul`, `ol` sono configurati per la generazione automatica dell&#39;ID. È possibile aggiungere altri elementi a questo elenco in modo che, ogni volta che questi elementi vengono inseriti in un documento, AEM Guides generi e assegni un ID in base al modello specificato

Per configurare gli elementi in modo che abbiano un ID generato automaticamente, effettua le seguenti operazioni:

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


**Argomento padre:**&#x200B;[ Personalizza editor Web](conf-web-editor.md)
