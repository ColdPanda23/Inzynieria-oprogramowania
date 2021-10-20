# Specyfikacja wymagań John Wick The Game (JWTG)

JWTG jest projektem gry wieloosobowej mającej na celu zabić każdą sekundę nudy.Jest to grą typu RPG w której gracz może stać się słynnym zabójcą z ołówkiem w ręku. Cel gracza jest prosty stać się legendą i zastraszać innych. Projekt zakłada poruszanie się po świecie w czasie rzeczywistym świecie generowantm przez serwer oraz walki turowe z NPC-ami lub innymi graczami.



![](John.png)



## Spis treści

[TOC]
## Architektura gry

Opierać się będzie na połączeniu klient-serwer. Użytkownik będzie miał  możliwość poruszania się po interfejsie graficznym, świecie wygenerowanym przez serwer.  Klient będzie interfejsem do serwera jego głównymi cechami będą takie elementy jak:

- Możliwość rejestracji i logowania do bazy danych by stworzyć swój unikatowy profil
- Wyświetlanie stanu postaci na świecie oraz możliwość edytowania jego wyglądu
- Przechwytywanie sygnałów z klawiatury oraz myszki 


Serwer natomiast będzie symulował cały świat, a więc będzie obsługiwał elementy takie jak:

- Interakcje graczy z otoczeniem świata 
- Zarządzanie misjami
- Przechowywanie informacji o stanie postaci (jej poziomie życia, ekwipunku, stanie pieniędzy)
- Zarządzenie kontami graczy
- Przekazywanie klientom stanu własnej postaci oraz otoczenia

## Technologie
Klient będzie pisany w języku C++ oraz QT. Obsługi komunikacji z serwerem oraz interfejsem graficznym zostanie wykorzystana biblioteka SFML.

Serwer zostanie stworzony za pomocą języka Python. Obsługę połączeń obsłuży wbudowana biblioteka `socket`.

Do łączenia się przez internet zostanie wykorzystany protokół TCP.

Ponad to projekt będzie przygotowany i zastosowany w ramach gry w chmurze. 
Gdzie przebieg grania w grę będzie polegał na tym, że gra uruchamiana jest na zewnętrznym superkomputerze, który zajmuje się wszystkimi obliczeniami i wyświetlaniem grafiki gry, która następnie jest przesyłana do odbiorcy w formie obrazu i dźwięku. Gracz steruje kontrolerem i wysyła informacje zwrotne do serwera, który odsyła kolejne zmiany na ekranie.

Niezbędną rzeczy by móc grać w grę będzie za tem dobre połączenie sieciowe. A sam sprzęt nie będzie stanowił problemu.





![Schemat działania game in cloud](cloud.jpeg)


