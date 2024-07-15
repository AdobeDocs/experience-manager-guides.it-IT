---
title: Rimuovi l’opzione Elimina dal menu di scelta rapida dei file nell’editor web per utenti specifici
description: Scopri come personalizzare l’editor web rimuovendo l’opzione Elimina dal menu di scelta rapida dei file per utenti/gruppi specifici
exl-id: 31b4dd53-3938-42e1-bbc6-64806d668696
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 0%

---

# Rimuovi l’opzione Elimina dal menu di scelta rapida dei file nell’editor web

Questo articolo illustra come nascondere l’opzione Elimina dal menu di scelta rapida dei file in AEM Guides Web Editor per utenti o gruppi specifici. Per altre personalizzazioni sulle opzioni del menu di scelta rapida dei file, controlla il framework dell’estensione delle guide. Ulteriori dettagli sono disponibili [qui](https://github.com/adobe/guides-extension/tree/main).

Come puoi vedere dallo snippet qui sotto, il menu di scelta rapida del file presenta l’opzione Elimina disponibile per questo utente specifico.

![Menu di scelta rapida file con eliminazione](../../../assets/authoring/file-contextmenu-Delete.png)

Ora vediamo come nascondere l’opzione &quot;Elimina&quot; per questo utente.

## Passaggi di implementazione:

- Passa a Strumenti > Sicurezza > Autorizzazioni dalla pagina Home di AEM.
- Scegliere il gruppo o l&#39;utente dalla casella di ricerca.
- Fai clic su &quot;Aggiungi ACE&quot; dall’angolo in alto a destra.
- Scegli il percorso della cartella.
- Includi i privilegi &quot;jcr:removeChildNodes&quot; e &quot;jcr:removeNode&quot;.
- Scegli &quot;Tipo di autorizzazione&quot; come &quot;Nega&quot; e fai clic su &quot;Aggiungi&quot; come mostrato di seguito.

![Autorizzazione utente negata ACE](../../../assets/authoring/permission-ACE-Delete.png)

![Elenco di controllo degli accessi nelle autorizzazioni](../../../assets/authoring/delete-acl.png)

### Test

- Accedi all’AEM come utente per il quale sono stati aggiunti gli ACE.
- Apri l’editor web.
- Passare alla visualizzazione del repository e scegliere la cartella per la quale sono stati aggiunti gli ACE.
- Aprire il menu di scelta rapida dei file.
- L&#39;opzione &#39;Elimina&#39; non verrà visualizzata nel menu di scelta rapida.

Il menu di scelta rapida del file sarà ora simile al seguente:

![Menu di scelta rapida file senza eliminazione](../../../assets/authoring/file-contextmenu-Delete-removed.png)

```
Please note that these steps would also remove 'move' and 'rename' options from the Web Editor as they are also tied to delete process at the backend.
```
