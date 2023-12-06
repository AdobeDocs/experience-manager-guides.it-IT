---
title: Note sulla versione | Istruzioni per l’aggiornamento e problemi risolti nella versione 4.3.0 delle Guide di Adobe Experience Manager
description: Scopri le correzioni di bug e come effettuare l’aggiornamento alle versioni 4.3.0 delle guide di Adobe Experience Manager
exl-id: 7fb568a0-0b88-4ea0-9b79-2625336348ff
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '1086'
ht-degree: 1%

---

# Versione 4.3.0 delle guide di Adobe Experience Manager (luglio 2023)

Questa nota sulla versione descrive le istruzioni per l’aggiornamento, la matrice di compatibilità e i problemi risolti nella versione 4.3.0 delle Guide di Adobe Experience Manager (in seguito denominate *Guide AEM*).

Per ulteriori informazioni sulle nuove funzioni e sui miglioramenti, consulta [Novità della versione 4.3.0 delle guide di Adobe Experience Manager](./whats-new-4.3-release.md).

## Aggiornamento alla versione 4.3.0 delle guide AEM


Puoi aggiornare facilmente la versione corrente delle guide AEM alla versione 4.3.0. Prima di procedere con l’aggiornamento alla versione 4.3.0 delle guide AEM, è necessario considerare i seguenti punti: È possibile aggiornare la versione corrente delle guide AEM alla versione 4.3.0

- Se utilizzi la versione 4.2 o 4.2.x, puoi eseguire direttamente l’aggiornamento alla versione 4.3.0.
- Se utilizzi la versione 4.1 o 4.1.x, devi effettuare l’aggiornamento alla versione 4.2 o 4.2.x prima di passare alla versione 4.3.0.
- Se utilizzi la versione 4.0, devi effettuare l’aggiornamento alla versione 4.2 prima di passare alla versione 4.3.0.
- Se utilizzi la versione 3.8.5, devi effettuare l’aggiornamento alla versione 4.0 prima di passare alla versione 4.2.
- Se utilizzi una versione precedente alla 3.8.5, consulta la sezione Aggiornamento delle guide AEM nella guida all’installazione specifica per il prodotto.



>[!NOTE]
>
>È necessario installare il service pack per l’AEM prima di aggiornare la versione delle guide AEM.

Per ulteriori informazioni, consulta [Istruzioni per l’aggiornamento](../install-guide/upgrade-xml-documentation.md).

## Matrice di compatibilità

In questa sezione viene elencata la matrice di compatibilità per le applicazioni software supportate dalla versione 4.3.0 delle guide AEM.

### Adobe Experience Manager

**4.3.0 Non UUID**
Versione 6.5 Service Pack 18, 17, 16, 15 o 14

**4.3.0 UUID**
Versione 6.5 Service Pack 18, 17, 16, 15 o 14

Per ulteriori dettagli, vedi *Requisiti tecnici* nella guida Installare e configurare Adobe Experience Manager Guides.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| Versione | FMPS 2022 | FMPS 2020 | Fm 2022 | Fm 2020 |
| --- | --- | --- | --- | --- |
| 4.3.0 (non UUID) | 2022 o versione successiva | 2020.2 o versione successiva* | 2022 o versione successiva | 2020.3 o versione successiva |
| 4.3.0 (UUID) | 2022 o versione successiva | 2020.2 o versione successiva* | 2022 o versione successiva | 2020.4 o versione successiva |
| | | | |

*Le condizioni di base e quelle create nell’AEM sono supportate nelle versioni di FMPS a partire dal 2020.2.

### Connettore ossigeno

| Versione | Finestre del connettore dell&#39;ossigeno | Connettore di ossigeno Mac | Modifica in finestre a ossigeno | Modifica in Oxygen Mac |
| --- | --- | --- |--- |--- |
| 4.3.0 (non UUID) | 2.3-regular-5 | 2.3-regular-5 | 1,6 | 1,6 |
| 4.3.0 (UUID) | 3,0-uuid-4 | 3.0-uuid-3 | 2,3 | 2,3 |
|  |  |   |

## Problemi risolti

Di seguito sono elencati i bug risolti in varie aree:

### Authoring

