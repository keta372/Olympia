# Documentació Tècnica del Projecte Web: Olympia Gym
**Cicle Formatiu:** DAM 1A (Desenvolupament d'Aplicacions Multiplataforma)  
**Mòdul:** Llenguatges de Marques (LLM)  
**Alumne:** Kevin Mario Tautu

---

## 1. Contextualització i Justificació de la tria
El present projecte consisteix en el disseny i desenvolupament d'un lloc web responsiu, semàntic i conforme a la legislació de protecció de dades (RGPD) per a **Olympia Gym**, un gimnàs fictici especialitzat en Fitness de gamma alta, entrenaments cardiovasculars d'última generació i, particularment, **Powerlifting** de competició.

### Justificació del projecte:
- **Sector amb alt potencial:** El món de la força i el powerlifting ha viscut un creixement exponencial en els últims anys. Un gimnàs que ofereix material d'elit (com barres i discs calibrats de la marca *Eleiko*) necessita una imatge digital moderna, prèmium i altament funcional per atraure el seu públic objectiu.
- **Estructura i objectius:** El lloc web consta de 5 pàgines clau estructurades de forma neta per guiar l'usuari des del descobriment dels serveis fins al contacte directe, assegurant el compliment estricte de la legalitat vigent de privadesa en el formulari de recollida de dades.

---

## 2. Estructura de Fitxers del Projecte
El portal manté una jerarquia organitzada d'arxius per assegurar l'escalabilitat i la facilitat de manteniment:

```text
Olympia/
├── index.html                  # Pàgina d'inici i presentació general
├── Documentacio_Projecte.md    # Document de justificació i detall de la tasca (aquest fitxer)
├── Pages/
│   ├── serveis.html            # Catàleg detallat de serveis i material del gimnàs
│   ├── sobre.html              # Valors, vídeo de presentació i equip d'entrenadors
│   ├── contacte.html           # Formulari d'atenció amb consentiment explícit RGPD
│   └── privadesa.html          # Pàgina legal amb la política de privadesa exigida
└── Assets/
    ├── css/
    │   └── styles.css          # Estils globals, definició de variables i disseny responsiu
    └── img/
        ├── Eleiko.jpg          # Imatge prèmium de discos calibrats
        ├── Hammer-strength.jpg # Màquines de musculació Hammer Strength
        ├── OlympiaInside.jpg   # Sala de fitness interna
        ├── OlympiaOutside.jpg  # Vista exterior de l'edifici
        └── Technogym.jpg       # Cintes de córrer Technogym
```

---

## 3. Metadades i SEO (Cercadors)
S'han utilitzat metadades avançades en la capçalera (`<head>`) de cada arxiu HTML per facilitar el posicionament orgànic als cercadors i optimitzar l'experiència d'usuari:
- **Charset (`UTF-8`):** Garanteix la correcta codificació de caràcters especials en català (accents, dièresis, c trencalla, etc.).
- **Viewport (`width=device-width, initial-scale=1.0`):** Permet que els navegadors mòbils renderitzin la web de forma adequada sense forçar el zoom.
- **Meta Description:** Cada pàgina inclou una descripció única que sintetitza el contingut del document en menys de 160 caràcters per maximitzar el *CTR* (Click-Through Rate) als resultats de Google.

### Catàleg de recursos de generador de metadades recomanats:
1. **Hey Meta (heymeta.com):** Eina web visual per provar i generar metadades estàndard, Open Graph (Facebook) i Twitter Cards en temps real.
2. **Meta Tags.io:** Excel·lent simulador que mostra com es veurà el portal als cercadors i xarxes socials més populars abans de desplegar el codi.

---

## 4. Semàntica Web i Dades Estructurades (Schema.org)
La semàntica assegura que la informació sigui entenedora tant per als usuaris de lectors de pantalla com per als robots indexadors.

### 4.1 HTML Semàntic (HTML5)
S'ha evitat l'ús abusiu de contenidors genèrics (`<div>`) i s'ha implementat una estructura basada en etiquetes de posicionament estructural:
- `<header>` i `<footer>`: Per definir les capçaleres i peus corporatius globals.
- `<nav>`: Que envolta exclusivament el menú de navegació del lloc web.
- `<main>`: Que engloba l'únic contingut principal i diferenciat de cada pàgina de la web.
- `<section>` i `<article>`: Per subdividir el contingut en unitats de significat lògiques i independents (per exemple, les targetes de serveis i els perfils d'entrenadors).
- `<figure>` i `<figcaption>`: Per a les imatges de la galeria amb el seu corresponent peu descrit explicant la imatge.
- **Ús jeràrquic d'encapçalaments:** Respectant un únic `<h1>` per pàgina (el logotip de la capçalera) i dividint les subseccions amb títols `<h2>` i `<h3>` de manera descendent i ordenada.

### 4.2 Schema.org (Structured Data - Rich Snippets)
Per facilitar la comprensió del contingut als motors de cerca, s'ha afegit un script JSON-LD de dades estructurades a cada fitxer adaptant el tipus de schema a la informació corresponent de cada secció:
- **Inici (`index.html`):** `@type: "GymOrFitnessCenter"`, indicant el nom de l'entitat, descripció, adreça física a Barcelona, rang de preus i horaris de funcionament.
- **Serveis (`serveis.html`):** `@type: "ItemList"` i `@type: "Service"`, llistant detalladament l'assortiment de serveis de musculació i entrenaments que l'usuari pot contractar.
- **Sobre Nosaltres (`sobre.html`):** `@type: "AboutPage"` amb informació sobre els empleats (`@type: "Person"` per a Christian, Marc i Sam) i els seus respectius càrrecs.
- **Contacte (`contacte.html`):** `@type: "ContactPage"`, que assenyala directament el formulari de recollida de consultes dels usuaris.
- **Privadesa (`privadesa.html`):** `@type: "WebPage"`, identificant de manera formal els termes i condicions legals.

*Eines de validació utilitzades:* **Google Rich Results Test** i el validador oficial de Schema.org en línia.

---

## 5. Disseny Responsiu (Responsive Web Design)
La web s'ha maquetat de manera fluida i s'han definit **tres punts de ruptura (breakpoints)** específics per adaptar els estils i la usabilitat segons la mida de pantalla del dispositiu:

1. **Pantalla Gran / Escriptori (Desktop) — Més de 1024px:**
   - La capçalera utilitza Flexbox distribuint el logotip a l'esquerra i la navegació alineada a la dreta.
   - Les targetes de serveis es distribueixen en format de graella flexible de 3 columnes.
   - La taula d'horaris es mostra en amplada completa.
2. **Tauleta / Tablet (Tablet) — Entre 768px i 1024px:**
   - L'amplada dels contenidors es reajusta per oferir un marge de seguretat lateral.
   - Les targetes del catàleg es modifiquen a una disposició de 2 columnes.
   - La galeria adopta una configuració de 3 files per assegurar la proporcionalitat.
3. **Mòbil / Smartphone (Mobile) — Menys de 768px:**
   - El menú es recol·loca verticalment sota el logotip per evitar col·lisions d'enllaços.
   - La graella de targetes passa a 1 sola columna on cada element ocupa el 100% de l'ample.
   - La taula d'horaris s'embolcalla amb un contenidor amb la propietat `overflow-x: auto` per evitar que desquadri l'amplada de la pantalla.
   - El formulari redueix els seus espaiats interiors (padding) per a millor visualització de camps de text.
   - El bàner de galetes reorganitza els botons d'acceptació en línies verticals consecutives fàcilment clicables amb el polze.

---

## 6. Compliment RGPD / LOPD i Privadesa
A l'estat espanyol s'aplica el Reglament General de Protecció de Dades (RGPD, del 25 de maig de 2018) i la LOPDGDD. S'han incorporat tres mesures pràctiques i obligatòries d'acord amb la legislació:
1. **Alerta de Galetes (Cookie Banner):** Un bàner no intrusiu situat a la part inferior de la pantalla que requereix acció per part de l'usuari. Utilitza *localStorage* en JavaScript per recordar l'elecció i evitar aparèixer a cada canvi de pàgina.
2. **Formulari amb Consentiment Explícit:** A la pàgina de contacte, és indispensable activar un checkbox obligatori abans de poder enviar el formulari, garantint que l'usuari ha triat explícitament acceptar el tractament de dades.
3. **Pàgina de Política de Privadesa (`Pages/privadesa.html`):** Redactada en català detallant de forma clara la identitat del responsable del fitxer, la finalitat del tractament de les dades, la seva legitimació legal, el temps de conservació i com exercir els drets ARCO-POL (Accés, Rectificació, Cancel·lació, Oposició, Portabilitat i Limitació).

---

## 7. Validació del Codi (W3C)
El codi s'ha estructurat seguint estàndards semàntics moderns i s'ha validat amb les eines oficials del *World Wide Web Consortium*:
- **Validació HTML5 (validator.w3.org):** S'ha garantit l'absència d'etiquetes obsoletes o mal tancades, i s'ha comprovat que els atributs obligatoris com `alt` en imatges i `for` en etiquetes de formulari estiguin perfectament definits.
- **Validació CSS3 (jigsaw.w3.org/css-validator):** Es confirma la inexistència d'errors sintàctics de CSS en les definicions de variables globals (`:root`) i les propietats modernes de Flexbox, Grid i adaptabilitat de vídeo de YouTube.

---

## 8. Gestió del Projecte i Eines
- **Hosting utilitzat:** Allotjat gratuïtament en servidors de GitHub Pages per a una visualització pública immediata i una integració de codi neta.
- **Planificació:** Organitzat mitjançant un tauler Kanban a Trello dividint les tasques en *Per fer*, *En curs*, *Validació* i *Finalitzades* per garantir el lliurament abans de la data límit.
- **Plataforma de codi:** Github per al control de versions.
