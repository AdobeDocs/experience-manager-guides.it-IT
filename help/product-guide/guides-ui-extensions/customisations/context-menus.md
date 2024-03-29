---
title: Menu di scelta rapida
description: Personalizzazione dei menu di scelta rapida
role: User, Admin
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 0%

---


# Personalizzazione dei menu di scelta rapida

È possibile personalizzare i seguenti menu di scelta rapida:

- `file_options`
controller:
   - Vista mappa: `ditamap_viewer_controller`
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
   - Vista mappa: `ditamap_viewer_controller`

- `baseline_panel_menu`
controller:
   - Pannello linea di base: `baseline_panel`

- `preset_item_menu`
controller:
   - Pannello predefiniti: `preset_panel`

Puoi anche creare un menu di scelta rapida personalizzato definendo un nuovo ID univoco.

Ora ogni menu di scelta rapida ha un `controller id` ad esso associato. Questo controller gestisce `on-event` funzionalità per le varie opzioni del menu di scelta rapida

Prendiamo un esempio per capire

```js title=customise_context_menu.js"
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
            const path  = this.model.selectedItem.path
            this.loader.loadDitaFile(path).then((file) => {
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

1. `id` viene utilizzato per identificare il menu di scelta rapida da personalizzare.
2. `contextMenuWidget` viene utilizzato per definire `widget id` o `component` che chiama il menu di scelta rapida e gestisce `events`.

Il resto rimane lo stesso, per cui `view` viene utilizzato per definire gli elementi, `target` identifica dove sostituire, aggiungere o anteporre l&#39;opzione e `contextMenuWidget` il controller gestisce `on-click` eventi.
