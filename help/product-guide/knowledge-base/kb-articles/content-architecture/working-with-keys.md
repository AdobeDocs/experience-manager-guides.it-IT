---
title: Utilizzo delle chiavi
description: Come creare chiavi da utilizzare nei contenuti dell’organizzazione
role: Admin
exl-id: b8e3a6d2-ea82-4fdb-bd16-3f4b6594af52
feature: Use Keys in AEM Guides
source-git-commit: 47e6c57b8a61f02dc4f03594d91ee842bdccef90
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 0%

---

# Creare le chiavi

Le organizzazioni devono utilizzare i tasti nei casi in cui dispongono di testo riutilizzabile e comune, come il nome del prodotto o la tinta del prodotto, che viene utilizzato in molte posizioni ma è soggetto a modifiche. L’utilizzo di chiavi per questo testo riutilizzabile consente di inviare un aggiornamento in più posizioni apportando la modifica in un’unica posizione, ad esempio nel valore chiave.

## Passaggio 1: creare una mappa globale per la memorizzazione delle chiavi

Crea una mappa e aggiungi [!UICONTROL keyref] a esso.

```
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE map PUBLIC "-//OASIS//DTD DITA Map//EN" "technicalContent/dtd/map.dtd">
<mapid="map.ditamap_ffbdbf06-8658-4311-ad84-1c631bba904f">
  <title>global-keys-map</title>
  <keydefkeys="adobe">
    <topicmeta>
      <linktext>Adobe Systems</linktext>
    </topicmeta>
  </keydef>
  <keydefkeys="AEM">
    <topicmeta>
      <linktext>Adobe Experience Manager</linktext>
    </topicmeta>
  </keydef>
</map>
```

Qui hai definito due definizioni, come mostrato sopra, a condizione che [!UICONTROL keyref] as _AEM_ per _Adobe Experience Manager_ testo.

## Passaggio 2: aggiungi questa mappa alla mappa della pubblicazione

```
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE map PUBLIC "-//OASIS//DTD DITA Map//EN" "technicalContent/dtd/map.dtd">
<mapid="map.ditamap_cbf4a96d-e382-4e8c-8830-bcc093fe6638">
  <title>sample-map</title>
  <topicrefhref="sample-topic-using-the-keys.dita"type="topic">
  </topicref>
  <maprefformat="ditamap"href="global-keys-map.ditamap"type="map">
  </mapref>
</map>
```

## Passaggio 3: utilizzare le chiavi per fare riferimento alle variabili definite nella mappa chiave globale

+ Modifica l’argomento e aggiungi il valore chiave utilizzando [!UICONTROL keyref].
+ Come mostrato nella schermata, viene visualizzata una piccola finestra da cui è possibile scegliere le parole chiave. Questo verrà visualizzato quando aggiungi l’elemento &quot;keyword&quot;.
  ![Inserisci elemento](assets/insert_element.png)
  ![Rif. chiave](assets/key_ref.png)

```
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE topic PUBLIC "-//OASIS//DTD DITA Topic//EN" "technicalContent/dtd/topic.dtd">
<topicid="topic.dita_31b00e61-04b5-4193-af7a-68503e88b087">
  <title>sample-topic-using-the-keys</title>
  <shortdesc></shortdesc>
  <body>
    <p>This is a sample topic using the keys defined in the global map</p>
    <p>here i am using the key definition for AEM :<keyword keyref="AEM"></keyword></p>
  </body>
</topic>
```
