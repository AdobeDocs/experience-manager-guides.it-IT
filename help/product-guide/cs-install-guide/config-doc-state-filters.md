---
title: Configurare i filtri dello stato del documento
description: Scopri come configurare i filtri per lo stato del documento
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 4942b914ff278ebcf09d00da32d6f9c7cc4d7ff9
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 0%

---

# Configurare i filtri dello stato del documento

Adobe Experience Manager Guides offre la funzione di eseguire ricerche in un file in base al suo stato corrente del documento. È possibile utilizzare la ricerca con filtro per cercare i file dall&#39;interfaccia del repository per sfogliare i file.

Per configurare i filtri dello stato del documento, effettuare le seguenti operazioni:

1. Accedi a Adobe Experience Manager come amministratore.
1. Seleziona il collegamento Adobe Experience Manager in alto e scegli **Strumenti**.
1. Selezionare **Guide** dall&#39;elenco degli strumenti, quindi selezionare **Profili cartella**.
1. Apri il riquadro **Profilo globale**. Puoi anche selezionare una sezione del profilo di cartella specifica se desideri che queste modifiche vengano applicate solo a tale cartella invece che a livello globale.
1. Passa a **Configurazione editor XML**.
1. Seleziona l&#39;icona **Modifica** in alto.
1. Seleziona l&#39;icona **Scarica** per scaricare il file `ui\_config.json` nel sistema locale.
Nel file `ui\_config.json` scaricato, fare riferimento alla sezione seguente:

       &quot;
       &quot;repositoryFilters&quot;: &lbrack;
       &lbrace;
       &quot;title&quot;: &quot;Stato documento&quot;,
       &quot;property&quot;: &quot;jcr:content/metadata/docstate&quot;,
       &quot;elementi figlio&quot;: &lbrack;
       &lbrace;
       &quot;title&quot;: &quot;Bozza&quot;,
       &quot;valore&quot;: &quot;Bozza&quot;
       &rbrace;,
       &lbrace;
       &quot;title&quot;: &quot;Modifica&quot;,
       &quot;valore&quot;: &quot;Modifica&quot;
       &rbrace;,
       &lbrace;
       &quot;title&quot;: &quot;In-Review&quot;,
       &quot;value&quot;: &quot;In-Review&quot;
       &rbrace;,
       &lbrace;
&rbrace;       &quot;title&quot;: &quot;Approvato&quot;,
       &quot;valore&quot;: &quot;Approvato&quot;
       &rbrace;,
       &lbrace;
&rbrace;       &quot;title&quot;: &quot;Rivisto&quot;,
       &quot;valore&quot;: &quot;Esaminato&quot;
       ,
       &lbrace;
       &quot;title&quot;: &quot;Fine&quot;,
       &quot;valore&quot;: &quot;Fine&quot;
       &rbrace;
       &rbrack;
       &rbrace;
       &rbrack;
       &quot;
   Questo frammento rappresenta i filtri predefiniti per lo stato del documento disponibili in Experience Manager Guides.

1. Puoi personalizzare i valori del filtro in base al flusso di lavoro della tua organizzazione. Ad esempio, per aggiungere uno stato del documento personalizzato **In sospeso**, inserire la voce seguente in `children`:

   ```
   {
       "title": "Pending",
       "value": "Pending"
   }
   ```

1. Una volta aggiornato, salva il file e caricalo.

I filtri configurati vengono visualizzati nel pannello **Filtri** nell&#39;archivio nella home page.

**Argomento padre:**&#x200B;[&#x200B; Personalizza editor Web](conf-web-editor.md)
