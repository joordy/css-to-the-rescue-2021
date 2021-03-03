# **CSS To The Rescue**

## 🔦 **Description**

**CSS Zen Garden** was een initiatief 20 jaar geleden om de mogelijkheden van CSS te verkennen: hoe kon je destijds CSS gebruiken om statische HTML om te zetten naar een visueel meesterwerk. Dezelfde taak nu voor jou, maar nu. Voor deze cursus maak ik een restaurant-menu met verschillende contexten en beperkingen

---

## 📄 **Proces**

### 🗓️ **Week 1 - Planning**

#### **Opdracht**

Als opdracht voor CSS To The Rescue heb ik gekozen voor **CSS Zen Garden - 2021 version**. Deze opdracht bestaat uit het ontwerpen van een menu-kaart met verschillende gerechten.

#### **Context**

- Prefers-color-scheme: Media query waarbij er gebruik kan worden gemaakt van dark & lightmode, op basis van de OS instellingen.
- Prefers-reduced-motion: Media-query voor degene die een gereduceerde website willen hebben, oftewel zonder animaties.
- Input met radio-buttons: Content laten zien op basis van input via radio buttons.

#### **Requirements**

- Responsive without media-queries (min-width & max-width)
- Level AAA (Lighthouse check 100%)

#### **Uitdagingen**

De komende weken wil ik mij voornamelijk focussen op het werken met verschillende variabelen, animaties en een bestands-structuur op te zetten. Al deze elementen zijn voor mij nog nieuw, en wil ik in combinatie met de context & requirements implementeren binnen mijn ontwerp.

#### **Versie 0.1**

Als eerste versie heb ik een schets opgezet waarbij er alle menu-items over elkaar heen worden 'gestacked'. Hiermee wordt er één grote stapel gecreëerd tijdens het scrollen door het menu. De gerechten worden met `position: sticky` en een `transform: rotate(x deg)` op hun plaats gezet.

