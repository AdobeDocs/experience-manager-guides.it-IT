---
title: PDF nativo | Usa variabili nell'output PDF
description: Utilizzare le variabili nei modelli di output e output PDF
feature: Output Generation
role: Admin
level: Experienced
exl-id: 96e54aee-52df-4af1-97fd-34986f553be4
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '1446'
ht-degree: 0%

---

# Variabili nell&#39;output PDF

Una variabile è una coppia nome-valore di dati che funge da informazione riutilizzabile. Questo rende il tuo contenuto portatile e facile da aggiornare. Quando si modifica una variabile o il relativo valore, viene aggiornato ogni occorrenza di tale variabile o valore.



## Crea una nuova variabile

Per creare una variabile, effettua le seguenti operazioni:

![Crea una nuova variabile](assets/add-variable-default.png){width="800" align="left"}

*Creare variabili e definirne i valori.*


1. Nell&#39;editor Web passare alla scheda **Output**.
1. Seleziona **Variabili** <img alt= "icona variabile" src="./assets/variables-icon.svg" width="25"> nel pannello a sinistra.
1. Seleziona **Modifica** <img alt= "Icona Modifica matita" src="./assets/edit_pencil_icon.svg" width="25"> per aprire l&#39;editor **Variabili**.
Le variabili sono elencate in ordine alfabetico.
1. Immettete il nome della variabile nella **colonna Nome** e il relativo valore nella **colonna Valore** .
   >[!TIP]
   >
   >Puoi utilizzare qualsiasi contenuto HTML come valore variabile per visualizzare il valore della variabile in una formattazione specifica. È ad esempio possibile aggiungere un tag `<b>` al valore della variabile per visualizzare il valore **Experience Manager Guides** in grassetto. È inoltre possibile aggiungere immagini dall’archivio come valori.

1. Seleziona **Aggiungi variabile** <img alt= "Icona Aggiungi" src="./assets/add-icon.svg" width="25"> per aggiungere una nuova variabile. Non è possibile creare una variabile con lo stesso nome di una variabile esistente. Viene visualizzato un errore.

   >[!NOTE]
   >
   >Se non selezioni **Aggiungi variabile** <img alt= "Icona Aggiungi" src="./assets/add-icon.svg" width="25">, la variabile non viene creata e aggiunta all&#39;elenco.

In questo modo, puoi creare variabili con valori predefiniti. Ad esempio:
* Nome prodotto: Experience Manager Guides
* Numero versione: 2300
* Data di rilascio: 01/01/2023


### Modificare una variabile

È possibile modificare una variabile in due modi:

**Dal pannello Variabili sul lato sinistro**

1. Seleziona una variabile nel pannello **Variabili**.
1. Passa il puntatore del mouse sulla variabile per visualizzare il menu **Opzioni**, quindi seleziona l&#39;opzione **Modifica**.
1. Nella finestra di dialogo **Modifica variabile** è possibile modificare il valore predefinito della variabile selezionata.
1. Fai clic su **Fine**.

**Dall&#39;editor variabili**

1. Seleziona **Variabili** <img alt= "icona variabile" src="./assets/variables-icon.svg" width="25"> nel pannello a sinistra.
1. Seleziona **Modifica** <img alt= "Icona Modifica matita" src="./assets/edit_pencil_icon.svg" width="25"> per aprire l&#39;editor **Variabili** .

1. **Nella editor Variabili** è possibile modificare il valore della variabile selezionata.

È necessario salvare le modifiche apportate dall&#39;editor **** Variabili per visualizzarle nel **pannello Variabili** sul lato sinistro.

>[!NOTE]
>
> Se si modifica un valore di variabile, Adobe Experience Manager Guide aggiorna simultaneamente tutti i riferimenti laddove applicabile.

### Search e visualizzare in anteprima una variabile

Puoi cercare e visualizzare in anteprima il valore di una variabile. Immettere una stringa nella casella di ricerca del pannello **Variabili**. La ricerca viene eseguita in base al nome della variabile e al relativo valore.
Puoi visualizzare in anteprima una variabile in due modi:

Nell’anteprima della variabile viene visualizzato il valore predefinito. Ad esempio, se hai definito il valore predefinito della variabile ProductName come &quot;Adobe Experience Manager Guides&quot;, questo valore viene visualizzato nell’anteprima.

