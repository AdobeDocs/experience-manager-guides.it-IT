---
title: Carica file
description: Scopri come caricare i file nell’archivio AEM e gestire gli errori. Conoscere l’interfaccia utente della console Assets, l’app desktop AEM, l’acquisizione in blocco delle risorse e utilizzare FrameMaker per il caricamento in blocco.
exl-id: b5430242-1122-43df-a0b2-275b1dea33f2
feature: Content Management
role: User
TQID: https://experienceleague.adobe.com/GG5Bx2yyJz2GaQFmMsDZ6wq6xzb4XUAsSBxEkRNvEVE
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 536
ht-degree: 0%

---

# Carica file {#id176FF000JUI}

Probabilmente si dispone di un archivio di contenuti DITA esistenti che si desidera utilizzare con Adobe Experience Manager Guides. Per tali contenuti esistenti, puoi utilizzare uno dei seguenti approcci per caricare in blocco i contenuti nell’archivio Adobe Experience Manager.

>[!IMPORTANT]
>
> Visualizza [Aggiungi risorse digitali ad Adobe Experience Manager as a Cloud Service Assets](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html?lang=it) per informazioni dettagliate sui metodi di caricamento dei contenuti supportati in Adobe Experience Manager.

## Interfaccia utente della console Assets

Per [aggiungere risorse digitali ad Adobe Experience Manager as a Cloud Service Assets](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html?lang=it#filename-handling?lang=it#upload-assets) tramite l&#39;interfaccia utente della console Assets, seleziona la risorsa richiesta sul desktop e trascina l&#39;interfaccia utente di Adobe Experience Manager \(browser Web\) nella cartella di destinazione. Durante il caricamento delle risorse, accertati che i nomi dei file non includano caratteri non supportati o non consentiti.

Per ulteriori dettagli, visualizzare la sezione [Gestione del nome file e caratteri non consentiti](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html?lang=it#filename-handling) nella documentazione di Adobe Experience Manager.

## App desktop Adobe Experience Manager

Se sei un professionista creativo e desideri gestire le risorse sul desktop locale, utilizza l’app desktop Adobe Experience Manager. Puoi aprire e modificare queste risorse con le tue applicazioni desktop. Puoi anche gestire le versioni e condividere i file con altri utenti. Per ulteriori dettagli, visualizzare [app desktop Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-desktop-app/using/using.html?lang=it).

## Acquisizione in blocco delle risorse

In caso di migrazioni su larga scala e acquisizioni in blocco occasionali, utilizza l’acquisizione in blocco delle risorse per caricare i contenuti. Utilizzando questo strumento, puoi caricare contenuti in blocco da archivi di dati supportati come Azure o S3. Per ulteriori dettagli, visualizza [Asset Bulk Ingestor](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html?lang=it#asset-bulk-ingestor).

## Utilizza FrameMaker per il caricamento in blocco

Adobe FrameMaker viene fornito con un potente connettore Adobe Experience Manager che consente di caricare facilmente i documenti DITA e FrameMaker esistenti \(`.book` e `.fm`\) in Adobe Experience Manager. Puoi utilizzare varie funzionalità di caricamento dei file, ad esempio il caricamento di un singolo file e di una cartella completa con o senza dipendenze \(come riferimenti a contenuti, riferimenti incrociati e elementi grafici\).

Per ulteriori dettagli sull&#39;utilizzo della funzionalità di caricamento in blocco in FrameMaker, vedere la sezione *Creare una cartella CRX e caricare i file* nella Guida utente di FrameMaker.

## Gestione degli errori durante il caricamento del contenuto {#id201MI0I04Y4}

In caso di errore durante il caricamento di uno o più file, al termine del processo di caricamento viene visualizzato un messaggio con un elenco dei file che non è stato possibile caricare, come illustrato nello snippet riportato di seguito.

![](images/uuid-files-failed-to-upload_cs.png){width="650" align="center"}

Per ulteriori dettagli sul funzionamento dei vari scenari di caricamento dei file, visualizzare [Gestione file e cartelle](authoring-file-management.md#).

Se utilizzi uno strumento come Adobe Experience Manager Desktop App o Asset Bulk Ingestor, l’azione da eseguire su un file duplicato è controllata da un’impostazione nel server Adobe Experience Manager. Contatta l’amministratore di sistema per informazioni su questa configurazione.

**Argomento padre:**&#x200B;[&#x200B; Gestisci contenuto](authoring.md)
