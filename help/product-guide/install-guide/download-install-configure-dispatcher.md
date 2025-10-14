---
title: Configurare Dispatcher
description: Scopri come configurare Dispatcher
exl-id: 525de1c3-5a79-4d65-89b4-ca05ae660c2c
feature: Installation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 3%

---

# Configurare Dispatcher {#id213BCM0M05U}

Se prevedi di utilizzare un’istanza Dispatcher su AEM Author insieme ad AEM Guides, per completare la configurazione devi eseguire le seguenti configurazioni aggiuntive:

>[!NOTE]
>
> Dispatcher è lo strumento di caching e/o bilanciamento del carico di Adobe Experience Manager. Per ulteriori dettagli sull&#39;utilizzo di Dispatcher, vedere [Panoramica di Dispatcher](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/dispatcher.html?lang=it).

## Abilitare AllowEncodedSlashes negli URL

Gli URL con barre codificate non sono abilitati per impostazione predefinita nella configurazione del dispatcher AEM, ma mentre lavori in AEM Guides devi abilitarli. A questo scopo, è necessario impostare il parametro AllowEncodedSlashes su On nella configurazione di Apache, come illustrato nel seguente snippet:

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

Quando si utilizza un Dispatcher con AEM Guides, è necessario assicurarsi che i file mappa e argomento DITA vengano sottoposti a rendering come HTML per consentire agli autori di visualizzare il contenuto come previsto \(anziché in formato testo non elaborato\).

Per aggiornare il file mime.types, effettua le seguenti operazioni:

1. Connettiti al server Dispatcher utilizzando SSH e individua il file httpd.conf.

1. Controlla il percorso del file &quot;mime.types&quot;.

1. Apri il file mime.types e cerca &quot; text/html&quot;. La mappatura predefinita per &quot; text/html&quot; è:

   `text/html html htm`

1. Aggiorna la mappatura aggiungendo estensioni ditamap e dita come:

   `text/html html htm ditamap dita`

1. Salva e chiudi il file.


Questo aggiornamento della configurazione assicura che i file mappa DITA e i file degli argomenti sottoposti a rendering da Dispatcher vengano visualizzati come HTML nell’interfaccia utente di Assets.

## Consenti URL richiesta preferenze utente

Quando utilizzi un Dispatcher con AEM Guides, se l’istanza Autore ha in primo piano un dispatcher, apporta le due modifiche seguenti:

- Inserisci nella whitelist l’URL della richiesta POST. Di seguito è riportata una regola di esempio &quot; `/filters`&quot;. Aggiungere questa regola al file di configurazioni del dispatcher:

```json
/xxxx {/type "allow" /method "POST" /url "/home/users/*/preferences"}
```

- Assicurati che il pattern URL &quot; /libs/cq/security/userinfo.json&quot; non sia memorizzato nella cache in Author Dispatcher, quindi aggiungi una regola \(simile a quella riportata di seguito\) in Author\_dispatcher.any

```json
/xxxx {
                /glob "/libs/cq/security/userinfo.json"
                /type "deny"
                }
```

**Argomento padre:**&#x200B;[&#x200B; Scarica e installa](download-install.md)