**Dal pannello Variabili sul lato sinistro**


1. Seleziona una variabile nel pannello **Variabili**.
1. Passa il puntatore del mouse sulla variabile per visualizzare il menu **Opzioni**, quindi seleziona l&#39;opzione **Anteprima**.

![anteprima variabile dal pannello variabili](assets/variables-panel-preview-default.png){width="550" align="left"}

*Visualizzare in anteprima il valore predefinito per una variabile.*

**Dall&#39;editor variabili**

1. Passa il cursore del mouse sulla variabile nell&#39;elenco per visualizzare il menu **Opzioni**.
1. Selezionare **Anteprima**.




### Duplicare una variabile

È possibile duplicare una variabile e modificarla in base alle proprie esigenze.


1. Passare il puntatore del mouse sulla variabile nell&#39;elenco per visualizzare il **menu Opzioni** .
1. Seleziona **Duplicazione**.

Il nome predefinito della variabile è `<selected variable name>` (ad esempio &quot;sample&quot;). Puoi modificare il nome in base alle tue esigenze.

### Eliminare una variabile

È possibile eliminare una variabile in due modi:

**Dal pannello Variabili sul lato sinistro**

1. Seleziona una variabile nel pannello **Variabili**.
1. Passa il puntatore del mouse sulla variabile per visualizzare il menu **Opzioni**, quindi seleziona l&#39;opzione **Elimina**.

**Dall&#39;editor variabili**

1. Passa il cursore del mouse sulla variabile nell&#39;elenco per visualizzare il menu **Opzioni**.
1. Selezionare l&#39;opzione **Elimina**.

La variabile viene eliminata da tutti i set di variabili.

## Set di variabili per i predefiniti di output

Adobe Experience Manager Guide supporta anche i set di variabili, che consentono di assegnare alle variabili valori alternativi. Ad esempio, un&#39;azienda può vendere due prodotti, A e B. Ha specifiche diverse per ciascuno di essi. Queste specifiche potrebbero includere il nome del prodotto, il numero di versione e la data di rilascio. Ci possono essere altre differenze nel branding. Utilizzando i set di variabili, puoi definire un set di valori diverso per le variabili. Quando generate l&#39;output, scegliete l&#39;insieme di variabili appropriato e create l&#39;output richiesto.

### Configurare i set di variabili

È necessario configurare i set di variabili prima di aggiungervi variabili.



1. Seleziona **Impostazioni** <img alt= "Icona Impostazioni" src="./assets/settings-icon.svg" width="25"> per aprire la finestra di dialogo **Configura set di variabili**.
   ![configura set di variabili](assets/configure-variable-set.png){width="550" align="left"}
1. Immettere il nome del set di variabili nella colonna **Nome**.
1. Seleziona **Aggiungi variabile** <img alt= "Icona Aggiungi" src="./assets/add-icon.svg" width="25"> per aggiungere un nuovo set di variabili. I set di variabili sono elencati in ordine alfabetico.
1. È possibile selezionare **Elimina** per rimuovere un set di variabili.

### Operazioni per set di variabili

Tutti i set di variabili hanno le stesse variabili, ma possono avere valori diversi.

Puoi visualizzare, modificare e visualizzare in anteprima i valori per un set di variabili specifico. Seleziona un set di variabili dal menu a discesa **Set di variabili**. I valori vengono visualizzati in base al set di variabili selezionato.
Quando si modificano i valori delle variabili in set di variabili specifici, vengono ignorati i valori predefiniti e vengono modificati i valori del set di variabili selezionato.
È possibile, ad esempio, impostare i seguenti valori per i set di variabili: *Adobe-set1* e *Adobe-set2*.


**Set di variabili 1**: *set di Adobi 1*

* ProductName: ProductA
* Numero di versione: 2311
* Data di rilascio: 11/02/2023


**Set di variabili 2**: *Set di Adobi 2*

* Nome prodotto: ProductB
* Numero di versione: 2310
* Data di rilascio: 09/07/2023

Ogni nuova variabile viene aggiunta a tutti i set di variabili. Quando elimini o duplichi una variabile, questa viene aggiornata per tutti i set di variabili.

