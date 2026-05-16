# Life Expectancy Countdown ⏳

Een confronterende, minimalistische webapplicatie die je resterende tijd op aarde berekent. Op basis van je geboortedatum, geslacht en land haalt de app live de actuele levensverwachting op via de World Bank API en toont een aftelklok tot op de seconde nauwkeurig. 

Ben je de statistieken al voorbij? Dan schakelt de app naadloos over op "Reservetijd" en begint de klok als ereteken op te tellen.

## ✨ Features

*   **Live Data:** Haalt realtime de gemiddelde levensverwachting op via de openbare World Bank API.
*   **Wereldwijde Dekking:** Ondersteuning voor meer dan 200 landen (automatisch alfabetisch gesorteerd).
*   **Meertalig (i18n):** Detecteert automatisch de browsertaal en schakelt vloeiend tussen Nederlands en Engels (inclusief landnamen).
*   **Reservetijd Modus:** Telt op (met een `+`) in opvallend groen als je ouder bent dan de actuele statistische levensverwachting.
*   **Focus Modus:** Schakelt bij activering over naar een afgesloten, afleidingsvrije fullscreen weergave.
*   **Modern Design:** Strak 'glassmorphism' setup-scherm en responsieve, meeschalende typografie (tabular-nums) voor de klok, geoptimaliseerd voor elk schermformaat.

## 🚀 Installatie & Gebruik

Dit project is 100% Vanilla HTML, CSS en JavaScript. Je hebt geen ingewikkelde build-tools, Node.js of externe frameworks nodig.

1. Clone of download deze repository.
2. Open het `index.html` bestand direct in je favoriete webbrowser.
3. Vul je gegevens in en klik op de startknop.

## 🛠 Technologieën & API

*   **Frontend:** HTML5, CSS3 (CSS Variables, Flexbox, Backdrop-filter), Vanilla JavaScript (ES6+).
*   **Data Source:** [World Bank API](https://datahelpdesk.worldbank.org/knowledgebase/articles/889392-about-the-indicators-api-documentation) 
    *   Indicator Mannen: `SP.DYN.LE00.MA.IN`
    *   Indicator Vrouwen: `SP.DYN.LE00.FE.IN`

## 🧠 Hoe de berekening werkt

1.  De applicatie doet een asynchrone `fetch` call naar de World Bank API voor de specifieke ISO-code en het geslacht.
2.  Het script zoekt in de asynchrone JSON-response automatisch naar het meest recente jaar met geldige data (om `null` values van lopende jaren op te vangen).
3.  De verwachte einddatum wordt berekend en telt exacte jaren (met schrikkeljaarcorrectie van `365.2425` dagen per jaar).
4.  Een `setInterval` update de UI elke seconde, waarbij het absolute tijdsverschil tussen 'nu' en de berekende 'einddatum' wordt gedestilleerd naar Jaren, Dagen, Uren, Minuten en Seconden.

## 📄 Licentie

Dit project is open-source. Voel je vrij om de code te gebruiken, aan te passen of te forken.

---
*Ontwikkeld door Jasper (2026).*
