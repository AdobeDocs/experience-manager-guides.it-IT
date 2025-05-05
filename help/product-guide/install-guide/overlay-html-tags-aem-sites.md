---
title: Sovrapponi i tag HTML nell’output AEM Sites non legacy
description: Configura le impostazioni video e immagine per l’output di AEM Sites in base alla mappatura dei componenti core
feature: Installation
role: Admin
level: Experienced
source-git-commit: 8310ae8d2e2eeda0fcfba9ec50650c806263cd49
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 0%

---


# Sovrapponi tag HTML nell’output di AEM Sites

Puoi aggiungere e personalizzare i tag HTML nell’output di AEM Sites generato utilizzando il predefinito di AEM Sites basato sulla mappatura dei componenti core dall’editor web. Per personalizzare i tag HTML, è possibile sovrapporre il file `config.xml`. Ad esempio, puoi configurare le mappe video e immagine nell’output di AEM Sites.

Per sovrapporre e aggiornare il file `config.xml`, effettuare le seguenti operazioni:

1. Accedi all’AEM e apri la modalità CRXDE Liti.

1. Passa al file di configurazione disponibile nella posizione seguente:

   `/libs/fmdita/cq/xssprotection/config.xml`

1. Crea un nodo di sovrapposizione della cartella `xssprotection` all&#39;interno del nodo delle app.

1. Passare al file di configurazione disponibile nel nodo `apps`:

   `/apps/fmdita/config/config.xml`

1. Aggiorna i seguenti tag per i video e le immagini. Quindi, salva il file.

Video:

```XML
    <tag name="video" action="validate">
   	<attribute name="src">
      <regexp-list>
        <regexp name="anything"/>
      </regexp-list>
    </attribute>
    <attribute name="width">
       <regexp-list>
           <regexp name="anything"/>
       </regexp-list>
    </attribute>
    <attribute name="height">
       <regexp-list>
          <regexp name="anything"/>
       </regexp-list>
     </attribute>
     <attribute name="data">
       <regexp-list>
         <regexp name="anything"/>
       </regexp-list>
    </attribute>
    <attribute name="class">
       <regexp-list>
           <regexp name="anything"/>
       </regexp-list>
    </attribute>
    <attribute name="poster">
      <regexp-list>
        <regexp name="anything"/>
        </regexp-list>
    </attribute>
    <attribute name="controls">
        <regexp-list>
            <regexp name="anything"/>
        </regexp-list>
    </attribute>
    </tag>
    <tag name="source" action="validate">
      <attribute name="src">
        <regexp-list>
           <regexp name="anything"/>
        </regexp-list>
      </attribute>
    </tag>
```

Mappe immagine:

```XML
    	<tag name="map" action="validate">
	<attribute    name="name">
		<regexp-list>
			<regexp name="anything"/>
		</regexp-list>
	</attribute>
    </tag>
    <!-- Image & image related tags -->
    <tag name="img" action="validate">
	<attribute name="src" onInvalid="removeTag">
		<regexp-list>
			<regexp name="onsiteURL"/>
			<regexp name="offsiteURL"/>
		</regexp-list>
	</attribute>
	<attribute name="name"/>
	<attribute name="alt"/>
	<attribute name="height"/>
	<attribute name="width"/>
	<attribute name="border"/>
	<attribute name="align"/>
	<attribute name="usemap">
		<regexp-list>
			<regexp name="anything"/>
		</regexp-list>
	</attribute>
	<attribute name="hspace">
		<regexp-list>
			<regexp name="number"/>
		</regexp-list>
	</attribute>
	<attribute name="vspace">
		<regexp-list>
			<regexp name="number"/>
		</regexp-list>
	</attribute>
    </tag>
    <tag name="area" action="validate">
	<attribute name="shape">
		<regexp-list>
			<regexp name="anything"/>
		</regexp-list>
	</attribute>
	<attribute name="coords">
		<regexp-list>
			<regexp name="anything"/>
		</regexp-list>
	</attribute>
	<attribute name="href">
		<regexp-list>
			<regexp name="anything"/>
		</regexp-list>
	</attribute>
   </tag>
```




Ulteriori informazioni sulle best practice di [Sicurezza](https://experienceleague.adobe.com/it/docs/experience-manager-65/content/implementing/developing/introduction/security).