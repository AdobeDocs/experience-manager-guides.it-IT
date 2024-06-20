---
title: API REST per lavorare con le mappe DITA
description: Scopri l’API REST per lavorare con le mappe DITA
exl-id: 6277e52d-1b05-4dd7-8d2b-4b94f329e2d7
feature: Rest API DITA Map
role: Developer
level: Experienced
source-git-commit: 7c529e98334999cf2b5e9ee18a27278d24318437
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 0%

---

# API REST per lavorare con le mappe DITA {#id175UB30E05Z}

La seguente API REST consente di lavorare con le mappe DITA nelle guide AEM.

## Scarica mappa DITA con dipendenti

Metodo di GET che scarica una mappa DITA con tutti i relativi dipendenti, ad esempio gli argomenti di riferimento, le mappe secondarie, le immagini e le DTD utilizzate nella mappa e negli argomenti.

**URL richiesta**: http://*&lt;aem-guides-server>*: *&lt;port-number>*/bin/fmdita/exportditamap

**Parametri**: |Nome|Tipo|Obbligatorio|Descrizione| ----|----|--------|-----------| |`ditamap`|String|Yes|Percorso assoluto del file di mapping DITA nell&#39;archivio AEM.| |`baseline`|Stringa|No|Titolo della linea di base utilizzata per recuperare il contenuto con versione. <br> **Nota:** Il valore distingue tra maiuscole e minuscole. |

**Valori di risposta**: file .zip il cui contenuto viene scritto nel flusso di output della risposta.

## Avvia esportazione per mappa DITA con dipendenti

Metodo POST che avvia un&#39;esportazione per una mappa DITA con tutti i relativi dipendenti, ad esempio argomenti di riferimento, mappe secondarie, immagini e DTD utilizzati nella mappa e negli argomenti. Successivamente è possibile interrogare lo stato e recuperare l’URL di download al termine dell’operazione.

**URL richiesta**: http:*//&lt;aem-guides-server>: &lt;port-number>/bin/dxml/async-export*

**Parametri**: |Nome|Tipo|Obbligatorio|Descrizione| ----|----|--------|-----------| |`ditamap`|String|Yes|Percorso assoluto del file di mapping DITA nell&#39;archivio AEM.| |`baseline`|Stringa|No|Titolo della linea di base utilizzata per recuperare il contenuto con versione. <br> **Nota:** Il valore distingue tra maiuscole e minuscole.| |`flatFS`|Boolean|No|\(Facoltativo\) Se impostato su true, nel file ZIP viene restituita una struttura semplice di file. Ad esempio, se la mappa DITA fa riferimento a contenuto in più cartelle, tutti i file di riferimento vengono estratti in un&#39;unica cartella. Nel caso vi siano file con lo stesso nome, tali file vengono rinominati aggiungendo un suffisso numerico. Tutti i riferimenti \(in mappa DITA e argomenti\) vengono gestiti automaticamente, in quanto vengono aggiornati in base alla nuova posizione dei file nella struttura di cartelle flat. Se impostato su false, la struttura delle cartelle viene mantenuta invariata nel file ZIP. Se la mappa DITA fa riferimento a file provenienti da più posizioni, anche tutte queste posizioni vengono create nel file ZIP. Quando si ripristina il file ZIP, viene creata la struttura di cartelle esatta nel percorso di destinazione. <br> Il valore predefinito per questo parametro è false.|

**Valori di risposta**: |Elemento|Descrizione| ----------- ------- |`status`|Stato di ritorno per l&#39;operazione eseguita. Le opzioni possibili sono: AVVIATO, NON RIUSCITO, IN CORSO, RIUSCITO, MANCANTE, ELIMINATO| |`jobId`|ID univoco del processo. Può essere utilizzato in seguito per eseguire una query per lo stato.| |errorMessage|Messaggio di errore del processo in caso di errore \(se lo stato è FAILED, MISSING o DELETED\).| |`filePath`|Percorso file del file ZIP. È presente solo quando il processo è completato e lo stato è RIUSCITO. Può essere utilizzato per scaricare il file ZIP.|

## Stato mappa DITA esportazione query

Un metodo GET che recupera lo stato di esportazione di una mappa DITA con tutti i relativi dipendenti. È possibile eseguire il polling a intervalli se lo stato è STARTED o INPROGRESS fino al completamento \(riuscito o con un errore\).

**URL richiesta**: http:*//&lt;aem-guides-server>: &lt;port-number>/bin/dxml/async-export*

**Parametri**
|Nome|Tipo|Obbligatorio|Descrizione| ----|----|--------|-----------| |`jobId`|Stringa|Sì|L&#39;ID del processo recuperato all&#39;avvio del processo di esportazione.|

**Valori di risposta**: |Elemento|Descrizione| ----------- ------- |`status`|Stato del processo di esportazione. Le opzioni possibili sono: AVVIATO, NON RIUSCITO, IN CORSO, RIUSCITO, MANCANTE, ELIMINATO| |`jobId`|ID univoco del processo. Può essere utilizzato in seguito per eseguire una query per lo stato.| |`errorMessage`|Messaggio di errore del processo in caso di errore \(se lo stato è FAILED, MISSING o DELETED\).| |`filePath`|Percorso file del file ZIP. È presente solo quando il processo è completato e lo stato è RIUSCITO. Può essere utilizzato per scaricare il file ZIP.|
