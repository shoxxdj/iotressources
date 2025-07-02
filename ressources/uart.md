## Description

UART (Universal Asynchronous Receiver Transmitter) est un composant utilisée pour lié deux périphériques (aussi appelé port Série).

Ce type de protocole "simple" n'est pas basé sur une horloge, mais sur une vitesse de transmission commune (baud rate).

C'est un protocole assez ancien, mais encore présent dans de nombreux équipements modernes, il tends à être remplacé par d'autres technologies comme [SPI](./spi.md), [i2c](./i2c.md) ...

## Identification

La première étape consiste à identifier les pins UART. En général ils sont 4 (et souvent, ils sont groupés):

- GND
- RX
- TX
- VCC

Pour identifier GND, le plus simple est de répérer une mise à la terre et d'éffectuer un test de continuitée.

Pour le VCC, une fois le GND identifié, la tension entre les deux doit être constante.

RX doit être à un voltage de 0 si aucun équipement n'est connecté (relier RX à GND pour meusurer la tension)

TX si des données sont transmises (au démarrage de l'appareil par exemple) aura une tension variable.

## Attacking

### Connexions

Une fois les flux UART détectés de nombreux équipements peuvent être utilisés pour établir une connexion sur les pins.

- USBTTL
- BUSPirate
- Une arduino / Une Raspberry ...

Les connexions dépendent de l'appareil utilisés ensuite, la seule régle à retenir concerne RX et TX qui doivent être croisés (RX de l'équipement vers TX du dongle et inversement).

### Découverte du baudrate

Les échanges entre périphériques basés sur UART ont une vitesse de transmission "standardisée". Parmis les plus connues :

- 4800
- 9600
- 115200

Plusieures méthodes existent pour détecter le baudrate approprié.

Soit à partir d'un analyseur logique.
Soit à partir d'un script :

- [https://github.com/devttys0/baudrate](https://github.com/devttys0/baudrate)
- [https://github.com/sickcodes/python3-baudrate](https://github.com/sickcodes/python3-baudrate)

## Protections

## Example devices

## Ressources

- [Attaque d'un device contenant de l'UART](https://shoxxdj.fr/articles/mon-premier-bidouillage-iot.html)
