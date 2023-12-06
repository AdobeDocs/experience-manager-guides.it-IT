---
title: Modificare gli argomenti nell'editor Web
description: Scopri come modificare gli argomenti nell’editor web. Scopri le varie funzioni di modifica per modificare i file degli argomenti nelle guide AEM.
exl-id: 8da37a81-e8c3-434f-b3f4-4723d87c2ade
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '572'
ht-degree: 0%

---

# Modificare gli argomenti nell&#39;editor Web {#id2056B040VUI}

L&#39;editor Web include una serie di funzioni di modifica che consentono di creare o modificare facilmente i file di argomenti. Per modificare un argomento nell&#39;Editor Web, è necessario eseguire la procedura seguente.

>[!IMPORTANT]
>
> Se si verifica un errore dell&#39;applicazione durante l&#39;utilizzo dell&#39;editor Web, aggiornare la pagina per continuare a lavorare.

1. Per apportare modifiche all&#39;argomento, fare clic all&#39;interno del bordo del testo dell&#39;elemento richiesto e iniziare ad apportare modifiche.

1. Per inserire un elemento specifico, fai clic su alla fine dell’elemento dopo il quale desideri inserire il nuovo elemento, quindi fai clic sull’icona dell’elemento richiesto nella barra degli strumenti. È inoltre possibile utilizzare la scelta rapida da tastiera `Alt+Enter` per richiamare **Inserisci elemento** popup.

   Viene visualizzato un elenco di elementi che è possibile utilizzare nell&#39;argomento. Le guide AEM consentono di posizionare in modo intelligente gli elementi in base alla loro posizione valida nell&#39;argomento.

   >[!NOTE]
   >
   > Puoi anche scegliere quale icona visualizzare nella barra degli strumenti configurando il `ui_config.json` file che si trova in - `/etc/designs/fmdita/clientlibs/xmleditor/`. Per ulteriori informazioni sulla personalizzazione delle funzionalità, contattare l&#39;amministratore di sistema.

1. Dopo aver modificato il documento, fare clic su **Salva**.

   >[!NOTE]
   >
   > Se non desideri confermare le modifiche nell’archivio AEM, fai clic su **Chiudi** e quindi fare clic su **Chiudi senza salvare** nella finestra di dialogo Modifiche non salvate.

   **Aggiorna il browser durante la modifica dei file**
Experience Manager Guides consente di aggiornare il browser mentre si modifica il contenuto nell&#39;editor Web. Questa funzione consente di continuare a modificare il contenuto in caso di errore dell’applicazione durante il lavoro. Se si preme il pulsante di aggiornamento del browser mentre uno o più file con modifiche non salvate vengono aperti per la modifica, viene visualizzato un avviso che segnala che le modifiche non salvate potrebbero andare perse. È possibile annullare l&#39;operazione di aggiornamento e salvare i file per mantenere le modifiche.

   Anche durante l&#39;aggiornamento del browser, le visualizzazioni dei pannelli sinistro e destro vengono mantenute nell&#39;editor Web. Experience Manager Guide ripristina l&#39;ultimo stato salvato dei file aperti nell&#39;editor Web quando si aggiorna il browser. Ad esempio, i file aperti nel pannello Repository vengono aperti nuovamente. Il pannello mappa viene mantenuto insieme alla mappa aperta in precedenza.

   L&#39;argomento attivo o la mappa DITA viene riaperto nell&#39;area di modifica del contenuto.

   Anche il pannello di destra viene riaperto e visualizza la stessa vista di prima dell’aggiornamento.

   **Indicatore copia di lavoro**
Le guide AEM forniscono l&#39;indicatore della copia di lavoro che indica se la \(copia di lavoro\) corrente del file è sincronizzata con la versione salvata. Se sono state apportate modifiche alla copia corrente e il file non è stato salvato, nella scheda File dell&#39;argomento verrà visualizzato il simbolo \* insieme al titolo. Questo indicatore funge da promemoria per il salvataggio delle modifiche e scompare quando si salva il file.

   ![](images/working-copy-text-update-indicator.png){width="550" align="left"}

   Le guide AEM indicano anche se l’ultima copia salvata del file \(working\) è sincronizzata o meno con la versione salvata. Se sono presenti modifiche non salvate tra la copia in modifica e l&#39;ultima versione salvata, viene visualizzato un segno \* insieme alle informazioni sulla versione visualizzate nell&#39;angolo superiore destro della scheda del file dell&#39;argomento. Questo indicatore funge da promemoria per salvare e creare una versione dalla copia \(working\) corrente del file.

   ![](images/version-update-indicator.png){width="550" align="left"}


**Argomento padre:**[ Utilizzare l’editor web](web-editor.md)
