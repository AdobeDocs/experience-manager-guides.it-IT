---
title: Tradurre il contenuto
description: Scopri come tradurre i contenuti
exl-id: 5af78233-343e-47ba-b60c-b7f4789e2406
feature: Translation
role: Admin
level: Experienced
source-git-commit: ea3083542e955a56c27cd833600370a7962c6b8d
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 9%

---

# Tradurre il contenuto {#id181GB0400UI}

Automatizza la traduzione di contenuti di pagina, risorse e contenuti generati dall&#39;utente per creare e gestire siti web multilingue. Per automatizzare i flussi di lavoro di traduzione, puoi integrare fornitori di servizi di traduzione con AEM e creare progetti per la traduzione dei contenuti in più lingue. AEM supporta flussi di lavoro di traduzione umana e automatica.

- Traduzione umana: il contenuto viene inviato al tuo provider di traduzioni e tradotto da traduttori professionisti. Una volta completato, il contenuto tradotto viene rinviato e importato in AEM. Quando il fornitore di traduzione è integrato con l&#39;AEM, i contenuti vengono scambiati automaticamente tra l&#39;AEM e il fornitore di traduzione

- Traduzione automatica: il servizio di traduzione automatica traduce immediatamente il contenuto


La traduzione del contenuto prevede i seguenti passaggi:

1. Connetti AEM con il tuo [fornitore di servizi di traduzione](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/integration-framework.html?lang=en) e crea configurazioni del Translation Integration Framework.

1. Associa le pagine della lingua master con il servizio di traduzione e le configurazioni del framework.

1. Identificare il tipo di [contenuto da tradurre](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/rules.html?lang=en).

1. [Prepara il contenuto per la traduzione](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/preparation.html?lang=en) creando la lingua master e le pagine root delle copie in lingua.

1. Crea [progetti di traduzione](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/managing-projects.html?lang=en) per raccogliere il contenuto da tradurre e preparare il processo di traduzione.

1. Utilizza i progetti di traduzione per [gestire il processo di traduzione del contenuto](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/managing-projects.html?lang=en).


Se il fornitore di servizi di traduzione non fornisce un connettore per l’integrazione con l’AEM, l’AEM supporta l’esportazione e l’importazione manuale dei contenuti tradotti in formato XML.

>[!TIP]
>
> Consulta la sezione *Traduzione* nella guida alle best practice per le best practice sulla traduzione dei contenuti.

## Configurare la scheda Traduzione nel dashboard delle mappe DITA

Per nascondere la scheda Traduzione nel dashboard delle mappe DITA, effettuare le seguenti operazioni:

1. Utilizza le istruzioni fornite in [Sostituzioni configurazione](download-install-additional-config-override.md#) per creare il file di configurazione.
1. Nel file di configurazione, fornisci i seguenti dettagli \(property\) per configurare la scheda di traduzione nel dashboard delle mappe:

   | PID | Chiave proprietà | Valore proprietà |
   |---|------------|--------------|
   | `com.adobe.fmdita.config.ConfigManager` | `tabs.translation` | Booleano \( true/ false\).<br> **Valore predefinito**: `true` |

   >[!NOTE]
   >
   > Questa configurazione è abilitata per impostazione predefinita e la scheda traduzione non è disponibile nel dashboard delle mappe.


## Configurare il flusso di lavoro di traduzione basato su componenti

Se il connettore per il fornitore di traduzione non supporta il contenuto DITA, è necessario abilitare il flusso di lavoro di traduzione basato su componenti. Una volta abilitato, il contenuto traducibile viene inviato come metadati della risorsa. Tuttavia, affinché questo flusso di lavoro funzioni, il connettore deve supportare la traduzione dei metadati delle risorse.

In base al flusso di lavoro di traduzione utilizzato nella configurazione, deve essere configurata l’opzione del flusso di lavoro di traduzione basato su componenti. Utilizza le istruzioni fornite in [Sostituzioni configurazione](download-install-additional-config-override.md#) per creare il file di configurazione. Nel file di configurazione, fornisci i seguenti dettagli \(property\) per configurare il flusso di lavoro di traduzione basato su componenti:

| PID | Chiave proprietà | Valore proprietà |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `component.translation` | Booleano: <br> -   Se utilizzi una traduzione umana, *Disabilita* \( `false`\) l&#39;opzione **Flusso di lavoro di traduzione basato su componenti**. <br> -   Se utilizzi la traduzione automatica, *Abilita \( `true`\)* l&#39;opzione **Flusso di lavoro di traduzione basato su componenti**. |



## Configurare il flusso di lavoro di traduzione legacy

>[!IMPORTANT]
>
> È consigliabile utilizzare l’ultimo flusso di lavoro di traduzione, disponibile in AEM Guides 2024.06.0 e versioni successive, per migliorare le prestazioni. Tuttavia, se hai abilitato una personalizzazione nel processo di traduzione e questo è influenzato dal nuovo flusso di lavoro, puoi considerare il ripristino del flusso di lavoro di traduzione legacy come soluzione alternativa.

Utilizza le istruzioni fornite in [Sostituzioni configurazione](download-install-additional-config-override.md#) per creare il file di configurazione. Nel file di configurazione, fornisci i seguenti dettagli (proprietà) per configurare il flusso di lavoro di traduzione legacy:


| PID | Chiave proprietà | Valore proprietà |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `translation.workflow.version.legacy` | Booleano: <br> - Se utilizzi il flusso di lavoro di traduzione più recente, *Disabilita* \( `false`\) l&#39;opzione **Esegui flusso di lavoro di traduzione legacy**.  <br> -   Se utilizzi la traduzione legacy, *Abilita \( `true`\)* l&#39;opzione **Esegui flusso di lavoro di traduzione legacy**. <br> **Valore predefinito**: false |




>[!NOTE]
>
> Se utilizzi il connettore di traduzione, accertati di averlo configurato come descritto nell&#39;argomento *[Configurazione del framework di integrazione della traduzione](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/integration-framework.html?lang=en)* nella documentazione di Adobe Experience Manager.

>[!IMPORTANT]
>
> Dopo aver impostato le configurazioni di traduzione, accertati di impostare la configurazione cloud appropriata nelle cartelle delle lingue.

## Configurare la post-elaborazione di copie per lingua temporanee

Quando avvii il flusso di lavoro di traduzione, il sistema crea copie temporanee in lingua del contenuto sorgente. Puoi scegliere di abilitare o disabilitare l’operazione di post-elaborazione su questi file temporanei. Nell’operazione di post-elaborazione, i riferimenti in entrata e in uscita dai file vengono risolti, lo stato del documento viene impostato, insieme ad altre operazioni. Se abiliti la post-elaborazione in questi file temporanei, il completamento del processo di traduzione potrebbe richiedere più tempo. Pertanto, si consiglia di mantenere disabilitata l’opzione di post-elaborazione.

Utilizza le istruzioni fornite in [Sostituzioni configurazione](download-install-additional-config-override.md#) per creare il file di configurazione. Nel file di configurazione, fornisci i seguenti dettagli \(property\) per configurare la post-elaborazione delle copie per lingua temporanee:

| PID | Chiave proprietà | Valore proprietà |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `postprocess.temporary.langcopies` | Booleano: <br> -   Se non si desidera eseguire l&#39;operazione di post-elaborazione sui file temporanei, *Disabilita* \( false\) l&#39;opzione **Copie per lingua post-elaborazione**.<br> -   Se desideri eseguire l&#39;operazione di post-elaborazione sui file temporanei, *Abilita* \( true\) l&#39;opzione **Copie lingua post-elaborazione**.<br> **Valore predefinito**: false |

