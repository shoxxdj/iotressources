## Description

MQTT pour "Message Queueing Telemetry Transport" est un protocole clients/serveur basé sur le mécanisme publish/subscribe.

- Un client A s'abonne à fil d'évènements "toto" sur le serveur (subscribe)
- Un client B publie un évènement sur le fil "toto" sur le serveur (publish)
- Le client A est informé de la publication de nouvelles données sur le fil "toto" (subscribe)

MQTT est un éllément central des architectures iot modernes car il permet de recevoir et envoyer des informations a tout système capable de s'y attacher.

Les composants d'une architecture MQTT sont les suivants :

- Les nodes sont les élléments qui se connectent au broker pour publier les messages, s'abonner à des évènements, recevoir des messages
- Le broker est le serveur qui se charge de recevoir les messages, les filtrer et les distribuer aux nodes s'étant abonné à l'évènement concerné

A noter qu'un serveur MQTT peut être un node.

## Identification

Le service MQTT tourne générallement sur les ports suivants :
| Communication | Port TCP |
|--- | --- |
| Non chiffrée | 1883 |
| Chiffrée | 8883 |

## Attacking

## Protections

## Example devices

- https://mqtt.org/
- https://mosquitto.org/
- https://www.zigbee2mqtt.io/
- https://www.home-assistant.io/integrations/zha/

## Ressources
