#Homepage-Integration
Veranstaltungsdaten werden per Webhook zu Veranstalterwebseiten/CMS übertragen.
##Integrationsmöglichkeiten
###Wordpress-Plugin
s. wordpress-plugin.md

###Joomla-Plugin
Coming soon…

###Drupal-Plugin
Coming soon…

###API
Es wird ein Endpoint benötigt, der Daten, die von Eventport kommen, verarbeitet. Dessen Adresse müssen Sie in Eventport-Einstellungen eintragen.

####Authentifizierung
In Eventport-Einstellungen können Sie einen Token generieren, der bei Jedem Datentransport als Query-Parameter `accessToken` mitgeschickt wird,

Beispiel: http://domain.tld/eventport.php?accessToken={{token}}
####Veranstaltungsverwaltung
#####Veranstaltung veröffentlichen
Methode: `POST`

Felder: Event object (s. formats.md)

#####Veranstaltung aktualisieren
Methode: `POST`

Felder: Event object (s. formats.md)

#####Veranstaltung löschen/absagen
Methode: `POST`

Felder: 
* `delete`: true
* `_id`: {{EventId}}

