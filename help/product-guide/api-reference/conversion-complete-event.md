---
title: Gestore di eventi del processo di conversione
description: Informazioni sul gestore eventi del processo di conversione
exl-id: 8033935d-2113-4e39-ab74-b7431b89f948
feature: Conversion Process Event Handler
role: Developer
level: Experienced
TQID: https://experienceleague.adobe.com/VhlUaVSMTZpfyh5MiJI0WHFpc46s41xjLbuLMUnKH58
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 191
ht-degree: 3%

---

# Gestore di eventi del processo di conversione {#id175UB30E05Z}

AEM Guides espone com/adobe/fmdita/conversion/complete event utilizzato per eseguire eventuali operazioni di post-elaborazione dopo il completamento di un processo di conversione dei documenti. Questo evento viene attivato ogni volta che viene eseguita la migrazione di un documento non DITA nel formato di file DITA. Se, ad esempio, si esegue una conversione da Word a DITA o un processo di conversione da InDesign a DITA, questo evento viene richiamato al termine del processo di conversione.

È necessario creare un gestore eventi di AEM per leggere le proprietà disponibili in questo evento ed eseguire ulteriori elaborazioni.

I dettagli dell’evento sono spiegati di seguito:

**Nome evento**:

```HTTP
com/adobe/fmdita/conversion/complete 
```

**Parametri**:

| Nome | Tipo | Descrizione |
|----|----|-----------|
| `status` | Stringa | Stato di ritorno per l&#39;operazione eseguita. Le opzioni possibili sono: - OPERAZIONE RIUSCITA: il processo di conversione è stato completato correttamente. <br> - COMPLETATO CON ERRORI: processo di conversione completato, ma con alcuni errori. <br>- NON RIUSCITO: processo di conversione non riuscito a causa di un errore irreversibile. |
| `filePath` | Stringa | Percorso assoluto del file di origine \(da convertire\) nell’archivio AEM. |
| `outputPath` | Stringa | Percorso assoluto della posizione di destinazione in cui verranno salvati i file DITA convertiti. |
| `logPath` | Stringa | Percorso assoluto del nodo in cui verrà salvato il registro di conversione. |
