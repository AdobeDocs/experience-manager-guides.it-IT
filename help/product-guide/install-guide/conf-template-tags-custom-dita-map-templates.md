---
title: Configurare un modello di mappa DITA personalizzato
description: Scopri come configurare un modello di mappa DITA personalizzato
exl-id: ea8a6687-1a7b-45c7-8cbc-161f9e88a8be
feature: Template Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/16cGf5xY2tAfhc0qIBZeUhYTes-RrdRp-Kj-MoTuacE
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: a7bba4a6-624b-4427-a9b8-dd411a1bfd41
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
  - id: df6fa66f-4542-4a6d-90ca-9f146eb5d494
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 336
ht-degree: 1%

---

# Configurare un modello di mappa DITA personalizzato {#id1774F04F05Z}

AEM Guides viene fornito con due modelli di mappe preconfigurati: Mappa DITA e Mappa libro. È possibile creare mappe in base a questi modelli oppure definire modelli di mappe personalizzati che possono essere utilizzati per creare nuove mappe.

Per aggiungere modelli di mappa personalizzati, effettua le seguenti operazioni:

1. Accedi a Adobe Experience Manager come amministratore.

1. Nell’interfaccia utente di Assets, passa alla cartella configurata per memorizzare i file del modello di mappa. Per impostazione predefinita, tutti i modelli di mappa sono memorizzati nella cartella /content/dam/dita-templates/maps.

   >[!NOTE]
   >
   > Per configurare un percorso personalizzato per l&#39;archiviazione di modelli di argomento o mappa, vedere [Configurare il percorso della cartella dei modelli DITA personalizzati](conf-template-tags-custom-dita-topic-template.md#id191LCF0095Z)

1. Fare clic su **Crea** \> **Modello DITA**.

1. Nella pagina Blueprint, seleziona il tipo di modello di mappa da creare.

   >[!NOTE]
   >
   > Puoi utilizzare il modello Mappa o Mappa libro come base per il nuovo modello.

1. Fai clic su **Avanti**.

1. Nella pagina Proprietà nuovo modello, immetti un **Titolo** e un **Nome** per il modello.

   >[!NOTE]
   >
   > Il nome viene suggerito automaticamente in base al Titolo del modello. Se desideri specificare manualmente il nome, accertati che il Nome non contenga spazi, apostrofi o parentesi graffe e termini con .ditamap.

1. Fai clic su **Crea**.

   Viene visualizzato il messaggio Mappa creata.

   È possibile scegliere di aprire il modello per la modifica nell&#39;Editor mapping o di salvare il file modello nel percorso dell&#39;archivio modelli. Una volta creato il modello, puoi utilizzare l’Editor mappa per personalizzarlo in base alle tue esigenze di authoring. Una volta installato un modello, accertati di associarlo a un profilo globale o a livello di cartella.


La prossima volta che crei una nuova mappa, il modello viene visualizzato nella pagina Blueprint. Per ulteriori informazioni sulla creazione di una mappa DITA, vedere *Utilizzo di Adobe Experience Manager Guides*.

>[!TIP]
>
> Consulta la sezione *Modelli personalizzati* nella guida alle best practice per le best practice sull&#39;utilizzo dei modelli di mappa personalizzati.

**Argomento padre:** [Configura modelli di argomento e mappa](conf-template-tags.md)
