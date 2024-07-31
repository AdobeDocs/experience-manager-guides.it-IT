---
title: Gestore di eventi del processo di conversione
description: Informazioni sul gestore eventi del processo di conversione
exl-id: 8033935d-2113-4e39-ab74-b7431b89f948
feature: Conversion Process Event Handler
role: Developer
level: Experienced
source-git-commit: 83966cc9187b13dd3b5956821e0aa038b41db28e
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 3%

---

# Gestore di eventi del processo di conversione {#id175UB30E05Z}

AEM Guides espone com/adobe/fmdita/conversion/complete event utilizzato per eseguire eventuali operazioni di post-elaborazione dopo il completamento di un processo di conversione dei documenti. Questo evento viene attivato ogni volta che viene eseguita la migrazione di un documento non DITA nel formato di file DITA. Se ad esempio si esegue un processo di conversione da Word a DITA o da InDesign a DITA, questo evento viene richiamato al termine del processo di conversione.

È necessario creare un gestore eventi AEM per leggere le proprietà disponibili in questo evento ed eseguire ulteriori elaborazioni.

I dettagli dell’evento sono spiegati di seguito:

**Nome evento**:

```HTTP
com/adobe/fmdita/conversion/complete 
```

**Parametri**:

| Nome | Tipo | Descrizione |
|----|----|-----------|
| `status` | Stringa | Stato di ritorno per l&#39;operazione eseguita. Le opzioni possibili sono: -   OPERAZIONE RIUSCITA: il processo di conversione è stato completato. <br> -   COMPLETATO CON ERRORI: il processo di conversione è stato completato, ma con alcuni errori. <br>-   FAILED: processo di conversione non riuscito a causa di un errore irreversibile. |
| `filePath` | Stringa | Percorso assoluto del file di origine \(da convertire\) nell’archivio AEM. |
| `outputPath` | Stringa | Percorso assoluto della posizione di destinazione in cui verranno salvati i file DITA convertiti. |
| `logPath` | Stringa | Percorso assoluto del nodo in cui verrà salvato il registro di conversione. |
