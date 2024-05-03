---
title: Icona di configurazione per i tipi dita personalizzati
description: Scopri come definire l’icona per i tipi dita personalizzati per visualizzarne l’icona in diverse interfacce in AEM
source-git-commit: ce2f5e4ab6b05fbce7b8384ff59091ebf9bab7be
workflow-type: tm+mt
source-wordcount: '484'
ht-degree: 0%

---

# Configurazione dell’icona per i tipi dita personalizzati (topic o map)


## Dichiarazione di problema

Con lo schema personalizzato utilizzato nelle guide dell’AEM, puoi creare tipi di argomenti o mappe personalizzati e con questo puoi notare che gli argomenti o le mappe personalizzati non mostrano l’icona nell’editor web o nell’interfaccia utente di Assets. Vedi la schermata come riferimento  (../assets/authoring/custom-ditatype-icon-notshown.png)

Per assegnare un’icona ai tipi di argomento/mappa personalizzati, devi effettuare le seguenti operazioni:
- Trovare il tipo di argomento/mappa personalizzato
- Scrivi gli stili per aggiungere l’icona desiderata per il tipo personalizzato


Possiamo implementare i passaggi precedenti per mostrare l’icona nell’editor web (vista archivio) e nell’interfaccia utente di Assets. Di seguito sono riportati i passaggi per entrambi


## Visualizzazione dell&#39;icona per l&#39;argomento o la mappa personalizzati nella visualizzazione editor Web

Passaggio 1: determinare il tipo di dita per l’argomento/mappa dita personalizzata - Aprire la visualizzazione archivio in editor web > aprire la console per sviluppatori sul browser - Inspect lo spazio delle icone accanto all’argomento/mappa elencato - Controllare la classe assegnata all’argomento personalizzato - Vedere la schermata  (../assets/authoring/custom-ditatype-icon-knowditatype.png) per ulteriori dettagli - Questa classe verrà utilizzata per assegnare un&#39;icona e scrivere css per questo

Passaggio 2: creare css e assegnare l&#39;icona a questo tipo dita - Creare una libreria client in /apps, ad esempio creare una cq:ClientLibraryFolder nel percorso desiderato - aggiungere categorie &quot;apps.fmdita.xml_editor.page&quot; - creare una cartella &quot;assets&quot; in questa directory e aggiungere tutte le icone che si desidera utilizzare per i tipi dita personalizzati - aggiungere un file css nella cartella della libreria client, ad esempio &quot;tree-icons.css&quot; - aggiungere il seguente codice

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

    : aggiungi css.txt nella cartella della libreria client e aggiungi il riferimento a &quot;tree-icon.css&quot; appena creato
    : salva/implementa queste modifiche
Fai riferimento alla schermata  (../assets/authoring/custom-ditatype-icon-define-webeditor-styles.png) per ulteriori dettagli.

E l&#39;output finale è mostrato nella schermata  (../assets/authoring/custom-ditatype-icon-webeditor-showstyles.png)


## Visualizzazione dell’icona per l’argomento o la mappa personalizzati nell’interfaccia utente di Assets

Passaggio 1: determinazione del tipo dita dell&#39;argomento/mappa dita personalizzata - questo è spiegato nel passaggio 1 dei metodi precedenti

Passaggio 2: creare JavaScript per definire le icone da caricare per il tipo di dita personalizzato per i tipi di argomento/mappa personalizzati. Creare una libreria client in /apps. Si supponga di creare un cq:ClientLibraryFolder nel percorso desiderato. Aggiungere le seguenti proprietà: - valore &quot;category&quot;(stringa multivalore) come &quot;dam.gui.admin.coral&quot; - valore &quot;dependencies&quot;(stringa multivalore) come &quot;libs.fmdita.versioncontrol&quot; - Creare una copia del file &quot;/libs/fmdita/clientlibs/clientlibs/xmleditor/clientlib-dam/topic_type.js&quot; in questa directory /apps. Modificare il &quot;topic_type.js&quot; copiato e modificare/aggiungere customtopictype nella variabile &quot;typejs&quot; NameMap&quot; - Puoi anche modificare il percorso della cartella delle immagini modificando il valore della variabile &quot;parentImagePath&quot; in cui sono memorizzate le icone personalizzate - Crea un file denominato js.txt nella cartella della libreria client e aggiungi il riferimento a &quot;topic_type.js&quot; - salva/implementa queste modifiche. Fai riferimento alla schermata  (../assets/authoring/custom-ditatype-icon-define-assetsui-styles.png) per ulteriori dettagli.

L’output finale verrà visualizzato come mostrato nella schermata  (../assets/authoring/custom-ditatype-icon-assetsui-showstyles.png)