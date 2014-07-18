#Wordpress Plugin#
##Einrichtung##
###Ordnerstruktur###
Das Plugin hat folgende Ordnerstruktur:

    .
    |-- eventport.php
    `-- php
        |-- config.php
        |-- eventport.php
        `-- statusCodes.php
###Konfiguration###
1. Zuerst muss man den API-Token von Eventport in `php/config.php` speichern:

        $accessToken = array('API-Token');

    API-Token findet man auf Eventport in `Einstellungen -> Homepage -> API Token`.
2. Die Variablen `$url_prefix` und `$url_postfix` bilden mit der Wordpress-Post_ID eine URL, die der Veranstaltung auf Eventport zugewiesen wird. Beispiel: 

        $url_prefix = 'http://domain.tld/wp-admin/post.php?post=';
        $url_postfix = '&action=edit';
    bilden `http://domain.tld/wp-admin/post.php?post='{Wordpress-Post_ID}&action=edit`
3. Nun muss man die URL von der Datei `php/eventport.php` auf Eventport in `Einstellungen -> Homepage -> WebHook URL` speichern. Im Normalfall lautet sie `http://domain.tld/wp-content/plugins/eventport/php/eventport.php`

###Aktivierung###
Wenn das Plugin richtig konfiguriert wurde, muss es noch im Adminpanel von Wordpress aktiviert werden. Das Aktivierungsskript erstellt in der Datenbank eine Tabelle, in der alle übertragenen Events gespeichert werden.

###Personalisierung###
Die Datei `php/eventport.php` empfängt Veranstaltungen im JSON-Format, speichert sie in der vom Plugin erstellten Datenbank Tabelle und ermöglicht personalisierte Weiterverarbeitung der Daten. Der Standardcode erstellt für jede Veranstalltung einen Wordpress-Post, kategorisiert ihn, lädt von Eventport ein Bild, das mit dem Verwendungszweck `Homepage Hauptfoto` markiert wurde, herunter und speichert es als Thumbnail/bevorzugtes Foto. **Diese Datei soll an eigene Bedürfnisse angepasst werden.**


