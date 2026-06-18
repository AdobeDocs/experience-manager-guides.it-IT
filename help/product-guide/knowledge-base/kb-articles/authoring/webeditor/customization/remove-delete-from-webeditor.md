---
title: Rimuovi l’opzione Elimina dal menu di scelta rapida dei file nell’editor web per utenti specifici
description: Scopri come personalizzare l’editor web rimuovendo l’opzione Elimina dal menu di scelta rapida dei file per utenti/gruppi specifici
exl-id: 31b4dd53-3938-42e1-bbc6-64806d668696
TQID: https://experienceleague.adobe.com/dzbMsXUoEibR5QxKB-Z-h4qGnQaX2NmIYLTtxVJHE-A
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: cc73b81787a3c3dbe8390d93e558064327e59965
workflow-type: tm+mt
source-wordcount: 240
ht-degree: 0%

---

# Rimuovi l’opzione Elimina dal menu di scelta rapida dei file nell’editor web

Questo articolo illustra come nascondere l’opzione Elimina dal menu di scelta rapida dei file nell’editor di AEM Guides per utenti o gruppi specifici. Per altre personalizzazioni sulle opzioni del menu di scelta rapida dei file, controlla il framework dell’estensione delle guide. Ulteriori dettagli sono disponibili [qui](https://github.com/adobe/guides-extension/tree/main).

Come puoi vedere dallo snippet qui sotto, il menu di scelta rapida del file presenta l’opzione Elimina disponibile per questo utente specifico.

![Menu di scelta rapida file con eliminazione](../../../assets/authoring/file-contextmenu-Delete.png)

Ora vediamo come nascondere l’opzione &quot;Elimina&quot; per questo utente.

## Passaggi di implementazione:

- Passa a Strumenti > Sicurezza > Autorizzazioni dalla pagina Home di AEM.
- Scegliere il gruppo o l&#39;utente dalla casella di ricerca.
- Fai clic su &quot;Aggiungi ACE&quot; dall’angolo in alto a destra.
- Scegli il percorso della cartella.
- Includere i privilegi &quot;jcr:removeChildNodes&quot; e &quot;jcr:removeNode&quot;.
- Scegli &quot;Tipo di autorizzazione&quot; come &quot;Nega&quot; e fai clic su &quot;Aggiungi&quot; come mostrato di seguito.

![Autorizzazione utente negata ACE](../../../assets/authoring/permission-ACE-Delete.png)

![Elenco di controllo degli accessi nelle autorizzazioni](../../../assets/authoring/delete-acl.png)

### Test

- Accedi ad AEM come utente per il quale sono stati aggiunti gli ACE.
- Apri l’editor web.
- Passare alla visualizzazione del repository e scegliere la cartella per la quale sono stati aggiunti gli ACE.
- Aprire il menu di scelta rapida dei file.
- L&#39;opzione &#39;Elimina&#39; non verrà visualizzata nel menu di scelta rapida.

Il menu di scelta rapida del file sarà ora simile al seguente:

![Menu di scelta rapida file senza eliminazione](../../../assets/authoring/file-contextmenu-Delete-removed.png)

```
Please note that these steps would also remove 'move' and 'rename' options from the Editor as they are also tied to delete process at the backend.
```
