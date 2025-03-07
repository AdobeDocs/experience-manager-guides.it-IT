---
title: Note sulla versione | Istruzioni per l’aggiornamento e problemi risolti in Adobe Experience Manager Guides versione 4.3.1
description: Scopri le correzioni di bug e come effettuare l’aggiornamento alla versione 4.3.1 di Adobe Experience Manager Guides
exl-id: 3fb6dc31-ec6e-40f5-ab3f-a6e591da315e
feature: Release Notes
role: Leader
source-git-commit: 1b25f1df67fa2442ab79830dc2ac5a6eabd0394c
workflow-type: tm+mt
source-wordcount: '1308'
ht-degree: 1%

---

# Versione 4.3.1 di Adobe Experience Manager Guides (ottobre 2023)

Questa nota sulla versione descrive le istruzioni per l&#39;aggiornamento, la matrice di compatibilità e i problemi risolti nella versione 4.3.1 di Adobe Experience Manager Guides (in seguito denominato *Experience Manager Guides*).

Per ulteriori informazioni sulle nuove funzionalità e sui miglioramenti, vedere [Novità della versione 4.3.1 di Adobe Experience Manager Guides](./whats-new-4-3-1-release.md).

## Aggiornamento alla versione 4.3.1 di Experience Manager Guides


Puoi aggiornare facilmente la versione corrente di Experience Manager Guides alla versione 4.3.1. Prima di procedere con l’aggiornamento alla versione 4.3.1 di Experience Manager Guides, è necessario considerare i seguenti punti:
È possibile aggiornare la versione corrente di Experience Manager Guides alla versione 4.3.1


- Se utilizzi le versioni 4.3.0, 4.2 o 4.2.1, puoi eseguire direttamente l’aggiornamento alla versione 4.3.1.
- Se utilizzi la versione 4.1 o 4.1.x, devi effettuare l’aggiornamento alla versione 4.3.0, 4.2 o 4.2.x prima di eseguire l’aggiornamento alla versione 4.3.1.
- Se utilizzi la versione 4.0, devi effettuare l’aggiornamento alla versione 4.2 prima di passare alla versione 4.3.1.
- Se utilizzi la versione 3.8.5, devi effettuare l’aggiornamento alla versione 4.0 prima di passare alla versione 4.2.
- Se utilizzi una versione precedente alla 3.8.5, consulta la sezione Aggiornamento di Experience Manager Guides nella guida all’installazione specifica per il prodotto.


>[!NOTE]
>
>Prima di aggiornare la versione di Experience Manager Guides è necessario installare il service pack per AEM.

