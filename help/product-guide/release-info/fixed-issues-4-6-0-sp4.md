---
title: Note sulla versione | Sono stati risolti i problemi in Adobe Experience Manager Guides 4.6.0 Service Pack 4
description: Scopri le correzioni di bug nella versione 4.6.0 Service Pack 4 di Adobe Experience Manager Guides
role: Leader
source-git-commit: f9a03ae620a362989a36ebaefb264ea28220a4b3
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 1%

---

# Sono stati risolti i problemi nella versione 4.6.0 Service Pack 4 (aprile 2025)


Questo articolo descrive i bug corretti in varie aree della versione 4.6.0 Service Pack 4 di Adobe Experience Manager Guides.

Informazioni sulle [istruzioni di aggiornamento per la versione 4.6.0 Service Pack 4](upgrade-instructions-4-6-0-sp4.md).

## Authoring

- Se si trascina un&#39;immagine all&#39;interno di un argomento nella visualizzazione **Autore**, il riferimento all&#39;immagine verrà interrotto e i dati andranno perduti. (25769)
- Il trascinamento di un `topicref` all&#39;interno di una mappa nella visualizzazione **Autore** non riesce a eseguire l&#39;operazione prevista e rimuove `topicref` accanto a `topicref` trascinato. (19460)
- Se non si chiudono le connessioni della sessione JCR durante l’aggiornamento o la creazione di argomenti, si verificano perdite di memoria e tempi di inattività del servizio. (26282)

## Pubblicazione

- La pubblicazione nativa di PDF continua a tempo indeterminato se il contenuto DITA ha un collegamento a Internet senza avere ambito come `external`. (26434)
- Quando si crea una nuova linea di base con un numero elevato di etichette, il caricatore delle etichette non riesce e impedisce il recupero delle etichette. (16232)
- La pubblicazione di PDF nativi e di siti AEM si blocca e viene messa in coda, in presenza di errori nel contenuto. (26516)

## Problemi noti

Adobe ha identificato il seguente problema noto per questa versione:

- La pubblicazione nativa di PDF in Windows ha esito negativo quando il contenuto DITA contiene un collegamento esterno che non include l&#39;attributo `scope`.
