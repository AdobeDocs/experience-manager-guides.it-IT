---
title: Note sulla versione | Problemi risolti in Adobe Experience Manager Guides, versione 2024.2.0
description: Scopri le correzioni di bug nella versione 2024.2.0 di Adobe Experience Manager Guides as a Cloud Service.
exl-id: fae1ff07-6232-4e9a-a89e-5e760e807b9d
TQID: https://experienceleague.adobe.com/z-L0sZ2HH720nI3LyDjiIqujxSBP-QLdPqvEInNNRnE
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
  - id: d6596f3f-92a7-43ec-b444-237db6adad05
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 504
ht-degree: 8%

---

# Sono stati risolti i problemi nella versione 2024.2.0 di

Questo articolo descrive i bug corretti in varie aree della versione 2024.2.0 di Adobe Experience Manager Guides as a Cloud Service.

Per ulteriori informazioni sulle nuove funzioni e sui miglioramenti, consulta [Novità della versione 2024.2.0](whats-new-2024-2-0.md).

Scopri le [istruzioni di aggiornamento per la versione 2024.2.0](upgrade-instructions-2024-2-0.md).



## Authoring

- Il controllo ortografico nell’editor non consente la selezione di suggerimenti. (15045)
- Il pulsante di navigazione globale non funziona e il dashboard non viene caricato. (14968)
- Nell’editor web, la funzione di download mappa non attiva una notifica pop-up quando è pronto per il download. (14626)
- Nell&#39;editor Web, la funzionalità di download mappa non consente di scaricare una mappa con linea di base. (14622)
- Errore DTD non valido nella versione di ottobre 2023 di Experience Manager Guides as a Cloud Service. (14482)
- Trascinare un argomento del glossario dal repository in una mappa del glossario crea `topicref`. (10767)
- La schermata di anteprima dei frammenti è bloccata. (14840)
- Le etichette del file `labels.json` vengono visualizzate in ordine casuale nell&#39;editor Web. (10508)

## Pubblicazione

- Nella pubblicazione nativa in PDF, gli attributi personalizzati nei predefiniti per le condizioni non funzionano per la pubblicazione nativa in PDF. (14943)
- Nella pubblicazione nativa su PDF, i riferimenti chiave non vengono risolti per la versione di dicembre 2023 di Adobe Experience Manager Guides. (15085)
- La pubblicazione di AEM Sites non riesce e causa errori di ambito per i file con `xref` nel file DITA che iniziano con &quot;HTTP&quot;. (15154)
- Impossibile aggiungere un modello personalizzato dalla scheda **Output** nell&#39;editor. (14846)
- Il predefinito per **Sito AEM** non funziona a causa di un percorso di modello vuoto. (14804)
- La rigenerazione del sito AEM ha esito negativo per le mappe DITA con argomenti che contengono equazioni di MathML. (14790)
- Nella pubblicazione nativa di PDF, la generazione di PDF genera errori nell&#39;ottenere le dipendenze per la pubblicazione di `Node.js`. (14445)
- Il predefinito AEM non consente la selezione di un modello esterno alla gerarchia `/content` nell&#39;editor Web. (14260)
- Nell&#39;output di AEM Sites, lo stile o le interruzioni di riga sono stati persi per l&#39;elemento `<lines>` con elementi secondari. (12542)
- I metadati personalizzati non sono disponibili nell’output finale. (12116)
- Nella pubblicazione nativa di PDF non è possibile utilizzare le proprietà dei metadati delle mappe DITA per popolare i metadati per l&#39;output di file PDF. (15159)



## Gestione

- **I file del filtro della linea di base** non funzionano con il nome file nell&#39;editor Web. (13486)
- La disattivazione dell&#39;indicizzazione della mappa DITA padre per ottenere prestazioni migliori può influire sulle funzionalità di alcune funzionalità.(12213)


## Rivedere

- Il menu di scelta rapida visualizzato facendo clic con il pulsante destro del mouse non funziona per **Accept** o **Reject** track changes. (14607)
- L’opzione per chiudere gli argomenti DITA nella schermata di revisione non funziona nella versione di dicembre 2023 di Adobe Experience Manager Guides. (14537)
- La personalizzazione dei modelli e-mail per il flusso di lavoro di revisione non funziona con la sovrapposizione. (13954)

## Problema noto

Adobe ha identificato il seguente problema noto per la versione 2024.2.0:

- La versione 1.0 non viene visualizzata nell&#39;interfaccia utente del file DITA duplicato.
- La propagazione dei metadati delle risorse non funziona per la versione 2024.2.0 di con il microservizio abilitato per qualsiasi predefinito.