Per ulteriori dettagli, vedere [Istruzioni per l&#39;aggiornamento](../install-guide/upgrade-xml-documentation.md).

## Matrice di compatibilità

In questa sezione viene elencata la matrice di compatibilità per le applicazioni software supportate da Experience Manager Guides versione 4.3.1.

### Adobe Experience Manager

**4.3.1 Non UUID**
Versione 6.5 Service Pack 18, 17, 16, 15 o 14

**4.3.1 UUID**
Versione 6.5 Service Pack 18, 17, 16, 15 o 14

Per ulteriori dettagli, consulta la sezione *Requisiti tecnici* nella guida Installare e configurare Adobe Experience Manager Guides.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| Versione | FMPS 2022 | FMPS 2020 | Fm 2022 | Fm 2020 |
| --- | --- | --- | --- | --- |
| 4.3.1 (non UUID) | 2022 o versione successiva | 2020.2 o versione successiva* | 2022 o versione successiva | 2020.3 o versione successiva |
| 4.3.1 (UUID) | 2022 o versione successiva | 2020.2 o versione successiva* | 2022 o versione successiva | 2020.4 o versione successiva |
| | | | |

*Le condizioni di base e quelle create nell’AEM sono supportate nelle versioni di FMPS a partire dal 2020.2.

### Connettore ossigeno

| Versione | Finestre del connettore dell&#39;ossigeno | Connettore di ossigeno Mac | Modifica in finestre a ossigeno | Modifica in Oxygen Mac |
| --- | --- | --- |--- |--- |
| 4.3.1 (non UUID) | 2.3-regular-5 | 2.3-regular-5 | 1,6 | 1,6 |
| 4.3.1 (UUID) | 3.2-uuid-5 | 3.2-uuid-5 | 2,3 | 2,3 |
|  |  |   |



### Versione modello della Knowledge Base

| Nome pacchetto componenti | Versione componenti | Versione modello |
|---|---|---|
| Pacchetto di contenuti per componenti Experience Manager Guides per Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

## Problemi risolti

Di seguito sono elencati i bug risolti in varie aree:

### Authoring

- Le ore pomeridiane non sono impostate nella **Data** per la creazione delle linee di base. (12712)
- Impossibile incollare il codice JSON nell&#39;elemento `<codeblock>` dell&#39;editor Web. (12326)
- Le modifiche delle versioni non salvate e i relativi indicatori non vengono visualizzati per i file di grandi dimensioni. (11784)
- Durante la modifica in coreano, il primo carattere diventa il carattere predefinito. (10049)

- Il prefisso viene duplicato nella modalità di anteprima dell’editor web. (13133)
- `Choicetable` righe non visualizzate o non selezionabili. (12616)
- L’editor web genera errori di convalida in scenari specifici durante la creazione di un argomento utilizzando uno schema personalizzato. (12576)
- I riferimenti al modello di argomento ditaval non creano una copia nella cartella dei contenuti durante la creazione di una mappa dal modello di mappa. (12150)

- La casella di ricerca nelle mappe DITA non dispone di un pulsante di chiusura. (11867)
- Quando si salvano file lunghi nell&#39;editor Web, `DirtyChecker` genera un&#39;eccezione con una traccia dello stack lunga e riempie i file di log. (11860)
- La creazione di argomenti DITA richiede l&#39;autorizzazione Elimina sul nodo di cartella corrispondente, anche se la mappa può essere creata con l&#39;autorizzazione di scrittura. (11706)
- L’editor web mostra un titolo errato quando è presente una barra. (10949)

- Se il titolo di un argomento contiene una barra &quot;/&quot;, la scheda nell’editor mostra solo le lettere che arrivano dopo. (13455)
- L&#39;anteprima dell&#39;immagine non scompare dopo averla visualizzata nell&#39;editor. (13454)
- Alcune delle versioni esistenti o le relative etichette non vengono visualizzate nella Cronologia versioni dopo l’aggiornamento a 4.x. (13247)
- Il pannello Cronologia versioni nell&#39;interfaccia utente di Assets mostra una marca temporale non corretta per il campo **Corrente**. (12624)
- L&#39;argomento con titolo di riferimento non viene risolto nella vista archivio o nella vista mappa.(13304)


### Pubblicazione

- Native PDF | L’ordine degli argomenti non viene corretto durante la generazione dell’output di PDF. (13157)
- PDF nativa| Nessun tag di stile predefinito disponibile per l&#39;elemento `<p>`. (12559)
- Native PDF | Gli stili in linea applicati all&#39;area del contenuto non vengono applicati agli argomenti davanti e dietro. (13510)
- L&#39;attributo `DeliveryTarget` non viene propagato durante la generazione dell&#39;output del sito AEM.  (13132)
- Il flusso di lavoro **Publish** si blocca durante la generazione dell&#39;output del sito AEM per il contenuto con determinati errori. (12000)

- Native PDF | L&#39;inclusione di più xrefs estende il testo oltre la larghezza della colonna. (13004)
- Native PDF | Quando l’argomento e il titolo hanno lo stesso ID, si verifica un errore nella generazione dell’output PDF. (12644)
- Native PDF | Quando si aggiunge una classe di output a un elemento padre `<topicref>` in una mappa DITA e si applica uno stile personalizzato alla classe di output, lo stile viene applicato agli elementi all&#39;interno del corpo dell&#39;argomento, inclusi i titoli di sezione. (12166)
- La pubblicazione incrementale non funziona se una mappa DITA contiene più ditavalref. (12117)
- Sito AEM | Quando si crea una mappa con keydef che punta a un argomento come variabile e si aggiunge processing-role=resource-only, vengono create alcune pagine impreviste. (12099)
- Se vengono utilizzate risorse di DAM dell&#39;AEM in un output diverso dal sito AEM, i metadati &quot;jcr:createdBy&quot; non riflettono il nome dell&#39;editore o dell&#39;utente che ha modificato per ultimo la mappa o l&#39;argomento DITA. (12090)
- AEM Sites | La mappa DITA con l’intestazione dell’oggetto nel titolo della navigazione (con caratteri non supportati) causa la presenza di URL di pagina non validi. (11978)
- Native PDF | Si verificano problemi a supporto di topichead / topicmeta / navtitle in Frontmatter e Backmatter. (11969)
- Native PDF | La generazione di PDF per documenti di grandi dimensioni richiede molto tempo. (11955)
- Native PDF | La ridenominazione di un predefinito genera un’eccezione NullPointerException durante la generazione di un output PDF. (11889)
- Il contenuto di `<conref>` non è visualizzato nell&#39;output di PDF. (11131)
- All&#39;interno degli elementi `<div>` viene aggiunto uno spazio aggiuntivo quando si passa dalla visualizzazione Autore a quella Source nell&#39;editor di layout di pagina. (10750)
- Il contenuto replicato in AEM Cloud Manager non è visibile nell’istanza di Publish. (9564)


### Gestione

- La cronologia delle versioni non viene visualizzata anche se la proprietà `dc:format` non è presente per una risorsa. (10463)
- Il riferimento al contenuto è interrotto per copiare e incollare file DITA quando l&#39;ID argomento non corrisponde a GUID. (12614)
- Nelle baseline dinamiche, l&#39;elenco delle etichette non viene estratto dai riferimenti diretti della copia di lavoro di una mappa DITA. (11917)
- La linea di base mostra il numero errato di file nel dashboard mappa quando si utilizza la funzionalità Sfoglia tutti gli argomenti. (13265)
- Nell&#39;editor Web, la baseline mostra il titolo della versione precedente anziché della versione selezionata del file DITA. (13444)

### Rivedi

- La revisione di un argomento mostra commenti non corretti. (13453)
- Il pulsante Chiudi nella pagina Revisione del Experience Manager Guides porta gli utenti alla home page dell&#39;AEM. (13535)
- Gli allegati non vengono visualizzati nel pannello di destra dell’editor per un argomento In-review. (13011)



### Traduzione

- La linea di base esportata dal dashboard **Traduzione** non riesce e non si apre nella lingua di destinazione. (13466)

- Vengono creati nuovi progetti di traduzione invece di aggiungere nuovi processi ai progetti di traduzione esistenti selezionati.  (10214)
- Il titolo del file tradotto viene visualizzato al posto del titolo del file sorgente. (11630)
- L’approvazione automatica a volte non funziona e si verificano eccezioni se sullo stato della traduzione è impostato un valore errato. (13607)
- La linea di base esportata dal dashboard di traduzione non riesce e non si apre nella lingua di destinazione. (12993)
- Mancano alcuni file durante l’utilizzo delle linee di base nella traduzione. (13021)
