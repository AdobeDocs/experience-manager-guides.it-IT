---
title: Configurare un connettore di origine dati
description: Scopri come configurare un connettore di origine dati
exl-id: bd1188e1-0e1d-4e70-928a-10251c3d529d
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 0%

---

# Configurare un connettore di origine dati

Le guide AEM forniscono connettori predefiniti per database JIRA e SQL (MySQL, PostgreSQL, SQL Server, SQLite). È inoltre possibile aggiungere altri connettori estendendo le interfacce predefinite. La seguente configurazione consente di aggiungere facilmente le varie origini dati. Una volta aggiunte, è possibile visualizzare le origini dati nell’Editor web.

Per configurare un connettore di origine dati e utilizzarlo dall&#39;editor Web, eseguire la procedura seguente:

## Configurare un connettore

Puoi configurare un connettore preconfigurato caricando un file JSON. È possibile utilizzare i seguenti file di installazione di esempio per impostare i connettori per i database Jira e SQL (MySQL, PostgreSQL, SQL Server, SQLite).

Esempio di file di configurazione per l’autenticazione di base di Jira con nome utente e password:

```
{
	"connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.rest.JiraConnector",
	"configName": "Jira",
	"templateFolders": ["/content/dam/dita-templates/konnect/jira"],
	"connectionConfig": {
		"configClazz": "com.adobe.guides.konnect.definitions.ootb.config.rest.BasicAuthRestConfig",
		"configData": {
			"username": "jirausername",
			"password": "jirapassword",
			"url": "https://jira.corp.adobe.com/rest/api/latest/search"
		}
	}
}
```

Ad esempio, salva con nome `jira.json`.

Esempio di file di configurazione per l’autenticazione di base di Jira con token:

```
{
	"connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.rest.JiraConnector",
	"configName": "Jira",
	"templateFolders": ["/content/dam/dita-templates/konnect/jira"],
	"connectionConfig": {
		"configClazz": "com.adobe.guides.konnect.definitions.ootb.config.rest.BasicAuthRestConfig",
		"configData": {
			"token": "jiraauthtoken",
			"url": "https://jira.corp.adobe.com/rest/api/latest/search"
		}
	}
}
```

Ad esempio, salva con nome `jira.json`.

Un esempio di file di configurazione per l’autenticazione di base di Jira con il token contenente la parola chiave &quot;Basic&quot;:

```
{
	"connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.rest.JiraConnector",
	"configName": "Jira",
	"templateFolders": ["/content/dam/dita-templates/konnect/jira"],
	"connectionConfig": {
		"configClazz": "com.adobe.guides.konnect.definitions.ootb.config.rest.BasicAuthRestConfig",
		"configData": {
			"token": "Basic jiraauthtoken",
			"url": "https://jira.corp.adobe.com/rest/api/latest/search"
		}
	}
}
```

Ad esempio, salva con nome `jira.json`.

Esempio di file di installazione per l&#39;autenticazione di base di MySql:

```
{
	"connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.sql.MySqlConnector",
	"configName": "MySQL",
	"templateFolders": ["/content/dam/dita-templates/konnect/sql"],
	"connectionConfig": {
		"configClazz": "com.adobe.guides.konnect.definitions.ootb.config.sql.UserPassSqlConfig",
		"configData": {
			"username": "admin",
			"password": "admin",
			"driver": "com.mysql.jdbc.Driver",
			"connectionString": "jdbc:mysql://host.corp.adobe.com:3306/plm"
		}
	}
}
```

Ad esempio, salva con nome `mysql.json`.

Esempio di file di installazione per l&#39;autenticazione di base di PostgreSQL:

```
{
	"connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.sql.PostgreSqlConnector",
	"configName": "PostgreSQL",
	"templateFolders": ["/content/dam/dita-templates/konnect/sql"],
	"connectionConfig": {
		"configClazz": "com.adobe.guides.konnect.definitions.ootb.config.sql.UserPassSqlConfig",
		"configData": {
			"username": "admin",
			"password": "admin",
			"driver": "org.postgresql.Driver",
			"connectionString": "jdbc:postgresql://host:port/database"
		}
	}
}
```

Ad esempio, salva con nome `postgres.json`.

Esempio di file di installazione per l&#39;autenticazione di base di MS SQL Server:

```
{
	"connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.sql.MsSqlServerConnector",
	"configName": "MSSQLServer",
	"templateFolders": ["/content/dam/dita-templates/konnect/sql"],
	"connectionConfig": {
		"configClazz": "com.adobe.guides.konnect.definitions.ootb.config.sql.UserPassSqlConfig",
		"configData": {
			"username": "admin",
			"password": "admin",
			"driver": "com.microsoft.sqlserver.jdbc.SQLServerDriver",
			"connectionString": "jdbc:sqlserver://10.10.10.10\\SQLEXPRESS01:1433;database=TutorialDB;encrypt=false;trustServerCertificate=true"
		}
	}
}
```

Ad esempio, salva con nome `mssqlserver.json`.

Esempio di file di installazione per l&#39;autenticazione di base di SQLite:

```
{
	"connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.sql.SqliteConnector",
	"configName": "SQLiteServer",
	"templateFolders": ["/content/dam/dita-templates/konnect/sql"],
	"connectionConfig": {
		"configClazz": "com.adobe.guides.konnect.definitions.ootb.config.sql.UserPassSqlConfig",
		"configData": {
			"username": "admin",
			"password": "admin",
			"driver": "org.sqlite.JDBC",
			"connectionString": "jdbc:sqlite:sample.db"
		}
	}
}
```

Ad esempio, salva con nome `sqqlite.json`.

### Personalizzare una configurazione di connettore

Le guide AEM consentono di personalizzare alcuni valori nel file di configurazione in base alle esigenze dell&#39;utente.

| Nome proprietà | Descrizione |
|---|---|
| configName | L’utente può specificare un nome di configurazione per aiutare a identificare il connettore |
| templateFolders | Elenco delle cartelle da cui verranno recuperati i modelli |

Altri campi vengono personalizzati in base alla classe di configurazione selezionata per eseguire il connettore.

## Carica il file in una posizione in AEM

Carica il file in una posizione specifica in AEM Assets.

Ad esempio:  `/content/dam/jira.json`

## Creare una configurazione tramite API REST

Puoi registrare la configurazione utilizzando l’API REST. Per ulteriori dettagli, vedi *API REST per registrare un connettore di origine dati* nella sezione Riferimento API per le guide di Adobe Experience Manager.

Dopo aver configurato l’origine dati, il connettore viene elencato nel pannello Origini dati dell’Editor web. È quindi possibile connettersi all&#39;origine dati e inserire uno snippet di contenuto negli argomenti. Per ulteriori dettagli, vedi [Inserire uno snippet di contenuto dall&#39;origine dati](../user-guide/web-editor-content-snippet.md).
