---
title: Icona di configurazione per i tipi dita personalizzati
description: Scopri come definire l’icona per i tipi di dita personalizzati per visualizzarne l’icona in diverse interfacce in AEM
exl-id: 5a259ea0-3b5f-4c6e-b488-1586767aa991
TQID: https://experienceleague.adobe.com/OFZePwGXAKS5XhsNcrCqOya-bgEHmtO4yl1IciNUxdQ
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: ab01a588-7dea-43f2-a699-0b3f128465d6id: d90290ec-3e61-4ebd-8649-bcafe0836803
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 496
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

_Passaggio 1 :_Determinare il tipo di dita per l&#39;argomento/app dita personalizzato
- Apri la vista archivio in editor web > apri console sviluppatori nel browser
- Controlla lo spazio delle icone accanto all’argomento o alla mappa elencati
- Controlla la classe assegnata all&#39;argomento personalizzato
- Vedi la schermata seguente per ulteriori dettagli ![Vedi la schermata](../assets/authoring/custom-ditatype-icon-knowditatype.png)
- Questa classe verrà utilizzata per assegnare un&#39;icona e scrivere css per questo

_Passaggio 2 :_Crea CSS e assegna l&#39;icona a questo tipo di dita
- Crea una libreria client in /apps, supponiamo che tu crei un cq:ClientLibraryFolder nel percorso desiderato
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

_Passaggio 1 :_che determina il tipo dita dell&#39;argomento/mappa dita personalizzato
- questo è spiegato nel passaggio 1 dei metodi precedenti

_Passaggio 2 :_Crea JavaScript per definire quali icone caricare per il tipo di dita personalizzato per i tipi di argomento/mappa personalizzati
- Crea una libreria client in /apps, supponiamo che tu crei un cq:ClientLibraryFolder nel percorso desiderato
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
