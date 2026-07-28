---
title: Aggiornamenti API nelle versioni Experience Manager Guides
description: Scopri i vari aggiornamenti API nelle versioni di Experience Manager Guides
source-git-commit: 24637376024107ae575620e5491c0150da6cc956
workflow-type: tm+mt
source-wordcount: '500'
ht-degree: 2%

---


# Aggiornamenti API nelle versioni Experience Manager Guides

Questo articolo fornisce dettagli sulle nuove API aggiunte nella documentazione Swagger per le versioni di Adobe Experience Manager Guides. Puoi accedere alla documentazione di Swagger tramite l&#39;interfaccia di AEM passando a **Strumenti** > **Guide** > **Swagger API**.

<table style="border: 1; border-collapse: collapse; table-layout:fixed">
    <tr>
        <td colspan="5"><strong>Versione 2026.08.0</strong></td>
    </tr>
    <tr>
        <td>Funzione</td>
        <td>Sub-funzione</td>
        <td>Metodo</td>
        <td>API</td>
        <td>Descrizione</td>
    </tr>
    <tr>
        <td rowspan="7"><b>Risorse</b></td>
        <td rowspan="7"></td>
        <td>POST</td>
        <td>"/bin/guides/v1/asset/import"</td>
        <td>Importa una o più risorse in una cartella di destinazione; supporta il caricamento multipart e la risoluzione dei conflitti</td>
    </tr>
    <tr>
        <td>POST</td>
        <td>"/bin/guides/v1/asset/list"</td>
        <td>Restituisce un elenco impaginato di risorse in un percorso di cartella</td>
    </tr>
    <tr>
        <td>POST</td>
        <td>`/bin/guides/v1/asset/validatexml`</td>
        <td>Convalida l'XML DITA per la correttezza della formattazione, la validità dello schema e l'integrità della conversione</td>
    </tr>
    <tr>
        <td>POST</td>
        <td>"/bin/guides/v1/asset/version/revert"</td>
        <td>Ripristina una versione specificata di una risorsa</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>"/bin/guides/v1/asset/currentversion/detail"</td>
        <td>Restituisce i dettagli della versione corrente (nome versione, stato dirty, etichette, ecc.)</td>
    </tr>
    <tr>
        <td>POST</td>
        <td>"/bin/guides/v1/assets/status"</td>
        <td>Avvia il processo asincrono per verificare lo stato delle guide nei percorsi specificati</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>"/bin/guides/v1/assets/status"</td>
        <td>Recupera lo stato/i risultati di un processo di stato delle risorse per ID processo</td>
    </tr>
    <tr>
        <td rowspan="3"><b>Pubblicazione</b></td>
        <td rowspan="3"></td>
        <td>POST</td>
        <td>`/bin/guides/v1/output/generate`</td>
        <td>Avvia l'esecuzione del predefinito per generare l'output per una mappa</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>`/bin/guides/v1/output/status`</td>
        <td>Restituisce lo stato di una singola generazione di output in base al percorso mappa e all'ID generazione</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>`/bin/guides/v1/output/status/list`</td>
        <td>Restituisce lo stato di tutti i predefiniti generati per un percorso mappa</td>
    </tr>
    <tr>
        <td rowspan="18"><b>Traduzione</b></td>
        <td rowspan="6">Lingua</td>
        <td>GET</td>
        <td>"/bin/guides/v1/translation/language/copy"</td>
        <td>Copie per lingua di una risorsa per percorso o UUID</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>"/bin/guides/v1/translation/language/groups"</td>
        <td>Gruppi di lingue per un profilo di cartella</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>`/bin/guides/v1/translation/language/list`</td>
        <td>Supporta le lingue di traduzione (filtrate)</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>`/bin/guides/v1/translation/language/root`</td>
        <td>Lingue principali disponibili per un percorso risorsa</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>`/bin/guides/v1/translation/language/variable`</td>
        <td>Variabili di lingua per tipo e codici di lingua</td>
    </tr>
    <tr>
        <td>POST</td>
        <td>`/bin/guides/v1/translation/language/variable`</td>
        <td>Crea, aggiorna o elimina variabili di lingua</td>
    </tr>
    <tr>
        <td rowspan="7">Progetto</td>
        <td>POST</td>
        <td>`/bin/guides/v1/translation/project/create`</td>
        <td>Crea/aggiorna progetto di traduzione per una mappa DITA</td>
    </tr>
    <tr>
        <td>POST</td>
        <td>`/bin/guides/v1/translation/project/sync`</td>
        <td>Crea/aggiorna il progetto di traduzione (flusso di sincronizzazione)</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>"/bin/guides/v1/translation/project/creationstatus"</td>
        <td>Stato di sincronizzazione della traduzione per un progetto in base al percorso</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>"/bin/guides/v1/translation/project/existing"</td>
        <td>Progetti di traduzione esistenti per l’utente corrente</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>"/bin/guides/v1/translation/project/inprogress"</td>
        <td>Progetti in corso per una determinata risorsa</td>
    </tr>
    <tr>
        <td>ELIMINA</td>
        <td>"/bin/guides/v1/translation/project/delete"</td>
        <td>Aggiornamento pre-eliminazione degli stati/proprietà di traduzione delle risorse</td>
    </tr>
    <tr>
        <td>ELIMINA</td>
        <td>"/bin/guides/v1/translation/project/job/delete"</td>
        <td>Aggiornamento pre-eliminazione degli stati delle risorse prima della rimozione del processo</td>
    </tr>
    <tr>
        <td rowspan="5">Riferimento</td>
        <td>POST</td>
        <td>"/bin/guides/v1/translation/reference/accept"</td>
        <td>Accetta contenuti tradotti da pagine figlie processo</td>
    </tr>
    <tr>
        <td>POST</td>
        <td>"/bin/guides/v1/translation/reference/rejected"</td>
        <td>Rifiuta contenuto tradotto da pagine figlie processo</td>
    </tr>
    <tr>
        <td>POST</td>
        <td>`/bin/guides/v1/translation/reference/sync`</td>
        <td>Creare copie per lingua nelle cartelle di destinazione</td>
    </tr>
    <tr>
        <td>POST</td>
        <td>"/bin/guides/v1/translation/reference/baseline/export"</td>
        <td>Esporta la linea di base di traduzione nelle lingue di destinazione</td>
    </tr>
    <tr>
        <td>POST</td>
        <td>`/bin/guides/v1/translation/reference/status/forcesync`</td>
        <td>Forza aggiornamento delle risorse non sincronizzate in sincronia</td>
    </tr>
</table>
