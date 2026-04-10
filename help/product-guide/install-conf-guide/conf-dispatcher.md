---
title: Configurare Dispatcher
description: Scopri come configurare Dispatcher
feature: Installation
role: Admin
level: Experienced
source-git-commit: 834959a6a0e22cd5d2b2c5d0e57ceb6d45c0c666
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 7%

---

# Configurare Dispatcher {#id213BCM0M05U}

Se prevedi di utilizzare un’istanza Dispatcher su AEM Author insieme ad AEM Guides, per completare la configurazione devi eseguire le seguenti configurazioni aggiuntive:

>[!NOTE]
>
> Dispatcher è lo strumento di caching e/o bilanciamento del carico di Adobe Experience Manager. Per ulteriori dettagli sull&#39;utilizzo di Dispatcher, vedere [Panoramica di Dispatcher](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/dispatcher.html?lang=it).

## Abilitare AllowEncodedSlashes negli URL

Gli URL con barre codificate non sono abilitati per impostazione predefinita nella configurazione di AEM Dispatcher, ma è necessario abilitarli mentre si lavora in AEM Guides. A tale scopo, è necessario impostare il parametro `AllowEncodedSlashes` su **On** nella configurazione di Apache, come illustrato nel seguente snippet:

```XML
<VirtualHost *:80>
                ServerName www.geometrixx-outdoors.com
                **AllowEncodedSlashes On**
                <Directory />
                <IfModule disp_apache2.c>
                SetHandler dispatcher-handler
                </IfModule>
                Options FollowSymLinks
                AllowOverride None
                </Directory>
                </VirtualHost>
            
```

## Configurare il file mime.types per DITA

Quando si utilizza un Dispatcher con AEM Guides, è necessario assicurarsi che i file di mappa e argomenti DITA vengano riprodotti come HTML affinché gli autori possano visualizzare il contenuto come previsto \(anziché in formato testo non elaborato\).

Per aggiornare il file `mime.types`, effettuare le seguenti operazioni:

1. Connettersi al server Dispatcher utilizzando SSH e individuare il file `httpd.conf`.

1. Controllare il percorso del file `mime.types`.

1. Aprire il file `mime.types` e cercare &quot;text/html&quot;. La mappatura predefinita per &quot; text/html&quot; è:

   `text/html html htm`

1. Aggiorna la mappatura aggiungendo estensioni ditamap e dita come:

   `text/html html htm ditamap dita`

1. Salva e chiudi il file.


Questo aggiornamento della configurazione assicura che i file mappa DITA e i file degli argomenti sottoposti a rendering da Dispatcher vengano visualizzati come HTML nell’interfaccia utente di Assets.

## Consenti URL richiesta preferenze utente

Quando utilizzi un Dispatcher con AEM Guides, se l’istanza Autore ha in primo piano un dispatcher, apporta le due modifiche seguenti:

- Inserisci nella whitelist l’URL della richiesta POST. Di seguito è riportata una regola `/filters` di esempio: Aggiungi questa regola al file di configurazioni del dispatcher:

```json
/xxxx {/type "allow" /method "POST" /url "/home/users/*/preferences"}
```

- Verificare che il pattern URL `/libs/cq/security/userinfo.json` non sia memorizzato nella cache in Author Dispatcher, quindi aggiungere una regola `\(like below\)` in `author\_dispatcher.any`

```json
/xxxx {
                /glob "/libs/cq/security/userinfo.json"
                /type "deny"
                }
```

