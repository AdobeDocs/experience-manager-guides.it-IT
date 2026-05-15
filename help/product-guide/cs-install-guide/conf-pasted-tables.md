---
title: Personalizza editor web
description: Scopri come personalizzare la visualizzazione delle tabelle incollate nell’editor
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 839128b4-4889-4c61-b1c0-214ba1d3165e
TQID: https://experienceleague.adobe.com/0g3LyLfKxZEbtl968wJK6r1xPHRjagayeBF4xSvJF6c
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 223
ht-degree: 0%

---

# Configurare la visualizzazione delle tabelle incollate

Utilizzando la barra degli strumenti secondaria nell&#39;editor, è possibile inserire una tabella semplice nella posizione valida corrente o successiva di un argomento. È inoltre possibile copiare una tabella da Microsoft Word o Excel e incollarla direttamente in un file di argomento.

Gli amministratori possono configurare la visualizzazione delle tabelle copiate. Per impostazione predefinita, tali tabelle copiate vengono visualizzate come `simpletable` nell&#39;editor. È tuttavia possibile modificare questa impostazione per visualizzare le tabelle copiate come `tgroup` aggiornando l&#39;impostazione di configurazione dell&#39;editor XML.

>[!NOTE]
>
> Se si copia una tabella con righe o colonne unite, la tabella verrà incollata come tabella normale `trgoup` e non `simpletable` indipendentemente dall&#39;impostazione della tabella configurata nella configurazione dell&#39;editor XML.

Per aggiornare il formato di tabella predefinito, effettuare le seguenti operazioni:

1. Apri la pagina Navigazioni Adobe Experience Manager e seleziona **Strumenti** a sinistra.
2. Nel pannello Strumenti, seleziona **Guide** dall&#39;elenco degli strumenti.
3. Selezionare **Profili cartella**, quindi selezionare il profilo in cui si desidera aggiornare l&#39;impostazione della tabella.
4. Passare alla scheda **Configurazione editor XML**.
5. Seleziona l&#39;icona **Modifica** in alto.
6. Seleziona l&#39;icona **Scarica** per scaricare il file `ui_config.json` nel sistema locale.
7. Nel file `ui_config.json`, aggiornare l&#39;impostazione `simpletable` come illustrato di seguito:

   ```
   "htmlToDitaMapping":{ "table": {
   "name" : "tgroup",
   "wrapTag" : {
       "dita" : "table",
       "html" : "div"
   }
   } },
   ```


Una volta aggiornato, salva il file e caricalo.