![v0.1](https://user-images.githubusercontent.com/48051912/109819840-c0d10700-7c34-11eb-9ad9-5e9c51a1bba8.png)

<!-- Welke opdracht ga je doen en voor welke opties kies je qua uitwerking.
Met welke CSS-technieken ga je als eerste aan de slag.
Waar liggen je (grootste) uitdagingen.
Neem schets(en) van je ontwerp op.
Maak wellicht ook al een eerste breakdown-schets. -->

### 🗓️ **Week 2 & 3 - Voortgang**

#### **Koerswijziging**

Tegenover concept 0.1 vanuit week 1, heb ik het roer volledig om gegooid in week 2. Zoals hieronder te zien is, is het ontwerp van de pagina dusdanig veranderd. Bovenin de pagina is er een header element, welke de gehele hoogte van de viewport in beslag neemt, gevolgd door een navigatie-menu, met daaronder de bijbehorende elementen. Dit wordt gedaan met behulp van een `input[type='radio']`, waarmee de bijbehorende content wordt getoond.

#### **Glitch**

Als thema van mijn pagina heb ik gekozen om glitch effecten toe te voegen. Vooralsnog alleen op de `H1`, maar het doel is om hier een terugkerend element van de maken op de site.

#### **Contrast**

Om een hoog contrast te hebben (minimaal 7:1), heb ik er voor gekozen om twee uitspringende kleuren te gebruiken. Uiteindelijk zijn het de kleuren donkerblauw (`rgb(34, 31, 62)`) & beige (`rgb(242, 195, 153)`) geworden, welke een score van 9.77 haalt volgens de website [www.contrast-ratio.com](https://contrast-ratio.com/#rgb%28242%2C%20195%2C%20153%29-on-rgb%2834%2C%2031%2C%2062%29), wat op basis van de WCAG 2.0 (Leven AAA) wordt gemeten.

#### **Versie 1.0 & 2.0**

![v1+v2](https://user-images.githubusercontent.com/48051912/109824293-fb3ca300-7c38-11eb-8caa-9dc6a23bc94c.png)

<!-- Laat je voortgang zien ('praatje met plaatjes').
Wat ging er soepel en wat was lastig.
Welke experimenten heb je gedaan die die 'mislukt' zijn.
Heb je nieuwe inzichten hoe je de kracht CSS kunt benutten (of juist niet).
Neem wijzigingen aan je 1e plan op.
Waar liggen je (nieuwe) uitdagingen voor komende week. -->

### 🗓️ **Week 4 - Afronding**

<!-- Bespreek je eindresultaat. ('praatje met plaatjes').
Wat ging er soepel , wat was lastig en waar ben je trots op.
Welke experimenten heb je gedaan die die 'mislukt' zijn.
Heb je nieuwe inzichten hoe je de kracht CSS kunt benutten (of juist niet).
Waar wil je meer mee gaan doen. -->

#### **Verbeteringen t.o.v week 2/3**

Ik ben gaan voortborduren op het concept wat ik in week 2 heb opgebouwd. Ik heb onder meer mijn hele CSS structuur overhoop gehaald, om hier een logisch systeem voor te maken voor mijzelf. Ook heb ik met verschillende kleuren geëxperimenteerd, en heb ik een 3D-rotatie toegevoegd aan mijn idee, evenals nog meer toevoegen van glitch-elementen binnen mijn pagina.

Verschillende nieuwe elementen die ik hier aan heb toegevoegd is de `:is()` selector binnen CSS, waardoor je kortere code kan schrijven, om de elementen aan te roepen. Ook heb ik gebruik gemaakt van `tabindex='0'` en de focus state, om zo te kunnen navigeren binnen de website.

Ook heb ik de navigatie opnieuw geschreven. In plaats van het `display` property om te gooien naar `block` in plaats van `none`, wordt er nu gebruik gemaakt van een `transform: translateX()`. Hierdoor kan er op de handeling een transitie worden getoont, waardoor het menu vloeiend beweegd.

#### **Structure**

```md
assets/
+-- css/
| +-- animations/
| | +-- keyframes.css
| +-- footer/
| | +-- footer.css
| +-- header/
| | +-- header.css
| +-- main/
| | +-- glitches/
| | | +-- glitches.css
| | +-- items/
| | | +-- item.css
| | +-- list/
| | | +-- list.css
| | +-- navigation/
| | | +-- navi.css
| | +-- main.css
| +-- media/
| | +-- light_dark.css
| | +-- motion.css
| +-- states/
| | +-- focus.css
+-- index.html
```

Aan de hand van deze structuur heb ik er voor gekozen om alle code-onderdelen op te splitsen. Ik heb er **bewust** niet voor gekozen om atomic web-design in mijn CSS-structuur te implementeren doordat ik dit zelf niet fijn vind werken, met enkel CSS. Binnen frame-works komt dit beter tot zijn recht, doordat alle code van een desbetreffend element dan bij elkaar staat.

Zodoende is mijn keuze geworden om alle elementen los te behandelen in een _header_, _main_ en _footer_ folder, waarin de hoofd-elementen worden gestyled. Randzaken zoals _media-queries_, _keyframes_ & _states_ staan ook in een losse folder, doordat dit geen directe invloed heeft op de styling van een element.

#### **Experimenten**

Ik heb onder meer geëxperimenteerd met de twee-kleuren restrictie. Hiervoor heb ik gebruik gemaakt van de CSS filters. Denk hierbij aan `brightness(100%)`, `hue-rotate(100deg)`, `saturate(100%)` en ga zo nog maar even door. Helaas heb ik door mijn vele glitch-toevoegingen hier van af moeten stappen, omdat hier de kleuren rood, groen en blauw veelvoudig werden gebruikt.

#### **Accessability performance**

Een van mijn **requirements** was om goed te scoren op level AAA van de WCAG. Dit is onder meer te meten met de LightHouse tool, en hierbij is een score van 100% op basis van accessability naar boven gekomen. Enkel op basis van SEO is er geen 100% score behaald, dit was dan ook geen vereiste om level AAA te behalen, wat staat voor de accessabilty van een website.

![Accessability score](https://user-images.githubusercontent.com/48051912/109824991-ab121080-7c39-11eb-9e9f-a0aea1af85f3.png)

#### **Final result**

![Final result](https://user-images.githubusercontent.com/48051912/109820950-c4b15900-7c35-11eb-99c5-8872c37fe512.png)

---

## 🚀 **Live link**

De website is hier te bijken: [cssttr.netlify.app](https://cssttr.netlify.app/)

---

## 🔑 **Installation**

### **Clone the repository**

```bash
  git clone https://github.com/joordy/css-to-the-rescue-2021.git
```

---

## 🔍 **Sources**

- W3docs. (2020, July 14). How to Create Glitch Effect With CSS. Retrieved February 17, 2021, from https://www.w3docs.com/snippets/css/how-to-create-glitch-effect-with-css.html
- MDN. (2021, February 19). animation-fill-mode - CSS: Cascading Style Sheets | MDN. Retrieved March 02, 2021, from https://developer.mozilla.org/en-US/docs/Web/CSS/animation-fill-mode
- Perez, J. A. (2019, September 2). Carousel - CSS only. CodePen. Retrieved February 12, 2021, from https://codepen.io/JonAnderDev/pen/wBopXo
- Graham, G. (2019, January 4). :is(). CSS-Tricks. Retrieved March 03, 2021, from https://css-tricks.com/almanac/selectors/i/is/
<!-- - - Source (n.d.) Writer, Source. Retrieved February 01, 2020, from weblink -->

---

## 💽 **License**

---

<!-- https://codepen.io/ClementRoche/details/YQeQYJ  -->
<!-- # CSS To The Rescue

## 🔦 Description

**CSS Zen Garden** was an initiative 20 years ago to explore the possibilities of CSS: how can you use CSS to transform fixed HTML into a visual masterpiece at the time. The same task for you, but now. For this course, I create a restaurant menu with different contexts and restrictions

### Context



### Requirements

- Apply SVG in shapes, masks and filters
- Responsive without media-queries
- Level AAA (Lighthouse check 100%)

---

## ✍🏼 Sketches

![version_01 of idea's](https://user-images.githubusercontent.com/48051912/107026502-1556a300-67ab-11eb-8177-57ecc3afa11b.png)

---

## 📝 Breakdown

---

## 🚀 Live link

[www.cssttr.netlify.app](https://cssttr.netlify.app/)

---

## 📄 Proces

---

## Features

---

## 🔑 Installation

### Clone the repository

```bash
  git clone https://github.com/joordy/css-to-the-rescue-2021.git
```

---
