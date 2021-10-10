# IoT Tech opdracht 2: met Adafruit IO een LEDstrip aansturen via Arduino
## Installeer de Arduino IO libraries 
Het eerste wat ik heb gedaan is extra libraries in Arduino te installeren om te kunnen communiceren met Adafruit IO.
Dit heb ik als volgt gedaan:
1. Open een nieuwe Arduino sketch
2. Navigeer naar: sketch —> include library —> manage libraries 
3. Typ in de zoekbalk: Adafruit IO Arduino
Hier heb ik een noob-foutje gemaakt die ik elke keer maak als ik een nieuwe library wil aanmaken, en dat is op more info klikken om vervolgens doorwerken te worden naar de GitHub, dat wil ik niet!
![More info button](https://github.com/EstherWillems/IoT-Tech-Opdr-2/blob/main/1.png)
![De doorverwezen GitHub](https://github.com/EstherWillems/IoT-Tech-Opdr-2/blob/main/2.png)
4. Terug bij manage libraries kies je voor Install All 

## Adafruit IO Setup
Om adafruit te kunnen gebruiken, heb ik een account en een dashboard aangemaakt.
Dit heb ik als volgt gedaan:
1. Navigeer naar https://io.adafruit.com/
2. Klik op get started for free
3. Maak een account aan
4. Navigeer boven naar IO en klik op My Key
5. Kopieer je key en je username, deze heb je later nodig
6. Maak een nieuw dashboard aan: hier ging ik even de fout in, ik snapte niet goed wat er bedoeld werd met de volgende stappen van een block aanmaken, feed name creëren etc. En daardoor heb ik ipv een nieuwe feed een nieuw dshabord aangemaakt:
![Dashboard](https://github.com/EstherWillems/IoT-Tech-Opdr-2/blob/main/3.png)
7. Hierdoor ben ik even terug gaan kijken naar de stappen en heb ik de YouTube video gekeken van Harm.
8. Navigeer nu naar feed 
9. Klik op +new feed
10. Maak een nieuwe feed met de naam color
11. Navigeer nu naar dashboards, ik kan mijn eerst gemaakte dashboard gebruiken na de fout, deze heb ik ook color genoemd
12. Navigeer naar de instellingen rechts boven
13. Creeer een nieuw block
14. Kies de color picker
15. Kies de feed die je net hebt aangemaakt, de mijn heet color
16. Geef je block een titel
17. Klik create block
18. Klik op de je block en kies een kleur, klik op save

## Code uploaden en debuggen
1. Navigeer in een nieuwe arduinen sketch naar: File > Examples > Adafruit IO Arduino > Adafruitio_14_neopixel
2. Daarna heb ik #define PIXEL_PIN 5 aangepast naar #define PIXEL_PIN D5
3. Navigeer naar de tab: config.h
4. Voer op regel 23 en 24 wifi en wachtwoord in
5. Voer op regel 5 en 6 jou adafruit username en key in
6. Check n de serial monitor of die verbonden is
Hier ging ik de mist in.. Ik heb wel 10 minuten gestresst met de foutmelding tot ik er achter kwam dat ik mijn USB niet in de laptop had gedaan..
![nietaangesloten](https://github.com/EstherWillems/IoT-Tech-Opdr-2/blob/main/1.heic)
7. De volgende stap is de sketch uploaden en checken in de monitor of deze verbonden is met Adafruit Io 
Hier ging het ook goed mis bij mij!
Ik kreeg de foutmelding:
![foutmelding](https://github.com/EstherWillems/IoT-Tech-Opdr-2/blob/main/4.png)
Ik wist dat dit niet aan de code of iets lag, maar een port of board connectie fout was. Daarom ben ik begonnen met het raadplegen van internet, bron: https://www.esp8266.com/viewtopic.php?f=26&t=20976
Ik werd hier iniet veel wijzer van en ging zelf uittesten:
In het andere usb poortje op de laptop, werk niet
Een andere port selecteren, werkt niet 
![port](https://github.com/EstherWillems/IoT-Tech-Opdr-2/blob/main/5.png)
Uiteindelijk heb ik een ander NodeMCU geselecteerd bij Board, niet de 1.0 maar de 0.9 
![board](https://github.com/EstherWillems/IoT-Tech-Opdr-2/blob/main/6.png)
8. Hierna heb ik de monitor geopend
9. Een kleur via adafruit IO dashboard gepikt:
![colorpicker](https://github.com/EstherWillems/IoT-Tech-Opdr-2/blob/main/8.png)
![color](https://github.com/EstherWillems/IoT-Tech-Opdr-2/blob/main/9.png)
10. Terug naar de sketch, geeft hij de kleur weer in de montiro:
![Monitor](https://github.com/EstherWillems/IoT-Tech-Opdr-2/blob/main/7.png)
11. En op de led! COOL!
![1eled](https://github.com/EstherWillems/IoT-Tech-Opdr-2/blob/main/2.heic)
![picker](https://github.com/EstherWillems/IoT-Tech-Opdr-2/blob/main/11.png)
![Monitor](https://github.com/EstherWillems/IoT-Tech-Opdr-2/blob/main/10.png)
![2eled](https://github.com/EstherWillems/IoT-Tech-Opdr-2/blob/main/3.heic)

