---
title: Sostituzioni configurazione
description: Scopri come eseguire le sostituzioni della configurazione
exl-id: dc5f81f7-5b0a-4d12-a944-ba66b0239d5c
feature: Installation
role: Admin
level: Experienced
source-git-commit: e4b213b5f0efda18fb24f100f3ee8237947890bf
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 0%

---

# Sostituzioni configurazione {#id216IFC003XA}

Per apportare qualsiasi aggiornamento alla configurazione, si deve utilizzare il seguente approccio generico:

1. Accedi all’archivio Git di Cloud Manager.

1. Crea un nuovo file JSON nella posizione seguente:

   src/main/content/jcr\_root/apps/fmditaCustom/config/

1. Denomina il file nel formato seguente:

   $\{PID\}.cfg.json

   In questo caso, il PID è l’ID processo della configurazione.

1. Aggiungi le proprietà nel file JSON utilizzando il seguente formato:

   ```
   {
      "aem.adminuname": "updatedUserjson",
      "valid.characters": "[-a-zA-Z0-9_@$]",
      "dita.serialization": true
   }
   ```

1. Apporta le modifiche ed esegui la pipeline Cloud Manager per distribuire la configurazione aggiornata.

## Configurare l’interfaccia utente di Experience Manager Guides

La versione 2025.02.0 di Adobe Experience Manager Guides offre un’interfaccia utente rinnovata e funzioni migliorate per consentirti di lavorare in modo più rapido ed efficiente che mai. Tra questi, una pagina Home completamente nuova, una barra degli strumenti dell’editor più pulita e organizzata, una console di mappe dedicata e funzioni avanzate.

Per garantire una transizione fluida e ridurre al minimo le interruzioni, Experience Manager Guides fornisce un’opzione di configurazione che consente di tornare alla vecchia interfaccia utente ( e viceversa) in base alle esigenze.

>[!IMPORTANT]
>
> Questa opzione di configurazione per passare dalla nuova alla vecchia interfaccia utente era supportata fino alla versione 2025.4.0. Con la versione 2025.6.0 di, questa impostazione è obsoleta e non può più essere utilizzata per ripristinare la vecchia interfaccia utente.

Per configurare l’interfaccia utente di Experience Manager Guides, effettua le seguenti operazioni:

1. Apri Adobe Experience Manager, quindi seleziona il programma contenente l’ambiente da configurare.
2. Passa alla scheda **Ambienti**.
3. Seleziona il nome dell’ambiente da configurare. Dovresti passare alla pagina **Informazioni sull&#39;ambiente**.
4. Passa alla scheda **Configurazione**.
5. Seleziona **Aggiungi/Aggiorna**.
6. Aggiungi i dettagli di configurazione dell’interfaccia utente. Assicurati di usare lo stesso nome e la stessa configurazione forniti nella schermata seguente.

   ![](assets/enable-penultimate-ui.png){width="800" align="left"}

   Impostando il valore su **true** si mantiene la vecchia interfaccia utente, mentre **false** attiva la nuova interfaccia utente.



**Argomento padre:**&#x200B;[&#x200B; Scarica e installa](download-install.md)
