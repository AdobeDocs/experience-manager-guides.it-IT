---
title: Note sulla versione | Istruzioni per l’aggiornamento e problemi risolti in Adobe Experience Manager Guides, versione 2026.03.0
description: Scopri la matrice di compatibilità e come effettuare l’aggiornamento alla versione 2026.03.0 di Adobe Experience Manager Guides as a Cloud Service.
exl-id: 5700e649-104d-4caf-a195-6e667a71faee
hidefromtoc: true
source-git-commit: 22ea3fe3ccb974fe3795299f7815e7aae78d41e7
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 11%

---

# Istruzioni per l’aggiornamento alla versione 2026.03.0

Questo articolo descrive le istruzioni per l’aggiornamento e la matrice di compatibilità per la versione 2026.03.0 di Adobe Experience Manager Guides as a Cloud Service.

Per ulteriori informazioni sulle nuove funzioni e sui miglioramenti, consulta [Novità della versione 2026.03.0](whats-new-2026-03-0.md).

Per un elenco dei problemi risolti in questa versione, consulta [Problemi risolti nella versione 2026.03.0](fixed-issues-2026-03-0.md).

## Matrice di compatibilità

Questa sezione descrive la matrice di compatibilità per le applicazioni software supportate dalla versione 2026.03.0 di Experience Manager Guides as a Cloud Service.

### FRAMEMAKER e FRAMEMAKER PUBLISHING SERVER

| Versione di Experience Manager Guides as a Cloud | FMPS | FrameMaker | Autore ossigeno |
| --- | --- | --- | --- |
| 2026.03.0 | Non compatibile | 2022 o versione successiva | 26,1 |


### Connettore ossigeno

| Versione di Experience Manager Guides as a Cloud | Finestre del connettore dell&#39;ossigeno | Connettore di ossigeno Mac | Modifica in finestre a ossigeno | Modifica in Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2026.03.0 | 3,8-uuid 1 | 3,8-uuid 1 | 2,3 | 2,3 |


### Versione modello sito AEM

| Versione componenti | Versione sito |
|---|---|
| guides-components.all-1.4.0 | aemg-sites-template-1.3.0 |

### Versione modello della Knowledge Base

| Nome pacchetto componenti | Versione componenti | Versione modello |
|---|---|---|
| Pacchetto di contenuti per componenti Experience Manager Guides per Cloud Service | guides-components.all-1.4.0 | aem-site-template-dxml-1.0.17 |

## Aggiornamento alla versione 2026.03.0

Experience Manager Guides viene aggiornato automaticamente dopo l’aggiornamento alla versione più recente di Experience Manager as a Cloud Service.

>[!IMPORTANT]
>
> Questa versione include aggiornamenti alle impostazioni del profilo della cartella (ui_config.json). Se utilizzi impostazioni personalizzate, assicurati di riprenderle prima dell&#39;aggiornamento. Dopo l’aggiornamento, rivedi e regola le impostazioni per allinearle alle modifiche introdotte nell’ultima versione.

Esamina e convalida le configurazioni di configurazione per verificarne la corretta implementazione. Se sono state introdotte modifiche alla configurazione personalizzata, visualizzare [Configurazione aggiuntiva per l&#39;aggiornamento di Cloud Service](../cs-install-guide/additional-config-for-cloud-service.md) per le procedure aggiuntive applicabili alla versione da cui si sta eseguendo l&#39;aggiornamento.
