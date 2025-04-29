---
title: Usa specializzazione DITA-OT e DITA personalizzata
description: Scopri come utilizzare la specializzazione DITA-OT e DITA personalizzata
exl-id: 4d3e0fc1-b684-44f9-ab0d-411033024019
feature: DITA-OT Configuration
role: Admin
level: Experienced
source-git-commit: 3119ef32a753afac9405af31a241ae508f922ea7
workflow-type: tm+mt
source-wordcount: '1701'
ht-degree: 0%

---

# Usa specializzazione DITA-OT e DITA personalizzata {#id181GAJ0005Z}

DITA Open Toolkit \(DITA-OT\) è un insieme di strumenti open source basati su Java che forniscono l&#39;elaborazione per le mappe DITA e il contenuto dell&#39;argomento. AEM Guides consente di importare e utilizzare facilmente plug-in DITA-OT personalizzati. Una volta importato, AEM Guides può essere configurato per utilizzare il plug-in DITA-OT personalizzato per generare output in qualsiasi formato. Al momento della generazione dell&#39;output, è sufficiente selezionare l&#39;opzione DITA-OT e AEM Guides utilizza il plug-in DITA-OT personalizzato per generare l&#39;output richiesto.

Se desideri elaborare i parametri della formica durante la pubblicazione di un output, AEM Guides ti offre un modo semplice per farlo. È possibile specificare quali parametri di formica si desidera utilizzare e gli stessi vengono quindi elaborati dal processo di pubblicazione.

