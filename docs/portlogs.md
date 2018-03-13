## portlogs.com - Technische Übersicht
### Systemarchitektur
Die Website portlogs.com ist als serverseitig 3-Tier-Webapplikation entworfen und implementiert. Als Webtier wird der Reverseproxy-http-Server "Ngnx" betrieben, welcher die Anfragen an eine auf dem "Ruby on rails" Framework basierende Webapplikation weiterleitet. Sämtliche durch die Webapplikation erzeugten Daten werden in einer Mongodb Datenbank persistiert.

###  Details zur Webapplikation
Die Webapplikation basiert wie bereits erwähnt auf dem ruby on rails Webframework. Da als Backend mongodb genutzt wird werden aus dem ActiveRecord-Framework lediglich die Funktionen zur Validierung der Daten genutzt. Als Besonderheit ist zu nennen, dass zum Zweck der Nachvollziehbarkeit und um möglichst flexibel Änderungen an der Applikation umsetzen zu können sämtliche Datenänderungen nach dem Prinzip des Eventsourcings in einer separaten Collection als Event abgelegt werden. Da wenig dynamische Inhalte genutzt werden, wird das Rendering der HTML-Dokumente komplett serverseitg vorgenommen, ein clientseitiges Framework (Angular, react, etc.) wird nicht genutzt.

### Infrastruktur
portlogs.com wird auf einem virtuellen Linux-Server der Firma strato betrieben. Für das Senden und Empfangen von Emails werden ebenfalls die von Strato angebotenen Dienstleistungen genutzt.
