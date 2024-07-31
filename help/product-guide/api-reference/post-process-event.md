---
title: Gestore di eventi di post-elaborazione
description: Scopri il gestore di eventi di post-elaborazione
exl-id: 3b105ff5-02d4-40e3-a713-206a7fcf18b2
feature: Post-Processing Event Handler
role: Developer
level: Experienced
source-git-commit: 83966cc9187b13dd3b5956821e0aa038b41db28e
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 5%

---

# Gestore di eventi di post-elaborazione {#id175UB30E05Z}

AEM Guides espone com/adobe/fmdita/postprocess/complete event utilizzato per eseguire eventuali operazioni di post-elaborazione. Questo evento viene attivato ogni volta che si esegue un&#39;operazione su un file DITA. Le seguenti operazioni su un file DITA attivano questo evento:

>[!NOTE]
>
> Questo evento non viene attivato per l’operazione di eliminazione in AEM 6.1.

- Carica
- Creazione
- Modifiche
- Eliminazione

È necessario creare un gestore eventi AEM per leggere le proprietà disponibili in questo evento ed eseguire ulteriori elaborazioni.

I dettagli dell’evento sono spiegati di seguito:

**Nome evento**:

```
com/adobe/fmdita/postprocess/complete 
```

**Parametri**:

| Nome | Tipo | Descrizione |
|----|----|-----------|
| `path` | Stringa | Percorso del file che ha attivato l&#39;evento. In genere si tratta del file su cui è stata eseguita un&#39;operazione. |
| `status` | Stringa | Stato di ritorno per l&#39;operazione eseguita. Le opzioni possibili sono: - <br>- OPERAZIONE RIUSCITA: l&#39;operazione di post-elaborazione è stata completata. <br>- COMPLETATO CON ERRORI: operazione di post-elaborazione completata, ma con alcuni errori. <br>- NON RIUSCITO: operazione di post-elaborazione non riuscita a causa di un errore irreversibile. |
| `message` | Stringa | Nel caso in cui lo stato sia COMPLETATO CON ERRORI o NON RIUSCITO, questo parametro contiene i dettagli sull’errore o sul motivo dell’errore. |
| `operation` | Stringa | Operazione di post-elaborazione eseguita sul file. Le opzioni possibili sono:<br>- Aggiunta <br>- Aggiornamento <br>- Eliminazione |
