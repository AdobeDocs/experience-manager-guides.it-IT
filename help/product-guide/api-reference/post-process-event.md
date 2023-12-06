---
title: Gestore di eventi di post-elaborazione
description: Scopri il gestore di eventi di post-elaborazione
exl-id: 3b105ff5-02d4-40e3-a713-206a7fcf18b2
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 1%

---

# Gestore di eventi di post-elaborazione {#id175UB30E05Z}

Le guide dell’AEM espongono l’evento com/adobe/fmdita/postprocess/complete utilizzato per eseguire eventuali operazioni di post-elaborazione. Questo evento viene attivato ogni volta che si esegue un&#39;operazione su un file DITA. Le seguenti operazioni su un file DITA attivano questo evento:

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

**Parametri**: |Nome|Tipo|Descrizione| ----|----|-----------| |`path`|String|Percorso del file che ha attivato l&#39;evento. In genere si tratta del file su cui è stata eseguita un&#39;operazione.| |`status`|Stringa|Lo stato restituito per l&#39;operazione eseguita. Le opzioni possibili sono: - <br>- OPERAZIONE RIUSCITA: operazione di post-elaborazione completata. <br>- COMPLETATO CON ERRORI: l’operazione di post-elaborazione è stata completata, ma con alcuni errori. <br>- NON RIUSCITO: operazione di post-elaborazione non riuscita a causa di un errore irreversibile.| |`message`|String|Nel caso in cui lo stato sia COMPLETED WITH ERRORS o FAILED, questo parametro contiene i dettagli relativi all&#39;errore o al motivo dell&#39;errore.| |`operation`|Stringa|L&#39;operazione di post-elaborazione eseguita sul file. Le opzioni possibili sono:<br>- Aggiunta <br>- Aggiornamento <br>- Eliminazione|
