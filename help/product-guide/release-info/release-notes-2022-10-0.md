---
title: Note sulla versione | Adobe Experience Manager Guides as a Cloud Service, versione di ottobre 2022
description: Versione di ottobre di Adobe Experience Manager Guides as a Cloud Service
exl-id: 38638080-625c-49c3-9e54-56cc23831546
feature: Release Notes
role: Leader
TQID: https://experienceleague.adobe.com/w-fw81jYGDRDrmn98Dzn-hYIkOZzT0B3-4-y-bcxdz4
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dca
subfeature_v2: id: d5ea0417-7932-4688-a3e2-4d3b2e7076a3id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2: id: f8a45b24-4be7-4f1b-909b-60d06b483a20
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 489
ht-degree: 3%

---

# Versione di ottobre di Adobe Experience Manager Guides as a Cloud Service

## Aggiornamento alla versione di ottobre

Aggiorna la configurazione corrente di Adobe Experience Manager Guides as a Cloud Service (in seguito denominato *AEM Guides as a Cloud Service*) eseguendo i seguenti passaggi:
1. Consulta il codice Git dei servizi cloud e passa al ramo configurato nella pipeline dei servizi cloud corrispondente all’ambiente da aggiornare.
1. Aggiorna la proprietà `<dox.version>` nel file `/dox/dox.installer/pom.xml` del codice Git dei servizi cloud a 2022.10.183.
1. Apporta le modifiche ed esegui la pipeline dei servizi cloud per l’aggiornamento alla versione di ottobre di AEM Guides as a Cloud Service.

## Matrice di compatibilità

In questa sezione è elencata la matrice di compatibilità per le applicazioni software supportate dalla versione di ottobre 2022 di AEM Guides as a Cloud Service.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| FMPS | FrameMaker |
| --- | --- |
| Non compatibile | Aggiornamento 2020 4 e versioni successive |
| | |

*Le condizioni di base e create in AEM sono supportate nelle versioni FMPS a partire dal 2020.2.

### Connettore ossigeno

| Versione di AEM Guides as a Cloud | Finestre del connettore dell&#39;ossigeno | Connettore di ossigeno Mac | Modifica in finestre a ossigeno | Modifica in Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2022.10.0 | 2.7.13 | 2.7.13 | 2,3 | 2,3 |
|  |  |  |  |  |


## Nuove funzioni e miglioramenti

AEM Guides as a Cloud Service fornisce miglioramenti e nuove funzioni nella versione di ottobre:


### Pannello Generazione rapida

Ora AEM Guides fornisce il pannello **Generazione rapida** che consente di generare e visualizzare rapidamente l&#39;output dei predefiniti creati per la mappa DITA.

![Icona Generazione rapida](assets/quick-generate-icon.png)

Nel pannello **Generazione rapida** è possibile visualizzare l&#39;elenco di tutti i predefiniti di output creati per la mappa DITA.

![Generazione rapida pannello](assets/quick-generate-panel.png)

Seleziona uno o più predefiniti e genera rapidamente l’output. Potete anche visualizzare rapidamente l&#39;output generato per i predefiniti. Alla generazione dell’output viene visualizzato un messaggio di successo. Se la generazione dell’output non riesce, viene visualizzato un messaggio di errore. Puoi anche visualizzare il registro degli errori per visualizzare i dettagli dell’errore che si è verificato nel processo di generazione.


## Problemi risolti

Di seguito sono elencati i bug risolti in varie aree:

* PDF nativo | Errore durante la rimozione degli argomenti relativi alle sole risorse dall&#39;output di PDF. (10554)
* PDF nativo | I tasti vuoti vengono visualizzati nell&#39;output di PDF. (10553)
* PDF nativo | `navtitle` per `topichead` non è rispettato. (10509)
* PDF nativo | Supporto necessario per le versioni JDK amd64. (10465)
* PDF nativo | Non è possibile nascondere gli argomenti relativi al frontespizio dal sommario. (10355)
* PDF nativo | Riavviando il numero di pagina nel layout del capitolo, la numerazione inizia in modo casuale dalla fine del capitolo precedente. (10154)
* Browser Chrome | Lo schermo si oscura quando si trascina un elemento dall’interfaccia utente. Ad esempio, quando si trascina una condizione dal pannello Condizioni. (10524)
* Le proprietà del nodo vengono rimosse dopo l’operazione di copia e incolla di una risorsa. (10053)
* Facendo clic su **Chiudi** gli utenti venivano reindirizzati alle risorse. L&#39;esperienza è stata corretta per portare gli utenti alla home page di AEM. (9654)
