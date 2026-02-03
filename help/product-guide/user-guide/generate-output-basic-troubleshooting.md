---
title: Risoluzione dei problemi di base
description: Risolvi i problemi relativi alla risoluzione dei problemi di base in AEM Guides. Scopri come visualizzare, copiare e controllare il file di registro in un editor di testo e risolvere gli errori di compilazione JSP.
exl-id: 57b88291-b5a3-4931-b3ed-f2b2ce7a463c
feature: Publishing, Troubleshooting
role: User
source-git-commit: e049cb1f3d091c701285dbe89194058b93d5e2e4
workflow-type: tm+mt
source-wordcount: '776'
ht-degree: 0%

---

# Risoluzione dei problemi di base {#id1821I0Y0G0A}

Quando si lavora con Adobe Experience Manager Guides, è possibile che si verifichino degli errori durante la pubblicazione o l’apertura del documento. Tali errori possono essere presenti nella mappa DITA, nell&#39;argomento o nel processo Experience Manager Guides stesso. Questa sezione fornisce informazioni su come accedere e analizzare le informazioni nel file di registro di generazione dell&#39;output. Inoltre, se l&#39;argomento DITA è troppo grande, è possibile visualizzare l&#39;errore di compilazione JSP. Questa sezione fornisce anche informazioni su come risolvere l’errore di compilazione JSP.

## Visualizza e controlla il file di registro {#id1822G0P0CHS}

Per visualizzare e controllare il file di registro di generazione dell’output, effettua le seguenti operazioni:

1. Dopo aver avviato il processo di generazione dell&#39;output, selezionare **Output** nella console delle mappe DITA.

   La colonna **Generation setting** dei **Output generati** mostra il colore per dare un segnale visivo sull&#39;esito positivo o negativo della generazione dell&#39;output per diversi predefiniti di output.

   ![](images/output-general-settings-new.png){width="300" align="left"}

   Nella schermata precedente:

   - Il rosso indica una generazione di output non riuscita.
   - Il verde indica una generazione di output riuscita.
   - Il valore Amber indica una generazione di output riuscita con errori.

   >[!NOTE]
   >
   > I colori della scheda **Output**, che indicano lo stato dei vari risultati di output, sono diversi da quelli utilizzati per categorizzare i vari tipi di errore all&#39;interno dei file di log.

1. Selezionare il collegamento nella colonna **Generated At** al termine del processo.

   Il file di registro viene aperto in una nuova scheda.

   ![](images/log-file-new.png){align="left"}

1. Applica i seguenti filtri per evidenziare il testo nel file di registro:
   - **Fatal**: evidenzia gli errori irreversibili nel file di registro con un colore rosso scuro.
   - **Errore**: evidenzia gli errori nel file di registro con un colore rosso. Le eccezioni vengono trattate come errori e sono evidenziate in rosso in modo simile.
   - **Avviso**: evidenzia gli avvisi nel file di registro con il colore giallo.
   - **Informazioni**: evidenzia i messaggi di informazione nel file di registro con il colore verde.

1. Utilizzare i pulsanti di spostamento su e giù per passare al testo evidenziato nel file di log. In alternativa, scorri il file di registro e controlla i messaggi.

1. Nel file di registro è possibile eseguire le azioni seguenti:

   - **Registro di download**: se l&#39;elenco dei registri è esteso, selezionare **Registro di download** per scaricare il file di registro sul dispositivo per accedervi e rivederlo più facilmente.
   - **Copia registro**: copia l&#39;elenco dei registri negli Appunti, consentendo di incollarlo rapidamente in un editor di testo.

## Copiare e controllare il file di registro in un editor di testo

Per copiare e controllare il file di registro di generazione dell’output in un editor di testo, effettua le seguenti operazioni:

1. Dopo aver avviato il processo di generazione dell&#39;output, selezionare **Output** nella console delle mappe DITA.

1. Selezionare il collegamento nella colonna **Generated At** al termine del processo.

   Il file di registro viene aperto in una nuova scheda.

1. Seleziona il pulsante **Copia registro**. Il file di registro viene copiato negli Appunti.
1. Apri un editor di testo e incolla il file di registro nell’editor.

1. Scorrere il file di registro e verificare la presenza di messaggi.

   Le informazioni seguenti consentono di determinare se si è verificato un errore nel file DITA o nel processo Experience Manager Guides:

   - *Errore relativo al file di mappa DITA*: se viene rilevato un errore nel file di mappa DITA o in qualsiasi altro file contenuto nella mappa DITA, il file di registro conterrà una stringa &quot;BUILD FAILED&quot;. È possibile controllare le informazioni fornite nel file di registro per individuare il file errato e risolvere il problema.

   Nello snippet di file di log di esempio seguente è possibile visualizzare il messaggio `BUILD FAILED` insieme al motivo dell&#39;errore.

   ![](images/dita-error-in-log-file.png){width="650" align="left"}

   - *Errore relativo a Experience Manager Guides*: l&#39;altro tipo di errore che è possibile identificare nel file di log è relativo al processo di Experience Manager Guides stesso. In questo caso, il file mappa DITA viene analizzato correttamente, ma il processo di generazione dell&#39;output non riesce a causa di un errore interno in Experience Manager Guides. Per questo tipo di errori è necessario rivolgersi al team di supporto tecnico.

   Nel seguente frammento del file di log di esempio è possibile visualizzare il messaggio `BUILD SUCCESSFUL`, seguito da un altro errore tecnico.

   ![](images/process-error-in-log-file.png){width="650" align="left"}





## Risolvi errore di compilazione JSP

Se l&#39;argomento DITA è troppo grande, è possibile visualizzare l&#39;errore di compilazione JSP \(`org.apache.sling.api.request.TooManyCallsException`\) nel browser. Questo errore può essere visualizzato quando si apre un argomento per la modifica, la revisione o la pubblicazione.

Per risolvere il problema, effettua le seguenti operazioni:

1. Nella navigazione globale, selezionare Strumenti e scegliere Operazioni \> Console Web.

   Viene visualizzata la pagina Configurazione console Web Adobe Experience Manager.

1. Cerca e seleziona il componente *Apache Sling Main Servlet*.

   Vengono visualizzate le opzioni configurabili per Apache Sling Main Servlet.

1. Aumenta il valore per il parametro *Numero di chiamate per richiesta* in base alle tue esigenze.


**Argomento padre:**[ Generazione output](generate-output.md)
