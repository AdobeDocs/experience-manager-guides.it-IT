---
title: Gestore di eventi del processo di conversione
description: Informazioni sul gestore eventi del processo di conversione
exl-id: 8033935d-2113-4e39-ab74-b7431b89f948
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 0%

---

# Gestore di eventi del processo di conversione {#id175UB30E05Z}

Le guide AEM espongono com/adobe/fmdita/conversion/complete event che viene utilizzato per eseguire qualsiasi operazione di post-elaborazione dopo il completamento di un processo di conversione dei documenti. Questo evento viene attivato ogni volta che viene eseguita la migrazione di un documento non DITA nel formato di file DITA. Se ad esempio si esegue un processo di conversione da Word a DITA o da InDesign a DITA, questo evento viene richiamato al termine del processo di conversione.

È necessario creare un gestore eventi AEM per leggere le proprietà disponibili in questo evento ed eseguire ulteriori elaborazioni.

I dettagli dell’evento sono spiegati di seguito:

**Nome evento**:

```HTTP
com/adobe/fmdita/conversion/complete 
```

**Parametri**:\
|Nome|Tipo|Descrizione| ----|----|-----------| |`status`|Stringa|Lo stato restituito per l&#39;operazione eseguita. Le opzioni possibili sono: - OPERAZIONE RIUSCITA: il processo di conversione è stato completato correttamente. <br> - COMPLETATO CON ERRORI: il processo di conversione è stato completato, ma con alcuni errori. <br>- NON RIUSCITO: processo di conversione non riuscito a causa di un errore irreversibile.| |`filePath`|String|Percorso assoluto del file di origine \(da convertire\) nell’archivio AEM.| |`outputPath`|Stringa|Percorso assoluto del percorso di destinazione in cui verranno salvati i file DITA convertiti.| |`logPath`|Stringa|Percorso assoluto del nodo in cui verrà salvato il registro di conversione.|
