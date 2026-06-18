---
title: Configurare il salvataggio automatico dei file nell’editor
description: Scopri come configurare il salvataggio automatico dei file nell’editor
exl-id: 23fe404c-c76d-43ba-9b28-c49ab1e524de
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/-VGsv3zHE6oACLVpnYm24-rX9-H6uUGyz3SEsP2ILBE
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: cc73b81787a3c3dbe8390d93e558064327e59965
workflow-type: tm+mt
source-wordcount: 197
ht-degree: 1%

---

# Configurare il salvataggio automatico dei file nell’editor {#id199CC0J0M5Z}

Una delle funzioni più comuni nell’editor basato su browser è la possibilità di salvare i dati dopo un periodo di tempo specifico. L&#39;editor di AEM Guides supporta anche il salvataggio automatico di file di argomenti e mappe nell&#39;intervallo di tempo specificato. Quando questa funzione viene attivata, viene salvata la copia di lavoro dell&#39;argomento o della mappa. Non è stata creata una nuova versione dell&#39;argomento o della mappa. Per creare una nuova versione, fai clic sull’icona Salva revisione nella barra degli strumenti dell’editor.

La funzione di salvataggio automatico non è attivata per impostazione predefinita ed è necessario attivarla da configMgr. Per abilitare la funzione di salvataggio automatico nell’editor, effettua le seguenti operazioni:

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e fai clic sul bundle **com.adobe.fmdita.xmleditor.config.XmlEditorConfig**.

1. Nelle impostazioni *XmlEditorConfig*, seleziona l&#39;opzione **Salvataggio automatico**.

1. Nel campo **Intervallo salvataggio automatico**, specificare l&#39;intervallo di tempo in secondi per attivare la funzione di salvataggio automatico.

1. Fai clic su **Salva**.


**Argomento padre:**&#x200B;[&#x200B; Personalizza editor](conf-web-editor.md)
