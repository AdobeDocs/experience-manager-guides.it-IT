---
title: Configurare un modello di mappa DITA personalizzato
description: Scopri come configurare un modello di mappa DITA personalizzato
exl-id: a0eeb43c-06e4-4922-a005-704e8929063f
feature: Template Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '336'
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


La prossima volta che crei una nuova mappa, il modello viene visualizzato nella pagina Blueprint. Per ulteriori informazioni sulla creazione di una mappa DITA, vedere la guida Utilizzo di Adobe Experience Manager Guides as a Cloud Service.

>[!TIP]
>
> Consulta la sezione *Modelli personalizzati* nella guida alle best practice per le best practice sull&#39;utilizzo dei modelli di mappa personalizzati.

**Argomento padre:**[ Configura modelli di argomento e mappa](conf-template-tags.md)
