---
title: Pubblicazione tramite FrameMaker Publishing Server (FMPS) in AEM Guides
description: Pubblicazione con FMPS tramite AEM Guides
exl-id: 05d4d876-f83b-473c-bf31-14d6565e80e2
feature: AEM Guides FrameMaker Publishing Server
author: Pulkit Nagpal(punagpal)
role: User, Admin
TQID: https://experienceleague.adobe.com/-qkx3TRKOd-kPx1tFrguuWvBY4hIIyqLdCfKDQzR5jg
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: d5ea0417-7932-4688-a3e2-4d3b2e7076a3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 757
ht-degree: 0%

---

# Pubblicazione tramite FrameMaker Publishing Server (FMPS) in AEM Guides

L’integrazione di AEM Guides con FrameMaker Publishing Server potrebbe essere la soluzione ideale per chi cerca una pubblicazione automatizzata di alta qualità.\
Article consente di configurare ed eseguire FMPS con AEM Guides.

## Compatibilità di FMPS con AEM Guides

- Compatibilità con AEM Guides 4.1: [matrice di compatibilità 4.1](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/release-info/release-notes/on-prem-release-notes/release-notes-4.1.html?lang=en/#compatibility-matrix)
- Compatibilità con AEM Guides 4.0: [matrice di compatibilità 4.0](https://helpx.adobe.com/xml-documentation-for-experience-manager/release-note/release-notes-xml-documentation-solution-4-0.html/#Compatibility%20matrix)
- Ultima versione: [Informazioni sulla versione più recente](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/release-info/latest-release-info.html?lang=en)

## Installazione

Fai riferimento a quanto segue per l’installazione e la configurazione di AEM Guides e FMPS

### AEM Guides

L&#39;installazione e la configurazione fanno riferimento a: [4.1 installazione e configurazioni](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-1-2/Adobe-Experience-Manager-Guides_Installation-Configuration-Guide_EN.pdf)

### FMPS

Per l&#39;installazione di FMPS è possibile fare riferimento a [YouTube link](https://www.youtube.com/watch?v=2deelyM5VA8&t) o [FMPS installazione e configurazione](https://help.adobe.com/en_US/framemaker/server/index.html#t=fmps-user-guide%2Finstall_config_fmps.html%23install_config_fmps&rhtocid=_2)

## Configurazioni richieste

È possibile utilizzare FrameMaker Publishing Server (FMPS) per generare il contenuto DITA. FMPS supporta un&#39;ampia gamma di formati di output. Modifica le seguenti proprietà del bundle &quot;com.adobe.fmdita.config.ConfigManager&quot; nella console Web per configurare AEM Guides per l’utilizzo di FMPS.

Per aprire la console Web, passare all&#39;URL Accesso http://\&lt;nome server\>:\&lt;porta\>/system/console/configMgr.

**Proprietà di configurazione e relativa descrizione** [4.1 installazione e configurazione](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-1-2/Adobe-Experience-Manager-Guides_Installation-Configuration-Guide_EN.pdf#page=89)

## Test in esecuzione:

Utilizzando FMPS, puoi pubblicare automaticamente **PDF, Responsive HTML5** e **Epub** per il tuo Assets DITA e FM.

Dal menu &quot;Generate PDF using&quot; (Genera utilizzando), scegliere FrameMaker Publishing Server.

L’utente può fornire &quot;settings File(.sts)&quot; e &quot;ditaval&quot;. Il filtro viene eseguito utilizzando ditaval in base alle condizioni specificate.

- **File impostazioni**: file di impostazioni di pubblicazione di FrameMaker /FMPS contenente tutte le impostazioni che si desidera vengano rispettate da FMPS durante la pubblicazione. Ad esempio, la creazione di output con un modello personalizzato, la creazione di indicatori e pagine al vivo (PDF) e la creazione di PDF con sommario.
- **Predefinito FMPS:** Combinazione predefinita di file ditaval e impostazioni. Invece di fornire file ditaval e impostazioni separati, l’utente può pre-creare un predefinito FMPS che può essere riutilizzato per le esigenze di pubblicazione.

**Nota:** l&#39;impostazione di sistema predefinita viene utilizzata da FMPS per la pubblicazione se non si sceglie alcuna impostazione o il predefinito FMPS.

Si tratta di un conflitto se si sceglie il predefinito FMPS e si forniscono anche impostazioni personalizzate o un file ditaval da AEM. In questo caso, il predefinito FMPS ha la precedenza sulle impostazioni personalizzate o sul file ditaval.

### Pubblicazione della linea di base tramite FMPS:

È possibile pubblicare le linee di base già create con FMPS2020.0.2 o versione successiva.

**File di impostazioni FMPS di esempio (file con estensione sts) per iniziare:** [File di impostazioni FMPS di esempio](https://acrobat.adobe.com/link/track?uri=urn:aaid:scds:US:ef750752-7a7e-4e51-923e-6b7d9861ed54) (decomprimi il file)

## Domande frequenti e risoluzione dei problemi:

### La pubblicazione di FMPS non riesce con &quot;Eccezione di timeout&quot;

>Controlla e aumenta il valore di &quot;Timeout FMPS&quot; (secondi) in /system/console/configMgr/com.adobe.fmdita.config.ConfigManager&quot;

### Impossibile ottenere il predefinito FMPS nel menu a discesa

>Verificare che sul server sia stato creato un predefinito FMPS predefinito e che le impostazioni di connessione siano corrette.

### Ricevo PDF vuoti durante la pubblicazione

>Se utilizzi UUID, assicurati di aver selezionato &quot;Usa riferimenti basati su UUID&quot; in Preferenze di modifica di FrameMaker e viceversa per le guide di AEM non-UUID.

### Le mie impostazioni/ditaval non vengono applicate nell&#39;output pubblicato finale

>Verificate che non si stia scegliendo contemporaneamente il predefinito FMPS e il file di impostazione/diaval. Utilizza FrameMaker per controllare manualmente l’output.

### La baseline non viene pubblicata da FMPS

>FMPS2020.0.2 o versioni successive sono compatibili con la pubblicazione di base.
>Verificare che la baseline sia stata creata correttamente. Per verificare, passare a Map Dashboard— Topics— Download Map e scegliere &quot;Use Baseline&quot;.

### Le attività di pubblicazione da FMPS richiedono più tempo rispetto ad altri motori

>Durante la pubblicazione da FMPS, il tempo di intestazione fisso ideale è di circa 3-4 minuti; se ritieni che sia più lungo, contatta l’amministratore FMPS o contatta il supporto Adobe.

## Altre risorse:

[Formazione e supporto per FMPS](https://helpx.adobe.com/support/framemaker-publishing-server.html)

[Informazioni e supporto per AEM Guides](https://helpx.adobe.com/in/support/xml-documentation-for-experience-manager.html)

[Community FrameMaker e FMPS](https://community.adobe.com/t5/framemaker/ct-p/ct-framemaker?page=1&sort=latest_replies&lang=all&tabid=all)

[Community AEM Guides](https://experienceleaguecommunities.adobe.com/t5/experience-manager-guides/ct-p/aem-xml-documentation)
