# Trends-In-AI Sentinel Hub NDVI Analysetool


## Overzicht
Dit Python-script gebruikt de Sentinel Hub API om beelden van Sentinel-2-satellieten op te halen en de Vegetatie Index (NDVI) te berekenen. Het voert analyses uit over gewasgezondheid door NDVI te segmenteren en de toestand van gewassen te classificeren op basis van NDVI-waarden.

### Werking
1. Het script genereert een willekeurige bounding box binnen een vooraf gedefinieerd gebied (bijvoorbeeld Europa).
2. Het haalt Sentinel-2-beelddata op via de Sentinel Hub API.
3. Het berekent de NDVI en voert een classificatie uit op basis van de NDVI-waarden.
4. Het visualiseert de NDVI en de toestand van gewassen (geclassificeerd als "Goed", "Matig", "Slecht").

### Benodigde API-sleutels
Om dit script te kunnen uitvoeren, moet je een geldig **Sentinel Hub** account hebben. Je hebt toegangstokens nodig voor de `client_id` en `client_secret` variabelen in het script. Volg de instructies op [Sentinel Hub website](https://www.sentinel-hub.com/) om een account aan te maken en de API-sleutels te verkrijgen.

### Stappen om te runnen
1. Maak een account aan bij [Sentinel Hub](https://www.sentinel-hub.com/).
2. Verkrijg je **client_id** en **client_secret** van de Sentinel Hub instellingen.
3. Pas deze waarden aan in het script bij de respectieve variabelen: `CLIENT_ID` en `CLIENT_SECRET`.
4. Installeer de benodigde dependencies (zie `requirements.txt`).
5. Voer het script uit.

## Vereisten

Maak een virtuele omgeving aan (optioneel) en installeer de vereiste Python-pakketten via de `requirements.txt`:

```bash
pip install -r requirements.txt
```

installeer ook deze package!

```bash
sudo apt-get update
sudo apt-get install libgl1-mesa-glx
```

### Toepassing
Het script:
- Genereert een willekeurige bounding box binnen een opgegeven geografisch gebied.
- Verstuurt een verzoek naar de Sentinel Hub API om satellietbeelden op te halen.
- Berekent de NDVI (Normalized Difference Vegetation Index).
- Voert segmentatie en contourdetectie uit op gebieden met een lage NDVI (minder gezonde gewassen).
- Classificeert de toestand van gewassen op basis van NDVI en visualiseert dit in een afbeelding.

## Belangrijk
Zorg ervoor dat je een geldig toegangstoken en de juiste configuraties hebt in het script om verbinding te maken met de API van Sentinel Hub.

---
#### Creds
- Goudantov Bers, 3ITAI
- Van Camp Loïc, 3ITAI

----
#### Links
* [Github project repo](https://github.com/BersGoud/Trends-In-AI-Sentinel-2)