- Il file dell&#39;argomento non viene sbloccato nell&#39;editor Web, anche se sono selezionate le opzioni Sblocca il file e Non salvare. (12558)
- Impossibile estrarre un file nell&#39;editor Web, nonostante sia stata selezionata l&#39;opzione NO per ignorare le modifiche prima dell&#39;archiviazione. (12557)
- Le descrizioni comandi per le icone Blocca e sblocca file nella barra degli strumenti principale dell&#39;editor Web non sono coerenti con le icone visualizzate nella vista Archivio.(12555)
- L&#39;opzione Annulla estrazione e sblocca viene visualizzata per un file nell&#39;editor Web non ancora estratto in visualizzazione mappa. (12556)
- Impossibile selezionare le risorse PDF nei collegamenti &quot;topicref&quot; esistenti. (12477).
- Quando si esegue un&#39;unione e una suddivisione nelle tabelle, in AEM Guides 4.2 vengono generate celle di tabella aggiuntive. (11793)
- Nella Vista archivio, gli argomenti o le immagini non possono essere trascinati dopo aver utilizzato la funzionalità Ricerca/Filtro. (12396)
- I risultati della ricerca vengono disattivati nel pannello Trova e sostituisci dopo l’apertura di un file cercato. (12142)
- Il tasto numerico &quot;8&quot; sulla tastiera laterale non funziona nell’editor delle guide AEM. (12106)
- Gli attributi Inline/Display non vengono visualizzati nella visualizzazione Layout dell&#39;editor Web. (12498)
- La configurazione dell’interfaccia utente del profilo globale non corrisponde al profilo cartella. (11970)
- I riferimenti ai contenuti vengono interrotti quando i file DITA vengono copiati e incollati. (11959)
- Impossibile modificare il frammento di contenuto nella vista a colonne se sono installate le guide AEM. (7342)
- Il contenuto viene perso quando un riferimento esteso non racchiuso si trova sotto i tag di un elemento secondario. (12532)
- Il flusso di lavoro di approvazione non funziona se docstate viene modificato in &quot;end state&quot; dalle proprietà File del pannello di destra. (11026)
- Interfaccia utente risorse | Nella vista a elenco, le colonne disponibili sovrapposte non sono unificabili. (11528)
- Keyref non è risolto nella vista mappa. (11490)
- Il menu superiore non viene visualizzato quando si passa da un editor XML all&#39;altro. (10868)
- `conref` nel tag ph | La finestra di dialogo Sfoglia visualizzata non è corretta. (9481)
- I collegamenti locali ad altri elementi non vengono risolti in Editor Web. (8790)
- La funzione Matches() non funziona nella funzione Schematron. (11224)



### Gestione

- Il campo &quot;title&quot; nelle proprietà dei metadati della mappa DITA viene sovrascritto da `<title>` per la mappa. (10702)
- Quando si tenta di aprire o aggiornare la versione degli argomenti nella linea di base, il caricatore &quot;Recupero di informazioni dal server&quot; viene eseguito indefinitamente.(12478)


### Recensione

- Nuova interfaccia di revisione | Le condizioni evidenziano e mostrano il funzionamento di Nascondi in modo diverso rispetto a come funzionano nell’Editor web. (11628)

### Pubblicazione

- La pubblicazione non riesce quando si rinomina un predefinito di PDF nativo. (12564)
- La duplicazione di un modello di PDF nativo viene duplicata nel percorso predefinito del modello invece che nel percorso personalizzato fornito. (12563)
- Native PDF | Non è possibile impostare i metadati del linguaggio nel PDF generato in modo che siano conformi a WCAG 2.0. (12407)
- La pubblicazione sul sito AEM non riesce quando si leggono file temporanei dal pod che potrebbero essere stati aggiornati o riavviati. (12113)
- Native PDF | Gli attributi personalizzati non vengono propagati al motore temporaneo HTML o PDF. (DXML-12005)
- Native PDF | Java OutOfMemoryError si verifica quando si pubblicano contenuti di grandi dimensioni. (11789)
- Native PDF | Xref sta stampando il contenuto del titolo dell&#39;argomento href invece dell&#39;etichetta Xref. (11322)
- Native PDF | Impossibile salvare le impostazioni del modello PDF. (10751)
- Native PDF | Il testo si estende oltre la larghezza della colonna quando si includono più xref. (10876)
- Native PDF | `<note>``</note>` L&#39;elemento non genera un titolo di estensione aggiuntivo del relativo tipo. (10549)
- Output JSON | Il `fmUuid` proprietà nel nodo jcr:content di JSON diversa dall’&quot;id&quot; all’interno del JSON. (11564)
- Output JSON | Se sono presenti la mappa e l’argomento con lo stesso nome file, viene rimosso il codice JSON della mappa. (11524)

## Problema noto

L’Adobe ha identificato il seguente problema noto per la versione 4.3.0 delle Guide AEM:

- Il layout di pagina comune definito nel modello Base non viene applicato come modello predefinito.

  Soluzione alternativa: aggiungi il layout di pagina comune come copertina anteriore e posteriore, quindi inizia a venire per ogni pagina.
- Si è verificato un problema in Ricerca sito durante la ricerca nella pagina di output del sito AEM in AEM Service Pack 16 o 17.

  Soluzione alternativa:

   1. Apri il file con il percorso: `/libs/foundation/components/search/search.jsp` in `crx/de`
   1. Sostituire il numero di riga 234 con il seguente codice:

      ```
      <a href="<c:url value="${hit.URL}" context="/"/>" onclick="trackSelectedResult(this, ${status.index + 1})"><%= xssAPI.filterHTML(((Search.Hit) pageContext.getAttribute("hit")).getTitle()) %></a>
      
      *(Add the missing closing anchor tag at the end).
      ```

   1. Salva il file.