>[!NOTE]
>
> AEM Guides viene fornito con la versione 3.3.2 di DITA-OT, ma supporta una serie di versioni da DITA-OT 1.7 a DITA-OT 4.x. Per un elenco completo delle versioni DITA-OT, vedere [Versioni DITA-OT](http://www.dita-ot.org/download).

>[!TIP]
>
> Consultare le sezioni *Configurazione dei profili DITA-OT* e *Utilizzo di DITA-OT* personalizzati nella guida alle best practice per le procedure consigliate sull&#39;utilizzo di plug-in DITA-OT personalizzati.

## Usa plug-in DITA-OT personalizzati {#id181NH1020L7}

È possibile utilizzare il plug-in DITA-OT personalizzato per la pubblicazione caricando il plug-in DITA-OT personalizzato nell&#39;archivio AEM. Per impostazione predefinita, AEM Guides viene fornito con un profilo preconfigurato che contiene le configurazioni dei modelli predefiniti da utilizzare per la modifica e la pubblicazione dei contenuti. È possibile creare profili personalizzati con modelli personalizzati da utilizzare durante la modifica di documenti e plug-in DITA-OT personalizzati per la pubblicazione di contenuti.

Il pacchetto DITA-OT predefinito disponibile con AEM Guides è dotato di processore Apache FOP XSL-FO, che non supporta il rendering delle equazioni MathML. Se utilizzi le equazioni di MathML nel contenuto, accertati di aver integrato un plug-in del motore di rendering MathML per Apache FOP o di utilizzare un processore XSL-FO diverso.

Per caricare un plug-in DITA-OT personalizzato nell&#39;archivio AEM, effettuare le seguenti operazioni:

1. Scarica il file DITA-OT.zip dal collegamento condiviso nell’e-mail di benvenuto.

1. Estrai il contenuto del file zip sul sistema.

1. Utilizzare un meccanismo di integrazione plug-in DITA-OT per integrare la nuova versione di DITA-OT con il plug-in DITA-OT personalizzato.

1. Creare nuovamente il file ZIP mantenendo lo stesso nome \(`DITA-OT.ZIP`\) e la struttura della cartella.

1. Carica nuovamente il file ZIP aggiornato nell’archivio AEM.

   Verifica quanto segue prima di caricare il file ZIP:

   - Eseguire l&#39;integratore \(per installare il plug-in personalizzato\) su un sistema operativo Mac/Linux per evitare problemi con i separatori di file. Poiché i sistemi operativi Windows e Linux dispongono di separatori di file diversi, il plug-in integrato nel sistema operativo Mac/Linux è compatibile sia con il programma di installazione di Windows che con quello di Linux.
   - Verificare che il file `DITA-OT.ZIP` contenga una cartella denominata &quot;DITA-OT&quot; contenente tutti i plug-in e i file rilevanti.
   - Verifica che il file `DITA-OT.ZIP` creato sia di tipo mime: &quot;nt:file&quot; \(questo corrisponde al tipo primario di file ZIP quando viene caricato in AEM\). Utilizza uno strumento WebDAV o un’implementazione di codice per caricare questo file ZIP nel percorso desiderato in AEM. \(Non utilizzare Gestione pacchetti di AEM per distribuire questo file ZIP poiché questo file ZIP non è un pacchetto di contenuti AEM, ma solo un file di archivio.\)

   >[!NOTE]
   >
   > Si consiglia di non sovrascrivere il pacchetto DITA-OT predefinito. È necessario caricare il pacchetto DITA-OT personalizzato contenente la cartella plug-in /var/dxml/dita\_resources/dita-ot. Puoi eseguire questa operazione anche utilizzando la pipeline di Cloud Manager. Per ulteriori dettagli, consulta [Distribuzione in AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html) nella documentazione di AEM.

1. Per creare un nuovo profilo, potete scegliere di modificare il profilo predefinito, crearne uno nuovo o duplicare le impostazioni del profilo predefinito.

   >[!NOTE]
   >
   > È possibile aggiornare il profilo predefinito, ma non eliminarlo. Tuttavia, tutti i nuovi profili creati possono essere modificati ed eliminati.

1. Configurare le seguenti proprietà per l&#39;utilizzo del plug-in DITA-OT personalizzato:

   | Nome proprietà | Descrizione |
   |-------------|-----------|
   | **Proprietà profilo** |
   | Nome profilo | Specifica un nome univoco per questo profilo. |
   | Riutilizza output | *\(Facoltativo\)* Se il profilo è basato su un profilo esistente, selezionare questa opzione. Selezionando questa opzione, AEM Guides non estrae nuovamente il contenuto del pacchetto DITA-OT e riutilizza il pacchetto DITA-OT esistente. |
   | Percorso di estrazione profilo | *\(Facoltativo\)* Specificare il percorso in cui viene conservato DITA-OT sul disco. Per impostazione predefinita, AEM Guides raggruppa un pacchetto DITA-OT nel proprio archivio e lo estrae sul disco in questo percorso. <br> **NOTA** È possibile definire questo percorso utilizzando qualsiasi variabile o proprietà di sistema esistente. Per ulteriori informazioni, vedere la descrizione della proprietà [Variabili di ambiente DITA-OT](#id181NH0YN0AX). |
   | Percorso assegnato | \(*Facoltativo*\) Specificare il percorso nell&#39;archivio dei contenuti a cui è applicabile il profilo. È possibile specificare più posizioni. |
   | **Proprietà DITA-OT** |
   | Timeout DITA-OT | \(*Facoltativo*\) Specificare il tempo \(in secondi\) per il quale AEM Guides attende una risposta dal plug-in DITA-OT. Se non viene ricevuta alcuna risposta entro il tempo specificato, AEM Guides interrompe l’attività di pubblicazione e l’attività viene contrassegnata come non riuscita. Inoltre, i registri degli errori sono resi disponibili nel file di registro di generazione dell’output. <br> Valore predefinito: 300 secondi \(5 minuti\) |
   | Argomenti PDF DITA-OT | Specificare gli argomenti della riga di comando elaborati dal plug-in DITA-OT personalizzato per la generazione dell&#39;output di PDF. Per tutti i profili DITA-OT personalizzati, specificare il seguente argomento della riga di comando:`-lib plugins/org.dita.pdf2.fop/lib/` |
   | Argomenti AEM DITA-OT | \(*Facoltativo*\) Specificare gli argomenti della riga di comando personalizzati elaborati dal plug-in DITA-OT personalizzato per la generazione dell&#39;output del sito AEM. |
   | Percorsi libreria DITA-OT | \(*Facoltativo*\) Specificare i percorsi di libreria aggiuntivi del plug-in DITA-OT. |
   | XML build DITA-OT | \(*Facoltativo*\) Specificare il percorso dello script di compilazione Ant personalizzato fornito con il plug-in DITA-OT personalizzato. Questo percorso è relativo alla directory DITA-OT del file system. |
   | Cartella script ant DITA-OT | \(Facoltativo\) Specificare il percorso della cartella degli script di annotazione DITA-OT. Questo percorso è relativo alla directory DITA-OT del file system. |
   | Variabili di ambiente DITA-OT | *\(Facoltativo\)* Specificare le variabili di ambiente da passare al processo DITA-OT. Per impostazione predefinita, AEM Guides aggiunge quattro variabili: `ANT_OPTS`, `ANT_HOME`, `PATH` e `CLASSPATH`. <br> È possibile riutilizzare una qualsiasi delle variabili di ambiente di sistema o delle proprietà esistenti per la creazione di nuove variabili di ambiente. Ad esempio, se nel sistema sono definite `JAVA_HOME` variabili di sistema e si desidera definire una nuova variabile di ambiente denominata `JAVA_BIN` che viene generata utilizzando `JAVA_HOME`. È quindi possibile aggiungere la definizione di `JAVA_BIN` come:`JAVA_BIN= ${JAVA_HOME}/bin` <br> **Nota:** è inoltre possibile utilizzare le proprietà del sistema Java per generare le variabili di ambiente. Se ad esempio lo script di avvio di AEM definisce una proprietà di sistema Java `java.io.tmpdir` in una directory temporanea, è possibile utilizzare questa proprietà per definire una nuova variabile come: `${java.io.tmpdir}/fmdita/dita_ot`. <br> **Importante:** Per riutilizzare una variabile o una proprietà di sistema esistente, è necessario racchiuderla in `${}`. |
   | Sovrascrivi output DITA-OT | Scegliere se l&#39;output DITA-OT deve essere sovrascritto. Mantieni selezionata questa opzione. |
   | Percorso ZIP AEM DITA-OT | Specifica il percorso completo in cui il file DITA-OT.zip personalizzato viene memorizzato nell&#39;archivio AEM. |
   | Percorso plug-in DITA-OT | Percorso del plug-in personalizzato. Questo plug-in viene integrato automaticamente con il pacchetto principale DITA-OT. |
   | Integrare cataloghi | \(*Facoltativo*\) Percorso dei file DTD e XSD catalog.xml personalizzati nell&#39;archivio AEM. Questa opzione deve essere fornita solo quando i cataloghi non sono presenti nel pacchetto DITA-OT. Questi cataloghi vengono integrati automaticamente con il DITA-OT principale come plug-in. |
   | Aggiungi catalogo ID sistema | \(*Facoltativo*\) Selezionare questa opzione solo se mancano voci di ID pubblico nel catalogo o se i file DITA utilizzano solo gli ID di sistema relativi al percorso del server da cui vengono caricati. |
   | Percorso temporaneo DITA-OT | Percorso temporaneo in cui i file DITA vengono copiati per l&#39;elaborazione. Prima che DITA-OT elabori i file, questi vengono copiati in questa posizione temporanea. Per impostazione predefinita, il percorso di archiviazione temporanea è: <br> `<*AEM-Install*>/crx-quickstart/profiles/ditamaps` <br> **Importante:** Non modificare il percorso predefinito. |

   >[!NOTE]
   >
   > Il programma di installazione di AEM Guides crea due variabili di ambiente che è possibile utilizzare per specificare il percorso dei file plug-in DITA-OT personalizzati. Queste variabili di ambiente sono: `DITAOT\_DIR`, che contiene il percorso della directory DITA-OT nel file system, e `DITAMAP\_DIR`, che contiene il percorso in cui il contenuto della mappa DITA viene estratto nel file system.

1. Fai clic su **Fine** per salvare il profilo.


## Integrare la specializzazione DITA {#id211MB0E00XA}

La specializzazione DITA è il processo di creazione di nuove strutture DITA mediante l&#39;aggiunta di nuovi elementi o la rimozione di elementi esistenti. Per creare un nuovo elemento DITA, è possibile utilizzare come base un elemento DITA esistente e modificarlo in base alle proprie esigenze di creazione. In sostanza, la specializzazione DITA consente di creare modelli di informazioni personalizzati in grado di soddisfare le esigenze aziendali mantenendo i vantaggi dell&#39;architettura DITA esistente.

È possibile utilizzare la funzione Profilo per memorizzare le impostazioni di specializzazione DITA personalizzate. Queste impostazioni possono quindi essere utilizzate al momento dell&#39;authoring e della pubblicazione di contenuti DITA personalizzati. AEM Guides consente di utilizzare l&#39;ID pubblico e l&#39;ID sistema nelle DTD/XSD personalizzate.

>[!NOTE]
>
> AEM Guides Web Editor non supporta XSD.

Per creare un nuovo profilo e configurarlo per l’utilizzo di DTD e XSD specializzati nell’AEM Guides, effettua le seguenti operazioni:

1. Creare nel computer locale una cartella di specializzazione contenente le DTD e le XSD specializzate.

1. Specificare i dettagli DTD nel file `catalog.xml` che devono essere inclusi anche nella cartella di specializzazione.

   >[!NOTE]
   >
   > Nel caso di DITA 1.3, la posizione predefinita per il file DTD `catalog.xml` nell&#39;archivio AEM è: `/libs/fmdita/dita_resources/DITA-1.3/dtd/catalog.xml`.

1. Specificare i dettagli XSD nel file `catalog.xml` che devono essere inclusi anche nella cartella di specializzazione.

   >[!NOTE]
   >
   > Nel caso di DITA 1.3, la posizione predefinita del file catalog.xml XSD nell&#39;archivio AEM è: `/libs/fmdita/dita_resources/DITA-1.3/xsd/catalog.xml`.

1. Carica la cartella nel percorso seguente:

   `/var/dxml/dita_resources`

1. Fai clic sul collegamento Adobe Experience Manager in alto e scegli **Strumenti**.

1. Seleziona **Guide** dall&#39;elenco degli strumenti.

1. Fare clic sulla sezione **Profili DITA**.

1. Per creare un nuovo profilo, potete scegliere di modificare il profilo predefinito, crearne uno nuovo o duplicare le impostazioni del profilo predefinito.

   >[!NOTE]
   >
   > Non è possibile eliminare il profilo predefinito. Tuttavia, tutti i nuovi profili creati possono essere modificati ed eliminati.

1. Nelle impostazioni **Schema** \> **Catalogo**, specifica il percorso dei file `catalog.xml` DTD e XSD personalizzati nel tuo archivio AEM.

1. Selezionare l&#39;opzione **Aggiungi catalogo ID sistema**.

   >[!NOTE]
   >
   > Selezionare questa opzione solo se nel catalogo mancano voci di ID pubblico o se i file DITA utilizzano solo gli ID di sistema relativi al percorso del file locale da cui vengono caricati.

   Per ulteriori informazioni sulle altre proprietà della pagina Profili, vedere la tabella delle proprietà in [Passaggio 6](#id17A9F0D075Z) della sezione [Utilizzare plug-in DITA-OT personalizzati](#id181NH1020L7).

1. Fai clic su **Fine** per salvare il profilo.
