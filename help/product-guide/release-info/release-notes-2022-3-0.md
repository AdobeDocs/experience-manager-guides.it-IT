---
title: Note sulla versione per  [!DNL AEM Guides], versione di marzo 2022
description: Versione di marzo di  [!DNL Adobe Experience Manager Guides] as a Cloud Service
exl-id: 885edbb5-dfe4-4bdc-bb66-0df64addb094
feature: Release Notes
role: Leader
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '777'
ht-degree: 0%

---

# Versione di marzo di [!DNL Adobe Experience Manager Guides] as a Cloud Service

## Aggiornamento alla versione di marzo

Aggiorna la configurazione corrente di [!DNL Adobe Experience Manager Guides] as a Cloud Service (in seguito denominata *[!DNL AEM Guides]as a Cloud Service*) eseguendo i seguenti passaggi:
1. Consulta il codice Git dei servizi cloud e passa al ramo configurato nella pipeline dei servizi cloud corrispondente all’ambiente da aggiornare.
1. Aggiorna la proprietà `<dox.version>` nel file `/dox/dox.installer/pom.xml` del codice Git dei servizi cloud a 2022.3.123.
1. Eseguire il commit delle modifiche ed eseguire la pipeline dei servizi cloud per eseguire l&#39;aggiornamento alla versione di marzo di [!DNL AEM Guides] as a Cloud Service.

## Matrice di compatibilità

In questa sezione viene elencata la matrice di compatibilità per le applicazioni software supportate da [!DNL AEM Guides] as a Cloud Service versione di marzo 2022.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| FMPS | FrameMaker |
| --- | --- |
| Non compatibile | Aggiornamento 2020 4 e versioni successive |
| | |


### Connettore ossigeno

| Versione cloud [!DNL AEM Guides] | Finestre del connettore dell&#39;ossigeno | Connettore di ossigeno Mac |
| --- | --- | --- |
| 2022.3.0 | 2.4.0 | 2.4.0 |
|  |  |  |

*Le condizioni di base e create in AEM sono supportate nelle versioni FMPS a partire dal 2020.2.

## Nuove funzioni e miglioramenti

### Dashboard nuova linea di base

[!DNL AEM Guides] as a Cloud Service versione di marzo fornisce la funzione Baseline integrata nell&#39;editor Web. È ora possibile creare linee di base dall&#39;Editor Web e utilizzarle per pubblicare o tradurre argomenti di versioni diverse.

Nota: per il sistema aggiornato, aggiorna il **ui_config.json** più recente per il profilo cartella.

Utilizzare questa funzione per creare una baseline con una versione specifica degli argomenti disponibili in una data e un&#39;ora specifiche. Inoltre, è possibile ottenere il supporto API per creare o aggiornare una linea di base con un&#39;etichetta definita per una versione di argomenti.

![scheda gestione baseline](assets/baseline-manage.png)

È possibile eseguire ricerche nei file in base ai nomi o alla posizione dei file. È inoltre possibile filtrare gli argomenti da visualizzare nella finestra di modifica della baseline e ordinarli in base a colonne specifiche.

![scheda gestione baseline](assets/baseline-filter.png)

Sono state ulteriormente migliorate le prestazioni per il processo di creazione della linea di base. Il processo di creazione delle baseline è asincrono, pertanto è possibile continuare a modificare altri file nell&#39;editor Web durante la creazione della baseline. Per ulteriori dettagli, vedere *Creare e gestire le linee di base dall&#39;editor Web* nella Guida utente.

Nota: la scheda Linea di base nel quadro comandi mappa è nascosta per impostazione predefinita. L’amministratore può abilitare la scheda Baseline nel dashboard delle mappe.

### È stato migliorato il comportamento di aggiornamento dell’editor web

Con l’operazione di aggiornamento del browser nell’editor web sono ora disponibili i seguenti miglioramenti:

* Ora è possibile aggiornare il browser mentre si modifica il
contenuto nell’editor web. Se premi l’icona di aggiornamento del browser mentre uno o più file sono
le modifiche non salvate vengono aperte per la modifica, viene richiesto di salvare i file o di annullare l&#39;operazione di aggiornamento.

* Anche durante l’aggiornamento del browser, vengono mantenute le visualizzazioni del pannello sinistro e di quello destro.

* L&#39;argomento attivo o la mappa DITA viene riaperto nell&#39;area di modifica del contenuto.

### Miglioramenti alla pubblicazione

Il processo di pubblicazione è stato ulteriormente migliorato con la versione di marzo di [!DNL AEM Guides] as a Cloud Service:

* Le linee di base sono state rispettate per i metadati dell’output del sito AEM. È inoltre possibile elaborare le proprietà di una versione di base come metadati. Se non è definita alcuna linea di base, le proprietà della versione più recente vengono elaborate come metadati.

* Sono state aggiunte le opzioni **Nome file** e **Argomenti riga di comando DITA-OT** per i predefiniti di output HTML5, EPUB e Personalizzati. Ora puoi specificare il nome del file con cui vuoi salvare l’output. È inoltre possibile specificare gli argomenti aggiuntivi che DITA-OT deve elaborare durante la generazione dell&#39;output.

## Problemi risolti

Di seguito sono elencati i bug risolti in varie aree:

* Impossibile aggiungere elementi di frontmatter o di backmatter in una mappa segnalibro utilizzando la visualizzazione Autore dell&#39;editor Web. (7652)
* La struttura di riferimento si interrompe dopo la rimozione di un argomento e l&#39;esecuzione di un&#39;operazione di spostamento. (8804)
* Viene ricevuta un’eccezione durante la visualizzazione del contenuto dopo il caricamento di una risorsa. (3638)
* Si verifica un errore quando i file la cui cartella principale contiene caratteri speciali nel nome del file vengono aperti in ossigeno utilizzando il pulsante **Modifica in ossigeno**. (8918)
* L&#39;opzione **Individua nel repository** non individua ed evidenzia la mappa DITA nell&#39;editor XML. (8796)
* Quando si aggiungono più attributi al contenuto nell&#39;editor XML, il filtro non mostra i risultati appropriati. (8795)
* Si verifica un errore quando si aggiunge un utente come amministratore nel profilo della cartella quando l’ID utente è numerico. (8908)

## Problemi noti

Adobe ha identificato il seguente problema noto nella versione di marzo di as a Cloud Service [!DNL AEM Guides].

* La rimozione delle etichette sui riferimenti diretti comporta anche la rimozione delle etichette dai riferimenti indiretti.

* Impossibile riflettere il titolo della baseline aggiornato senza aggiornare manualmente il pannello della baseline.

* La funzione di anteprima della versione nel pannello Cronologia versioni non mostra l&#39;anteprima di un argomento selezionato.
