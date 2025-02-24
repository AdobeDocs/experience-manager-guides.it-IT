---
title: Personalizza editor web
description: Scopri come personalizzare la visualizzazione delle tabelle incollate nell’editor
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: d03ac6ba3ec8e5c52c31a3239e2043bbae79622e
workflow-type: tm+mt
source-wordcount: '223'
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

