# Trends-In-AI Sentinel Hub NDVI Analysetool

## Overzicht
Dit Python-script gebruikt de **Sentinel Hub API** om beelden van Sentinel-2-satellieten op te halen en de Vegetatie Index (NDVI) te berekenen. Het voert analyses uit over gewasgezondheid door NDVI te segmenteren en de toestand van gewassen te classificeren op basis van NDVI-waarden.

### Werking
Het script voert de volgende taken uit:
1. **Willekeurige bounding box genereren**: Het genereert een willekeurige bounding box binnen een vooraf gedefinieerd geografisch gebied (bijvoorbeeld Europa).
2. **Verzamelen van satellietbeelden**: Het haalt Sentinel-2-beelddata op via de Sentinel Hub API voor de gegenereerde bounding box.
3. **Berekenen van NDVI**: Het script berekent de **Normalized Difference Vegetation Index (NDVI)** van de satellietbeelden, wat een maat is voor de gewasgezondheid.
4. **Machine Learning Model**: Een **Random Forest-regressor** wordt getraind op basis van de NDVI-waarden om toekomstige NDVI-waarden te voorspellen.
5. **Visualisatie**: De NDVI en de voorspelde NDVI worden gevisualiseerd, samen met een interactieve **Folium-kaart** met satellietbeelden en landgrenzen.
6. **NDVI Classificatie**: Gewassen worden geclassificeerd op basis van hun NDVI-waarden in drie categorieën: "Goed", "Matig", en "Slecht".

### Benodigde API-sleutels
Om dit script te kunnen uitvoeren, heb je een geldig **Sentinel Hub account** nodig. Verkrijg toegangstokens voor de `client_id` en `client_secret` variabelen in het script. Volg de instructies op [Sentinel Hub website](https://www.sentinel-hub.com/) om een account aan te maken en de API-sleutels te verkrijgen.

### Stappen om te runnen
1. **Maak een account aan bij Sentinel Hub**:
   - Ga naar [Sentinel Hub](https://www.sentinel-hub.com/) en maak een account aan.
   - Verkrijg je **client_id** en **client_secret** van de instellingen en pas deze aan in het script bij de respectieve variabelen `CLIENT_ID` en `CLIENT_SECRET`.
   
2. **Installeer de vereiste dependencies**:
   - Maak een virtuele omgeving aan (optioneel) en installeer de vereiste Python-pakketten door het volgende commando uit te voeren:
     ```bash
     pip install -r requirements.txt
     ```

3. **Installeren van extra systeemvereisten**:
   - Zorg ervoor dat je de nodige systeemvereisten hebt geïnstalleerd:
     ```bash
     sudo apt-get update
     sudo apt-get install libgl1-mesa-glx
     ```

4. **Script uitvoeren**:
   - Voer het Python-script uit:
     ```bash
     python script_name.py
     ```

5. **Bekijk de resultaten**:
   - Het script genereert een willekeurige locatie, haalt satellietbeelden op, berekent de NDVI, traint een model en visualiseert de resultaten met behulp van **Matplotlib** en een interactieve **Folium-kaart**.

---

## Vereisten

- **Python 3.x** en de volgende Python-pakketten:
  - `oauthlib`
  - `requests_oauthlib`
  - `geopy`
  - `rasterio`
  - `numpy`
  - `scikit-learn`
  - `folium`
  - `matplotlib`

Je kunt de vereiste afhankelijkheden installeren via het volgende commando:
```bash
pip install -r requirements.txt
```

## Functies van het Script

### 1. **Genereren van een Willekeurige Bounding Box**
   Het script genereert een willekeurige bounding box binnen een opgegeven geografisch gebied. Dit wordt gebruikt om satellietbeelden op te halen voor een specifiek gebied.

### 2. **Verzoeken naar de Sentinel Hub API**
   Het script verstuurt een verzoek naar de Sentinel Hub API om satellietafbeeldingen van het gebied van de bounding box op te halen. De opgehaalde beelden bevatten de bands voor rood, groen, blauw en nabij-infrarood.

### 3. **Berekening van de NDVI**
   NDVI wordt berekend uit de nabij-infrarood (NIR) en rode (RED) banden van de satellietafbeeldingen. NDVI is een belangrijke index voor het bepalen van de gewasgezondheid en vegetatiebedekking.

### 4. **Machine Learning voor NDVI Voorspelling**
   Een **Random Forest-regressor** wordt getraind om NDVI-waarden te voorspellen op basis van de kenmerken van eerdere beelden. Dit wordt gebruikt om de NDVI van latere beelden te voorspellen.

### 5. **Visualisatie en Kaarten**
   Het script maakt gebruik van **Matplotlib** om de NDVI-waarden en de voorspelde NDVI visueel weer te geven. Daarnaast wordt er een interactieve **Folium-kaart** gegenereerd met een satellietlaag en landgrenzen, die het geografische gebied van interesse toont.

---

## Toepassing

- Het script kan worden gebruikt voor **landbouwmonitoring**, waar het de gezondheid van gewassen in een specifiek gebied kan beoordelen en voorspellen.
- Het kan ook nuttig zijn voor **milieuonderzoek** en **natuurlijke hulpbronnenbeheer**, aangezien NDVI een belangrijke indicator is van vegetatiegezondheid en landgebruik.

---

## Belangrijk

- Zorg ervoor dat je een geldig toegangstoken hebt en dat je de juiste configuraties in het script hebt ingesteld om verbinding te maken met de **Sentinel Hub API**.
- Dit script kan worden aangepast voor specifieke regio's door de grenzen van de bounding box aan te passen en door de datums voor de gewenste tijdsperiode op te geven.

---

#### Credits
- **Goudantov Bers**, 3ITAI
- **Van Camp Loïc**, 3ITAI

---

#### Links
- [GitHub project repository](https://github.com/BersGoud/Trends-In-AI-Sentinel-2)