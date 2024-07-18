---
title: Menu di scelta rapida
description: Personalizzazione dei menu di scelta rapida
role: User, Admin
exl-id: 25aa76dd-ef05-41ed-b980-14bbc1626059
source-git-commit: 492f72768e0de74a91eb7acc9db8264e21bfc810
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 0%

---

# Personalizzazione dei menu di scelta rapida

È possibile personalizzare i seguenti menu di scelta rapida:

- `file_options`
controller:
   - Visualizzazione mappa: `ditamap_viewer_controller`
   - Pannello archivio: `repository_panel_controller`
   - Pannello Preferiti: `collection_tree_controller`
   - Collegamenti di riferimento proprietà file: `file_references_links_controller`
   - Pannello di ricerca archivio: `repository_search_controller`
   - Pannello schema soggetto: `subject_scheme_tree_controller`

- `folder_options`
controller:
   - Pannello archivio: `repository_panel_controller`
   - Pannello Preferiti: `collection_tree_controller`

- `collection_options`
controller:
   - Pannello Preferiti: `collection_tree_controller`

- `map_view_options`
controller:
   - Visualizzazione mappa: `ditamap_viewer_controller`

- `baseline_panel_menu`
controller:
   - Pannello linea di base: `baseline_panel`

- `preset_item_menu`
controller:
   - Pannello predefiniti: `preset_panel`

Puoi anche creare un menu di scelta rapida personalizzato definendo un nuovo ID univoco.

Ora a ogni menu di scelta rapida è associato un `controller id`. Questo controller gestisce la funzionalità `on-event` per le varie opzioni del menu di scelta rapida

Prendiamo un esempio per capire

```js title=customise_context_menu.js"
const loadDitaFile = (filePath, uuid) =>{
  return $.ajax({
    type: 'POST',
    url: '/bin/referencelistener',
    data: {
        operation: 'getdita',
        path: filePath,
        type: uuid ? 'UUID' : 'PATH',
        cache: false,
    },
  })
}

const fileOptions = {
    id: "file_options",
    contextMenuWidget: "repository_panel",
    view: {
            items: [
                {
                    component: "div",
                    target: {
                        key:"displayName",value: "Delete",                    
                        viewState: VIEW_STATE.REPLACE
                    }
                },
                {
                    component: "div",
                    target: {
                        key:"displayName",value: "Edit",                    
                        viewState: VIEW_STATE.REPLACE
                    }
                },
                {
                    "displayName": "Download",
                    "data": {
                      "eventid": "downloadFile"
                    },
                    "icon": "downloadFromCloud",
                    "class": "menu-separator",         
                    target: {
                        key:"displayName",value: "Duplicate",                    
                        viewState: VIEW_STATE.REPLACE
                    }
                },
            ]

    },

    controller: {
        downloadFile(){
            const path  = this.getValue('selectedItems')[0].path
            loadDitaFile(path).then((file) => {
              function download_file(name, contents) {
                const mime_type = "text/plain";
        
                const blob = new Blob([contents], {type: mime_type});
        
                const dlink = document.createElement('a');
                dlink.download = name;
                dlink.href = window.URL.createObjectURL(blob);
                dlink.onclick = function() {
                    // revokeObjectURL needs a delay to work properly
                    const that = this;
                    setTimeout(function() {
                        window.URL.revokeObjectURL(that.href);
                    }, 1500);
                };
        
                dlink.click();
                dlink.remove();
            }
            download_file(path,file.xml)
            });
          }
    }
}
```

Ora cerchiamo di capire cosa sta facendo questo codice.

1. `id` viene utilizzato per identificare il menu di scelta rapida che si desidera personalizzare.
2. `contextMenuWidget` viene utilizzato per definire `widget id` o `component`, che chiama il menu di scelta rapida e gestisce `events`.

Il resto rimane invariato, dove `view` viene utilizzato per definire gli elementi, `target` identifica dove sostituire, aggiungere o anteporre l&#39;opzione e il controller `contextMenuWidget` gestisce gli eventi `on-click`.