Puoi anche visualizzare in anteprima i valori per un set di variabili.
Ad esempio, per il set di variabili *Adobe-Set1*, è stato definito il valore della variabile ProductName come &quot;ProductA&quot;, quindi il valore viene visualizzato nell&#39;anteprima nell&#39;editor di variabili.

![anteprima variabile dall&#39;editor variabili](assets/variables-editor-preview.png){width="550" align="left"}

*Visualizza in anteprima il valore definito nel set di variabili selezionato.*

### Reimpostare il valore di una variabile

Se hai modificato il valore, puoi anche reimpostare una variabile sul valore predefinito.
Ripristina <img alt= "icona di ripristino" src="./assets/application-variable-revert.svg" width="25"> viene visualizzato per una variabile con un valore modificato.
Ad esempio, è possibile reimpostare il valore della variabile ProductName sul valore predefinito Experience Manager Guides.

## Utilizzare le variabili nei modelli di PDF nativi

È possibile aggiungere variabili durante la generazione dell’output dei documenti di prodotto per renderli portatili e facili da aggiornare. È possibile inserire queste variabili all&#39;interno del layout di pagina visualizzato nelle diverse pagine dei documenti. Ad esempio, è possibile aggiungere la variabile ProductName che viene visualizzata nell&#39;area dell&#39;intestazione del layout di pagina (o in qualsiasi altra parte come il piè di pagina o il corpo).



Per inserire una variabile come ProductName nell&#39;area dell&#39;intestazione, effettuare le seguenti operazioni:
1. Apri il layout di pagina richiesto per la modifica.

   >[!NOTE]
   >
   > Visualizza la sezione [Personalizza layout di pagina](../native-pdf/components-pdf-template.md#customize-a-page-layout-customize-page-layout) per aprire un layout di pagina per personalizzarlo o modificarlo.

1. Seleziona l’intestazione per rendere attiva l’inserimento di una variabile.

1. È possibile inserire la variabile in due modi:

   **Dal pannello Variabili sul lato sinistro**

   * Trascinate una variabile dal **pannello Variabili** e rilasciatela nell&#39;area dell&#39;intestazione.

   **Dalla barra degli strumenti**

   1. Seleziona **Inserisci variabile/campi** <img alt= "icona variabile" src="./assets/variables-icon.svg" width="25">.
   1. Nella finestra di dialogo **Variabile** selezionare il nome della variabile per inserirla nell&#39;area dell&#39;intestazione.
   1. È inoltre possibile immettere la stringa di ricerca nella casella di testo. I nomi delle variabili contenenti la stringa specificata vengono filtrati e visualizzati nell’elenco. La variabile selezionata viene inserita nell’area dell’intestazione. Puoi visualizzare il valore predefinito della variabile.
   1. Per sostituire una variabile, fare doppio clic sul valore della variabile e selezionare un&#39;altra variabile dalla finestra di dialogo **Variabile**. La variabile viene sostituita.


## Genera output PDF con variabili

Puoi generare l’output PDF con i valori di variabili diverse. Prima di generare il layout, scegli un set di variabili dall&#39;elenco a discesa **Set di variabili** di un predefinito di output per sceglierne i valori.

![elenco a discesa set di variabili](assets/output-preset-variable-dropdown.png){width="550" align="left"}

*Seleziona un set di variabili dal menu a discesa nel predefinito di output che desideri utilizzare per generare l&#39;output PDF.*

>[!NOTE]
>
> È inoltre possibile selezionare (Predefinito) dal menu a discesa per pubblicare i valori predefiniti per tutte le variabili.

A seconda del set di variabili scelto, otterrai un output corrispondente ai valori delle variabili definiti nel set di variabili. Se ad esempio si seleziona il set di variabili *Adobe-set1*, nell&#39;output verranno visualizzati i valori delle variabili definiti in questo set.


<img src="assets/variable-pdf-output.png" alt="Output PDF con variabili" width="500" border="2px">

*Genera l&#39;output di PDF utilizzando le variabili nel layout di pagina.*

Potete anche aggiornare rapidamente i valori di qualsiasi insieme di variabili ogni volta che è necessario e rigenerare l&#39;output. Ad esempio, se è necessario aggiornare i dettagli di una versione, è possibile aggiornare il valore della versione nella variabile VersionNumber e rigenerare l&#39;output.
