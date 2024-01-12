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

Le guide AEM generano un ID documento per ogni nuovo documento creato. Ad esempio, quando si crea una mappa DITA, un ID come `map.ditamap_random_digits` viene assegnato all’ID della mappa. Puoi anche definire gli elementi ai quali viene generato e assegnato automaticamente un ID.

Le guide AEM forniscono semplici impostazioni di configurazione in cui è necessario definire gli elementi sui quali viene generato automaticamente un ID e un pattern per l’ID. Per impostazione predefinita, alcuni elementi come `section`, `table`, `ul`, `ol`, sono configurate per la generazione automatica dell&#39;ID. È possibile aggiungere altri elementi all&#39;elenco in modo che, ogni volta che questi elementi vengono inseriti in un documento, le guide AEM generino e assegnino un ID in base al modello specificato

Per configurare gli elementi in modo che abbiano un ID generato automaticamente, effettua le seguenti operazioni:

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e fai clic su **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** pacchetto.

1. In *XmlEditorConfig* , specificare uno o più elementi nel **Genera automaticamente ID per i tag elemento** campo.

   >[!NOTE]
   >
   > I tag elemento sono i nomi degli elementi DITA, ad esempio `body`, `title`, `codeblock`e così via. Per specificare più elementi, separa i nomi con una virgola.

1. In **Pattern per la generazione di ID** , specifica un pattern per generare un ID.

   Il valore predefinito per questo campo è impostato su `${elementName}_${id}`. Il `${elementName}` viene sostituito con il nome dell’elemento. Il `${id}` variabile genera un numero sequenziale per l’elemento. Ad esempio, se assegni all&#39;elemento paragrafo gli ID generati automaticamente, il primo paragrafo dell&#39;argomento o del documento otterrà un ID come p\_1, il paragrafo successivo otterrà p\_2 e così via. Tuttavia, in un documento diverso, il processo di generazione ID viene riavviato. Ciò significa che in un documento diverso, gli ID come p\_1 e p\_2 possono essere assegnati agli elementi di paragrafo.

   Se il documento contiene già ID nel modello specificato, il processo di generazione automatica non assegna tali ID ai nuovi elementi.

1. Fai clic su **Salva**.


**Argomento padre:**[ Personalizza editor web](conf-web-editor.md)
