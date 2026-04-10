---
title: Configurare nomi di file automatici basati su UUID
description: Scopri come configurare i nomi di file automatici in base all’UUID
feature: Filename Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 1%

---

# Configurare nomi di file automatici basati su UUID {#id205QG070D5Z}

Per impostazione predefinita, quando viene creato un file argomento o mappa, agli autori viene data un&#39;opzione per specificare anche il nome del file. Gli autori possono assegnare i nomi dei file in base alle proprie esigenze. Tuttavia, questo può causare incoerenza e un’ampia gamma di nomi di file può essere vista in un ampio sistema di documentazione. In qualità di amministratore, puoi impedire agli autori di assegnare nomi di file per i file creati nel sistema. Per ogni nuovo argomento o file mappa, puoi scegliere di assegnare automaticamente nomi di file basati su UUID.

Le schede seguenti forniscono istruzioni per configurare i nomi di file automatici in base all’UUID in base alla configurazione di Experience Manager Guides: Cloud Service o On-Premise.


>[!BEGINTABS]

>[!TAB Cloud Service]

Utilizza le istruzioni fornite in [Sostituzioni configurazione](download-install-config-override.md#) per creare il file di configurazione. Nel file di configurazione, fornisci i seguenti dettagli \(property\) per configurare i nomi di file automatici in base all’UUID:

| PID | Chiave proprietà | Valore proprietà |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.uniquefilenames` | Booleano \(true/false\).<br> **Valore predefinito**: false |

>[!NOTE]
>
> Quando questa opzione è attivata, gli autori non visualizzeranno l&#39;opzione per specificare il nome del file durante la creazione di un nuovo argomento o di un nuovo file di mappa. È possibile creare un nuovo argomento o un nuovo file di mappa dall’interfaccia utente di Assets e dall’editor web.

>[!TAB On-Premise]

Per assegnare automaticamente il nome di file basato su UUID per tutti i nuovi file creati nel sistema, effettua le seguenti operazioni:

1. Aprire la pagina Configurazione della console Web Adobe Experience Manager.

   L&#39;URL predefinito per accedere alla pagina di configurazione è:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Cerca e fai clic sul bundle *com.adobe.fmdita.xmleditor.config.XmlEditorConfig*.

1. Selezionare l&#39;opzione **Usa nomi file di sistema basati su UUID**.

1. Fai clic su **Salva**.


>[!NOTE]
>
> Per impostazione predefinita, questa opzione è disattivata. Quando questa opzione è attivata, gli autori non visualizzeranno l&#39;opzione per specificare il nome del file durante la creazione di un nuovo argomento o di un nuovo file di mappa. È possibile creare un nuovo argomento o un nuovo file di mappa dall’interfaccia utente di Assets e dall’editor web.

>[!ENDTABS]

