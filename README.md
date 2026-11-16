# Collega-netwerk voor OneNote (web)

Een taakvenster-invoegtoepassing voor OneNote op het web: wie weet wat, en waarvoor benader je ze.

**Wat het doet**
- **Zoeken**: typ een onderwerp en zie wie je moet hebben, met "Benader voor" bovenaan elk kaartje.
- **Filteren** op expertise, organisatie of dossier; sorteren op "langst niet gesproken".
- **Mindmap**: gegroepeerd op expertise, organisatie of dossier. Thema's in- en uitklappen, naam aanklikken voor details, "Groot scherm" voor overzicht.
- **+ Collega**: invulformulier met naam, organisatie/team, rol, expertise, waarvoor benaderen, dossiers, laatst gesproken, contact en notitie.
- **Naar OneNote**: zet de mindmap (als afbeelding) of een overzichtstabel op de geopende pagina.

## Bestanden
| Bestand | Functie |
|---|---|
| `taskpane.html` | De hele invoegtoepassing (opmaak en code in één bestand) |
| `manifest.xml` | Vertelt OneNote waar de invoegtoepassing staat |
| `icon-32.png`, `icon-64.png`, `icon-80.png` | Pictogrammen |

## Installeren in 3 stappen

### 1. Zet de bestanden op een https-adres
OneNote laadt de invoegtoepassing vanaf een webadres; een bestand op je eigen schijf werkt niet. De eenvoudigste gratis route is GitHub Pages:
1. Maak op github.com een nieuwe **openbare** repository, bijvoorbeeld `collega-netwerk`.
2. Upload `taskpane.html` en de drie pictogrammen.
3. Ga naar **Settings > Pages**, kies bij *Branch* `main` en sla op.
4. Na een minuut staat de pagina op `https://<gebruikersnaam>.github.io/collega-netwerk/taskpane.html`. Open dat adres ter controle: je ziet de invoegtoepassing dan al als gewone webpagina.

De code bevat geen gegevens over collega's, dus openbaar hosten is geen probleem. Elke andere https-webruimte werkt ook.

### 2. Pas het manifest aan
Open `manifest.xml` in Kladblok en vervang alle vier keer `JOUW-ADRES` door je eigen adres zonder `https://`, bijvoorbeeld `gebruikersnaam.github.io/collega-netwerk`. Opslaan.

### 3. Upload het manifest in OneNote
1. Open een notitieblok in OneNote op het web.
2. Kies **Invoegen > Office-invoegtoepassingen** (Engels: *Insert > Office Add-ins*).
3. Kies op het tabblad **Mijn invoegtoepassingen** (privéaccount) of **Mijn organisatie** (werkaccount) voor **Mijn invoegtoepassing uploaden** (*Upload My Add-in*).
4. Selecteer `manifest.xml` en klik op **Uploaden**. Het taakvenster opent naast je pagina.

Later open je hem opnieuw via Invoegen > Office-invoegtoepassingen.

## Goed om te weten
- **Werkaccount**: beheerders kunnen het zelf uploaden van invoegtoepassingen uitzetten. Ontbreekt de uploadknop, vraag dan IT om het manifest centraal uit te rollen (Microsoft 365-beheercentrum > Geïntegreerde apps), of test eerst met een privé Microsoft-account.
- **Waar staan je gegevens**: alleen in de opslag van je eigen browser, er wordt niets verstuurd. Wis je je browsergegevens of wissel je van browser, dan is de lijst weg. Maak daarom af en toe een back-up via **Meer > Back-up** en plak die bijvoorbeeld op een OneNote-pagina. Importeren doe je op dezelfde plek.
- **Opnieuw uploaden**: OneNote bewaart een zelf geüpload manifest ook in de browser. Na het wissen van je cache upload je het manifest opnieuw; je gegevens zet je terug met de back-up.
- **Persoonsgegevens**: je legt informatie over collega's vast. Houd het zakelijk.
- **Getest**: de pagina zelf (zoeken, filteren, mindmap, formulier, back-up) is getest in een browser. De koppelingen met OneNote (tabel en mindmap op de pagina zetten, groot scherm binnen OneNote) volgen de officiële OneNote-API maar zijn niet in een echte OneNote-omgeving getest.

## Problemen oplossen
| Probleem | Oplossing |
|---|---|
| Manifest wordt geweigerd | Controleer of `JOUW-ADRES` overal vervangen is en het adres met `https://` begint. |
| Taakvenster blijft leeg | Open het adres van `taskpane.html` los in de browser; werkt het daar niet, dan klopt de hosting niet. |
| "Op pagina zetten" doet niets | Klik eerst in een bewerkbare pagina (geen alleen-lezen sectie) en probeer opnieuw. |
| Gegevens blijven niet bewaard | De browser blokkeert opslag voor ingesloten pagina's (privémodus, strenge trackingpreventie). Gebruik een gewoon venster of sta opslag toe. |

## Aanpassen
Alles staat in `taskpane.html`. Velden per collega staan in de functie `schoon`, de kleuren van de mindmap in `PALET`. Na een wijziging upload je alleen `taskpane.html` opnieuw naar je webruimte; het manifest hoeft niet opnieuw.
