---
title: Icona di configurazione per i tipi dita personalizzati
description: Scopri come definire l’icona per i tipi dita personalizzati per visualizzarne l’icona in diverse interfacce in AEM
exl-id: 5a259ea0-3b5f-4c6e-b488-1586767aa991
source-git-commit: 7355f48ba8ad0ac15c54be183d9aa91bb88724e8
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 0%

---

# Configurazione dell’icona per i tipi dita (topic o map) personalizzati/specializzati


## Dichiarazione di problema

Con lo schema personalizzato utilizzato in AEM Guides, puoi creare tipi di argomenti o mappe personalizzati e con questo puoi notare che i tipi di argomenti/mappe personalizzati non mostrano l’icona nell’editor web o nell’interfaccia utente di Assets. Vedi la schermata seguente come riferimento

![schermata per riferimento](../assets/authoring/custom-ditatype-icon-notshown.png)


Pertanto, per assegnare un’icona ai tipi di argomento/mappa personalizzati, devi effettuare le seguenti operazioni:
- Trovare il tipo di argomento/mappa personalizzato
- Scrivi gli stili per aggiungere l’icona desiderata per il tipo personalizzato


Possiamo implementare i passaggi precedenti per mostrare l’icona nell’editor web (vista archivio) e nell’interfaccia utente di Assets. Di seguito sono riportati i passaggi per entrambi


## Visualizzazione dell&#39;icona per l&#39;argomento o la mappa personalizzati nella visualizzazione editor Web

_Passaggio 1:_ Determinare il tipo di dita per l&#39;argomento/app dita personalizzato
- Apri la vista archivio in editor web > apri console sviluppatori nel browser
- Inspect lo spazio delle icone accanto all’argomento/mappa elencato
- Controlla la classe assegnata all&#39;argomento personalizzato
- Vedi la schermata seguente per ulteriori dettagli ![Vedi la schermata](../assets/authoring/custom-ditatype-icon-knowditatype.png)
- Questa classe verrà utilizzata per assegnare un&#39;icona e scrivere css per questo

_Passaggio 2:_ Crea CSS e assegna l&#39;icona a questo tipo di dita
- Crea una libreria client in /apps. Supponiamo che si crei una cq:ClientLibraryFolder nel percorso desiderato.
   - aggiungi le categorie &quot;apps.fmdita.xml_editor.page&quot;
- crea una cartella &quot;assets&quot; sotto questa directory e aggiungi tutte le icone che desideri utilizzare per i tipi dita personalizzati
- aggiungi un file css nella cartella della libreria client, ad esempio &quot;tree-icons.css&quot;
   - aggiungi il seguente codice

```
            .tree-item-icon {
                &.custommaptype {
                    background-image: url('assets/custommap.svg')
                }
                &.customtopictype {
                    background-image: url('assets/customtopic.svg')
                }
            }
```

- aggiungi css.txt nella cartella della libreria client e aggiungi il riferimento a &quot;tree-icon.css&quot; appena creato
- salva/implementa queste modifiche

Fai riferimento alla schermata seguente per ulteriori dettagli.
![Riferisci schermata](../assets/authoring/custom-ditatype-icon-define-webeditor-styles.png)

E l&#39;output finale è mostrato nella schermata seguente
![visualizzato nella schermata](../assets/authoring/custom-ditatype-icon-webeditor-showstyles.png)


## Icona visualizzata per argomento/mappa personalizzato nell’interfaccia utente di Assets

_Passaggio 1:_ determinazione del tipo dita dell&#39;argomento/mappa dita personalizzato
- questo è spiegato nel passaggio 1 dei metodi precedenti

_Passaggio 2:_ Crea Javacscript per definire quali icone caricare per il tipo di dita personalizzato per i tipi di argomento/mappa personalizzati
- Crea una libreria client in /apps. Supponiamo che si crei una cq:ClientLibraryFolder nel percorso desiderato.
   - aggiungi le seguenti proprietà:
      - Valore &quot;Categories&quot;(stringa multivalore) come &quot;dam.gui.admin.coral&quot;
      - valore &quot;dependencies&quot;(stringa multivalore) come &quot;libs.fmdita.versioncontrol&quot;
- Crea una copia del file &quot;/libs/fmdita/clientlibs/clientlibs/xmleditor/clientlib-dam/topic_type.js&quot; in questa directory /apps
   - modificare &quot;topic_type.js&quot; copiato e modificare/aggiungere customtopictype nella variabile &quot;typeImageNameMap&quot;
   - È inoltre possibile modificare il percorso della cartella delle immagini modificando il valore della variabile &quot;parentImagePath&quot; in cui sono memorizzate le icone personalizzate
- Crea un file denominato js.txt nella cartella della libreria client e aggiungi un riferimento a &quot;topic_type.js&quot;
- salva/implementa queste modifiche
Fai riferimento alla schermata seguente per ulteriori dettagli.
  ![Riferisci schermata](../assets/authoring/custom-ditatype-icon-define-assetsui-styles.png)

L&#39;output finale verrà visualizzato come mostrato nella schermata ![mostrata nella schermata](../assets/authoring/custom-ditatype-icon-assetsui-showstyles.png)
