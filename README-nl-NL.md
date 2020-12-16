Forty Seconds CV
================

[中文](README-zh-CN.md) | [English](README.md)

## Omschrijving

Gewoon een andere CV klasse voor LaTeX - maar deze keer zeer aanpasbaar!

Dit project kan worden beschouwd als een bijna volledige herschrijving van de
oorspronkelijke twentysecondcv klasse. Het is niet bedoeld om een nieuwe
cv-stijl aan te bieden die je nergens anders kunt vinden, maar neemt juist een
zeer gevestigde stijl en voegt een duidelijke gebruikersinterface toe aan bijna
alle lay-outelementen en maakt daarmee een zeer aanpasbare framework-klasse:
FortySecondsCV.

Probeer het gewoon zelf, beginnend vanaf `template.tex`!

Wanneer zou je twentysecondcv of altacv of een andere LaTeX CV klasse moeten
gebruiken:

* Je bent tevreden met de lay-outelementen die worden aangeboden door de
  bestaande CV-stijlen
* Je hoeft het afdrukformaat niet aan te passen
* Je wilt je CV-stijl verder niet aanpassen

Wanneer zou je de FortySecondsCV klasse moeten gebruiken:

* Je bouwt graag een CV op dat is geoptimaliseerd voor 2 pagina's incl. een
  zijbalk (met de optie voor extra pagina's)
* Je wilt je CV in hoge mate aanpassen met een groot kleurenpalet en
  layout-elementen
* Je wilt geen enkele definitie in het klassenbestand wijzigen
* Je geeft de voorkeur aan een eenvoudig te gebruiken gebruikersinterface voor
  bijna alle stijlelementen
* Je hebt een netjes geschreven klassenbestand nodig voor het geval je toch
  besluit om low-level klasse definities te veranderen


## Attributies

* Deze LaTeX CV-klasse is gebaseerd op de stijlideeën van de
  [twentysecondscv class](https://github.com/spagnuolocarmine/TwentySecondsCurriculumVitae-LaTex)
  door Carmine Spagnuolo
* Pictogrammen voor talen in de template zijn afkomstig uit [de repository van gosquared](https://github.com/gosquared/flags)


## Benodigdheden

Je moet het document compileren met XeLaTeX of LuaLaTeX om de nieuwste Font
Awesome-pictogrammen (`fontawesome5`) en Academicons te kunnen gebruiken. Als je
alsnog wilt compileren met pdfLaTeX om welke reden dan ook, ~~zal FortySecondsCV
terug vallen naar het oudere pictogrampakket (`fontawesome`), waar sommige
pictogrammen er anders uit zien en anderen niet eens zijn inbegrepen~~ zal
Academicons niet beschikbaar zijn.


## Licentie

Forty Seconds CV is uitgebracht onder de BSD 3-clausule licentie. Zie het
LICENSE bestand voor meer informatie.


## Gebruikersinterface

### Klasse-opties

De mogelijke opties die kunnen worden doorgegeven aan FortySecondsCV zijn:

* alle geldige opties voor de standaard artikelklasse zoals bijv. `a4paper` of
  `11pt`.
* `sidesectionsize` stelt de lettergrootte van sectie titels in de zijbalk in op
  `\large`, `\huge`, etc., wanneer deze optie wordt ingesteld op `large`,
  `huge`, etc. (d.w.z. zonder de backslash er voor)
* `showframes` toont randen rond de zijbalk en de teksten in het hoofddocument
  wat kan helpen om de marges correct aan te passen. Let wel op dat hierdoor de
  inhoud van tabellen wat wordt verplaatst omdat de lijnen ook wat ruimte
  innemen.
* `vline=<lengte>` tekent een rode verticale lijn op x-positie `<length>` om te
  helpen de inhoud van de zijbalk aan te passen.
* `maincolor=<kleur>` stelt de themakleur in die wordt gebruikt voor de gehele
  zijbalk incl. koppen, pictogrammen, en grafieken. Veel kleuren worden van deze
  afgeleid.
* `sidecolor=<kleur>` stelt de achtergrondkleur van de zijbalk in.
* `sidetextcolor=<kleur>` stelt de kleur van de tekst in de zijbalk in.
* `sectioncolor=<kleur>` stelt de kleur van sectiekoppen in de hoofdtekst in.
* `itemtextcolor=<kleur>` stelt de kleur van cvitem beschrijvingen in.
* `subsectioncolor=<kleur>` hetzelfde als sectioncolor, voor subsecties.
* `sidebarwidth=<lengte>` stelt de totale breedte van de zijbalk in, d.w.z. de
  breedte van de zichtbare zijbalkkleur.
* `topbottommargin=<lengte>` stelt de boven- en onderpaginamarge in voor beide
  kolommen.
* `leftrightmargin=<lengte>` stelt de linker- en rechterpaginamarge in voor
  beide kolommen en tevens hoeveel ruimte er tussen de beide kolommen zal zijn.
* `profilepicsize=<lengte>` stelt de breedte van de profielfoto in.
* `profilepicborderwidth=<lengte>` stelt de breedte in van de rand van de
  profielfoto.
* `profilepicstyle=profilecircle` toont de profielfoto in een cirkel zoals in
  de originele `twentysecondcv` klasse.
* `profilepiczoom=<float>` stelt de zoomfactor voor de profielfoto in. Samen met
  de twee onderstaande opties kun je jouw favoriete profielfoto direct zonder
  wijziging hier gebruiken en hier bijsnijden.
* `profilepicxshift=<lengte>` stelt de xshift voor de profielfoto in.
* `profilepicyshift=<lengte>` stelt de yshift voor de profielfoto in.
* `profilepicrounding=<lengte>` stelt de afrondingsradius in voor de rechter
  bovenhoek en de linker benedenhoek voor de standaard afgeronde
  profielfotostijl.
* `sidebarplacement=right` verplaatst de zijbalk naar de rechterkant van het
  document in plaats van links.

Let op:

* Lengtes kunnen worden opgegeven in elke absolute lengte-eenheid, bijv. `em`
  voor breedtes, `ex` voor hoogtes, of relatieve waarden zoals`0.5\paperheight`
  of `0.3\linewidth`.
* Kleuren kunnen worden gekozen uit de volledige catalogus verzorgd door de
  `dvipsnames`, `svgnames`, en` x11names` opties van het `xcolor` pakket. Zie de
  [xcolor pakket documentatie](http://mirrors.ctan.org/macros/latex/contrib/xcolor/xcolor.pdf)
  voor meer informatie en kleurentabellen.
* Kleuren kunnen ook opnieuw worden gedefinieerd binnen de documenttekst met
  bijv. `\definecolor{sidecolor}{HTML}{000000}`.

### Zijbalk

De zijbalken aan de voor- en achterkant van het CV worden gegenereerd met behulp
van de commando's `\makefrontsidebar` en`\makebacksidebar` binnen het `document`
gedeelte van de LaTeX code. Het wordt aanbevolen om `\newpage` onmiddellijk vóór
`\makebacksidebar` te gebruiken.

Lay-outelementen in de zijbalk aan de voor- en achterkant kunnen worden
toegevoegd met
```latex
\addtofrontsidebar{}
\addtobacksidebar{}
```
met enkele vooraf gedefinieerde elementen zoals profielfoto, naam en functie
titel al ingesteld, of definieer ze volledig opnieuw met
```latex
\renewcommand{\makefrontsidebar}{%
  \begin{sidebar}
    <jouw code>
  \end{sidebar}
}
```
Je kunt alle eerder gedefinieerde macro's gebruiken zoals `\cvname` en
`\cvjobtitle` of andere elementen zoals de icontable
[hier](#persoonlijke-informatie) uitgelegd.
Zie [#22](https://github.com/PandaScience/FortySecondsCV/issues/22) voor een
meer gedetailleerd voorbeeld.

De `sidebar`-omgeving zorgt ervoor dat in ieder geval alle tekst correct wordt
gepositioneerd in de linkerkolom (zijbalk) van elke pagina. Als je iets
beperkters nodig hebt, bijv. om overloop te voorkomen bij gebruik van meerdere
diagramlabels, kun je delen van de zijbalkinhoud insluiten in een
`sidebarminipage`:
```latex
\begin{sidebarminipage}
  \chartlabel{Bubble Diagram}
  \chartlabel{met}
  \chartlabel{juiste}
  \chartlabel{overflow}
  \chartlabel{bescherming}
  \chartlabel{voor}
  \chartlabel{labels}
\end{sidebarminipage}
```
Met behulp van de `sidebar`-omgeving kun je ook makkelijk meer sidebar
definities toevoegen voor extra pagina's. Als je wilt dat de zijbalk in plaats
van de linkerkant, aan de rechterkant van de pagina verschijnt, gebruik dan de
klasse-optie `sidebarplacement=right`.

Als je de zijbalk volledig wilt verwijderen op een enkele pagina, roep dan
simpelweg de zijbalk constructors niet aan. Vervolgens kun je de gewenste marges
instellen met
```latex
\newpage
% geen \makebacksidebar enz.
\newgeometry{
  top=<lengte>,
  bottom=<lengte>,
  left=<lengte>,
  right=<lengte>
}
```
De standaardinstellingen zijn `\leftrightmargin` en `\topbottommargin`. Voor het
geval je op de volgende pagina's weer wilt terugkeren naar de standaard layout,
hoef je alleen maar `\restoregeometry` aan te roepen na de volgende `\newpage`.

De tekstkleur van sidebar elementen kan worden aangepast via de klasse-optie
`sidetextcolor`. Voor zwaardere stijlwijzigingen kun je ook het `\sidetext`
commando aanpassen aan je behoeften. Bijvoorbeeld:
```latex
  \renewcommand{\sidetext}[1]{\textcolor{red}{\texttt{#1}}}
```

### Persoonlijke informatie

Stel persoonlijke informatie in via handige functies:
```latex
  % logo afbeelding
  \cvlogopic[0.8\linewidth]{pics/logo.png}
  % profielfoto
  \cvprofilepic{pics/profile.png}
  % uw naam
  \cvname{Panda Bear}
  % functietitel
  \cvjobtitle{Panda Scientist,\\[0.2em] Panda of the Year}
  % geboortedatum
  \cvbirthday{Mar 7, 2019}
  % kort adres / locatie, gebruik \newline als er meer dan 1 regel nodig is
  \cvaddress{Park Ave.~1, 555 555 B-Woods}
  % telefoonnummer
  \cvphone{+86 555 555 555}
  % persoonlijke website
  \cvsite{https://pandascience.net}
  % e-mailadres
  \cvmail{panda@bamboo.cn}
  % pgp sleutel
  \cvkey{4096R/FF00FF00}{0xAABBCCDDFF00FF00}
  % elk ander custom item
  \cvcustomdata{\faFlag}{Chinese}
```
* Alleen `\cvname` en `\cvjobtitle` zijn verplicht.
* Als je wilt dat een (optioneel) item niet in je CV verschijnt, gebruik het dan
  simpelweg niet. Als je geen van deze handige commando's gebruikt, zal de
  tabel met persoonlijke informatie helemaal niet verschijnen.
* Het e-mailadres wordt automatisch gekoppeld aan `mailto:email`.
* Er wordt ook een hyperlink naar je website gemaakt.
* Voor de pgp-sleutel definieert het eerste argument de weergegeven tekst,
  die gekoppeld is aan een keyserver die zoekt naar de ID in het tweede
  argument.<br>
  Let op: Om veiligheidsredenen dien je de lange ID van je sleutel of de
  vingerafdruk in het tweede argument te gebruiken.
* De macro `\cvcustom{<pictogram>}{<tekst>}` laat zien hoe je nieuwe regels
  definieert met een pictogram als eerste, en wat tekst als tweede argument.
  Achter de schermen is dit commando eigenlijk gebruikt om de andere commando's
  in het bovenstaande voorbeeld te definiëren.

Als je de standaardstijl van de "persoonlijke informatietabel" niet mooi vindt,
kan je jouw eigen tabel definiëren met
```latex
\begin{icontable}[<arraystretch=1>]{<breedte 1st column>}{<ruimte tussen kolommen>}
  \personal{<pictogram>}{<tekst>}
  \social{<pictogram>}{<URL>}{<tekst>}
\end{icontable}
```
waarbij de breedte van de 1e kolom ook de grootte van alle pictogrammen in die
kolom bepaalt, aangezien pictogrammen worden geschaald naar de maximale breedte
van hun cel. Voor visuele doeleinden kun je de ruimte tussen de pictogrammen en
de bijbehorende tekst bepalen met het 2e verplichte argument. Het optionele
argument bepaalt de afstand tussen de tabel regels, wat alleen belangrijk is
voor kleine pictogramhoogtes (d.w.z. kleine 1e kolommen).

* `\personal` accepteert een pictogram en een tekst. Het pictogram wordt
  doorgegeven aan `\circleicon{<pictogram>}`, die een cirkel tekent die is
  gevuld met `maincolor` rondom het pictogram. Het pictogram zelf wordt wit
  weergegeven.
* `\social` accepteert een pictogram en een URL + tekst. `Tekst` wordt als label
  weergegeven van een hyperlink naar `URL`.
  In het geval dat `URL` leeg is, zal uw LaTeX-compiler een onschuldige
  waarschuwing geven over "Suppressing link with empty target" en de tekst zal
  worden weergegeven zonder link. Het pictogram zelf wordt doorgegeven aan
  `\socialicon{<pictogram>}`, dat simpelweg de grootte wijzigt van pictogram en
  het tekent in `maincolor`. Deze versie heeft de voorkeur voor de pictogrammen
  van sociale netwerken (zie voorbeeld).

De standaard "persoonlijke informatietabel" gebruikt
```latex
\begin{icontable}[1.6]{1.7em}{0.4em}
  \personal{<pictogram>}{<tekst>}
\end{icontable}
```

### Andere stijlelementen in de zijbalk

* Sectie kop tekst
  ```latex
  \profilesection{<sectie kop tekst>}
  ```

* Eenvoudige vaardigheid met alleen een pictogram en wat tekst en met optionele
  inspringing
  ```latex
  \skill[<inspringing>]{<pictogram>}{<tekst>}
  ```

* Vaardigheid uitgedrukt in punten, bestaande uit een icoon, tekst, het aantal
  punten en optioneel het maximaal mogelijke aantal punten (standaard: 5).
  Een paar voorbeelden:
  ```latex
  \pointskill{<pictogram>}{<tekst>}{<punten>}
  ```
  maakt een vaardigheid met behulp van een Font Awesome- of Academicons
  pictogram met wat tekst en een ranking van `<punten>` van de 5 punten.
  ```latex
  \pointskill{<pictogram>}{<tekst>}{<punten>}[<maximum>]
  ```
  maakt een vaardigheid met behulp van een Font Awesome- of Academicons
  pictogram met wat tekst en een ranking van `<punten>` uit `<maximum>`
  mogelijke punten.
  ```latex
  \pointskill{\flag{DE.png}}{Duits}{5}
  ```
  creëert een taalvaardigheid met behulp van een vlagpictogram, dat moet worden
  aangegeven met het `\flag` commando om de klasse te informeren dat het
  pictogram niet gekleurd moet worden in `\maincolor`.

* Vaardigheid uitgedrukt in een balk, bestaande uit een pictogram, tekst en
  percentage van hoe ver de vaardigheidsbalk moet worden gevuld
  ```latex
  \barskill{<pictogram>}{<tekst>}{<percentage>}
  ```

* "Over mij" tekst
  ```latex
  \aboutme{<tekst over meerdere regels>}
  ```

* Afgerond en gekleurd label voor bijv. grafieken en andere afbeeldingen
  ```latex
  \chartlabel{<tekst>}
  ```

* Wiel diagram
  ```latex
  \wheelchart{<buitenste straal>}{<binnenste straal>}{%
    <percentage>/<afstand>/<kleur>/<tekst>,
    <percentage>/<afstand>/<kleur>/<tekst>
  }
  ```
  * Percentages moeten samen uitkomen op 100

* Lidmaatschappen
  ```latex
  \begin{memberships}[<afstand>=1em]
    \membership[<pictogrambreedte>=4em]{<logo>}{<tekst>}
    \membership[<pictogrambreedte>=4em]{<logo>}{<tekst>}
    \membership[<pictogrambreedte>=4em]{<logo>}{<tekst>}
  \end{memberships}
  ```
  * De breedte van de 1e kolom met de pictogrammen is gelijk aan de breedte van
    de grootste pictogram zodat alle tekst in de 2e kolom uitgelijnd is.

* Sociale netwerken
  ```latex
  \begin{socialnetwork}[<afstand>=1em]
    \social{<pictogram>}{<URL>}{<tekst>}
    \social{<pictogram>}{<URL>}{<tekst>}
    \social{<pictogram>}{<URL>}{<tekst>}
  \end{socialnetwork}
  ```
  * Een andere pictogramstijl die gebruikt kan worden voor bijv. sociale
    netwerk pictogrammen van Academicons, maar die ook werkt voor FontAwesome
    pictogrammen.
  * `tekst` wordt de label van een link naar `URL`.
  * `tekst` kan zoals gewoonlijk worden opgemaakt via bijv. `\texttt{}` enz.

### Hoofdtekst

De rechterkolom van de CV met tabellen voor iets als "werkervaring" moet
gedefinieerd worden binnen de `document` omgeving.

* Sectie- en subsectie koppen
  ```latex
  \cvsection
  \cvsubsection
  ```

* CV-items moeten binnen `cvtable` worden geplaatst, onafhankelijk van het type.
  De mogelijkheden zijn:
  ```latex
  \begin{cvtable}[<arraystretch>=1]
    \cvitem{<data>}{<titel>}{<locatie>}{<omschrijving>}
    \cvitem{<data>}{<titel>}{<locatie>}{}
    \cvitemshort{<key>}{<omschrijving>}
    \cvpubitem{<titel>}{<auteur>}{<tijdschrift>}{<jaar>}
  \end{cvtable}
  ```
  * `cvitem` inclusief een omschrijving zal de titel vetgedrukt maken, de datum
    of data links uitlijnen, de locatie rechts uitlijnen en de omschrijving
    ingesprongen op de volgende regel zetten. De beschrijving zelf zal in
    `itemtextcolor` staan, zoals gedefinieerd in de
    [klasse opties](#klasse-opties).
  * Als `cvitem` een beschrijving mist, wordt er een item van één regel
    toegevoegd in de stijl hierboven omschreven, maar met een "normale" titel in
    plaats van vetgedrukt.
  * `cvitemshort` lijnt `<key>` linkt uit, gevolgd door de omschrijving.
  * `cvpubitem` voegt een item toe met links uitgelijnd jaar/datum, vetgedrukte
    titel op dezelfde regel, gevolgd door een cursieve gedrukte auteur naam, en
    normaal gedrukte tijdschrift, elk op een afzonderlijke regel.
  * `<arraystretch>` wijzigt de afstand tussen de items van `cvtable`. Voor
     tabellen van `cvitem` moet je minimaal 1.5 gebruiken, voor` cvitemshort` en
     `cvitem` zonder omschrijving is de standaardwaarde voldoende.

* Kleuren
  `cvsection`, `cvsubsection` en de tekst kleur van omschrijvingen kunnen
  worden gedefinieerd zoals omschreven in de [klasse opties](#klasse-opties).

* De combinatie van naam en functietitel met de juiste spatiëring, lettertype en
  kleur
  ```latex
  \nameandjob
  ```

* Het afronden van de CV met een plaats, datum en handtekening, zoals
  gebruikelijk in bijv. Duitsland wordt gedaan via
  ```latex
  \cvsignature
  ```

### Configuratie van het lettertype

* Wijzig het standaardlettertype door het bijbehorende pakket te laden, bijv.
  voor google noto
  ```latex
  \usepackage[sfdefault]{noto} % gebruik het google noto lettertype
  ```
  of door de optie van XeLaTeX te gebruiken om lokale lettertypen rechtstreeks
  in te laden via fontspec
  ```latex
  \usepackage[quiet]{fontspec}
  \newfontfamily\headingfont[Path = fonts/]{segoeuib.ttf}
  ```

* Voor meertalige documenten, raad ik het gebruik van van pdfLaTeX ten zeerste
  af. Omdat ik maar weinig ervaring heb met LuaLaTeX (maar ik zal waarschijnlijk
  wel binnenkort hiernaar overschakelen), kan ik voor nu alleen instructies
  geven voor XeLaTeX. Daar moet je eerst het `polyglossia` pakket inladen en
  vervolgens lettertypen instellen voor elke taal afzonderlijk. Voor documenten
  met Latijns schrift met bijv. enkele Arabische tekstfragmenten, gebruik dan
  ```latex
  \usepackage{polyglossia}
  \newfontfamily\arabicfont[Script=Arabic]{Amiri}
  \setdefaultlanguage{english}
  \setotherlanguage{arabic}
  % zet Arabische fragmenten in de hoofdtekst met één van
  \textarabic{...}
  \begin{Arabic}...\end{Arabic}
  ```
  terwijl u voor documenten met een niet-Latijns schrift iets kunt gebruiken als
  ```latex
  \usepackage{polyglossia}
  \setmainfont{Amiri}
  \newfontfamily\englishfont{Clear Sans}
  \setdefaultlanguage{arabic}
  \setotherlanguage{english}
  % zet Engelse fragmenten in de hoofdtekst met één van
  \textenglish{...}
  \begin{english}...\end{english}
  ```
  Voor Perzische talen (Farsi) zou het volgende moeten werken volgens
  [dit antwoord](https://tex.stackexchange.com/a/238245):
  ```latex
  \newfontfamily\farsifont[Script=Arabic,Scale=10,Contextuals=Swash]{IranNastaliq}
  ```
  Afhankelijk van welk lettertypestijl jouw standaard is, moet je
  `\arabicfontfs` (sans serif) gebruiken, of `\arabicfonttt` (monospace), in
  plaats van `\arabicfont`.

  OPMERKING: Als je een RTL-lettertype instelt als hoofdlettertype, worden ook
  andere delen van het CV automatisch omgedraaid. Hoewel dit voor de meeste
  onderdelen geen probleem lijkt te zijn voor zover ik kan zien (ik ben helemaal
  niet gewend aan RTL), breekt het wel een deel van de vaardigheid commando's,
  met name `\pointskill` en `\membership`, en leidt het tot enige problemen met
  de afstanden. Hoe dan ook, voor RTL wil je ook waarschijnlijk de
  `sidebarplacement=right` optie gebruiken.

* TODO: LuaLaTeX + babel-instellingen

* Je moet lettertypen zoals Amiri en Clear Sans handmatig installeren wanneer
  je ze via fontspec inlaadt. Dit is niet nodig voor documenten in één taal
  waar je eenvoudig van lettertype kunt wisselen, zoals in het eerste voorbeeld,
  door de respectievelijke LaTeX-pakketten te gebruiken.

* Als je op zoek bent naar een specifiek pictogram, bijvoorbeeld LinkedIn, moet
  je eerst in de [FontAwesome galerij](https://fontawesome.com/icons?d=gallery)
  naar de naam zoeken, bijv. `linkedin-in`, en vervolgens de bijbehorende
  LaTeX-code opzoeken in het
  [fontawesome5 pakket](https://ftp.gwdg.de/pub/ctan/fonts/fontawesome5/doc/fontawesome5.pdf),
  in dit geval '\faLinkedinIn'.

* Als je de regelafstand globaal wilt vergroten, gebruik je
  ```latex
  \usepackage{setspace}
  \setstretch{1.1}
  ```
  in plaats van de `arraystretch` modifier. Merk op dat dit ook van invloed is
  op de inhoud van de zijbalk.

* Als je de grootte van het basis lettertype wilt wijzigen, gebruik de opties
  van de 'artikel' klasse zoals `12pt`, voor alle elementen in het hoofd
  document en de paragrafen in de zijbalk. Koppen in de zijbalk kunnen worden
  aangepast via de `sidesectionsize` [klasse optie](#klasse-opties). Voor de
  lettergrootte van naam en functietitel moet je respectievelijke commando's
  opnieuw definiëren, zoals [hier](#zijbalk) uitgelegd.


## Voorbeeld

![](pics/template-0.jpg)
![](pics/template-1.jpg)
