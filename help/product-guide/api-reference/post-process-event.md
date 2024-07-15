---
title: Gestore eventi di elaborazione Post
description: Scopri il gestore eventi di elaborazione Post
exl-id: 3b105ff5-02d4-40e3-a713-206a7fcf18b2
feature: Post-Processing Event Handler
role: Developer
level: Experienced
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 1%

---

# Gestore eventi di elaborazione Post {#id175UB30E05Z}

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
|Nome|Tipo|Descrizione|
----|----|-----------|
|`path`|Stringa|Percorso del file che ha attivato l&#39;evento. In genere si tratta del file su cui è stata eseguita un&#39;operazione.|
|`status`|Stringa|Lo stato restituito per l&#39;operazione eseguita. Le opzioni possibili sono: - <br>- OPERAZIONE RIUSCITA: l&#39;operazione di post-elaborazione è stata completata. <br>- COMPLETATO CON ERRORI: operazione di post-elaborazione completata, ma con alcuni errori. <br>- NON RIUSCITO: operazione di post-elaborazione non riuscita a causa di un errore irreversibile.|
|`message`|Stringa|Nel caso in cui lo stato sia COMPLETATO CON ERRORI o NON RIUSCITO, questo parametro contiene i dettagli sull&#39;errore o il motivo dell&#39;errore.|
|`operation`|Stringa|L&#39;operazione di post-elaborazione eseguita sul file. Le opzioni possibili sono:<br>- Aggiunta <br>- Aggiornamento <br>- Eliminazione|
