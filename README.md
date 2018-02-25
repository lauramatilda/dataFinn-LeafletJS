# DEMO: [http://www.lauramatilda.com/dataFinn/](http://www.lauramatilda.com/dataFinn/)

# Lyhyesti projektista

Päätin tehdä saamani datan perusteella mahdollisimman kevyen ja intuitiivisen LeafletJS -kartan, jossa yhdistäisin saamaani dataa muista lähteistä keräämääni aineistoon. Tein vuokradatan perusteella päätelmän että se on vuodelta 2014, koska uusimpien kohteiden rakennusvuodet olivat tältä vuodelta. Jotta pystyin tuomaan aineiston rinnalle dataa myös muista lähteistä, tein vuokradatasta myös oletuksen että se pitää sisällään kaikki keräyshetkellä Vuokraovessa olevat avoimet kohteet.

Löysin aineistosta kaksi mahdollisesti kiinnostavaa näkökulmaa jota voisi visualisoida:
* Asuntokysyntä - vertailemalla kuinka monta asuntoa on listattu kutakin kuntaa kohden, suhteuttettuna kunnan asukaslukuun, ajattelin että olisi ehkä mahdollista nähdä trendejä asuntokysynnässä. Haasteena näin, että kysynnän – tai sen puutteen – syytä ei juurikaan saa selville. Onko kyse uuden rakentamisen puutteesta, vilkkaasta muutosta tms...
* Kohteiden omistajat - tutkin lyhyesti kohteiden vuokranantajien sivuja ja kokosin kuvan siitä mikä osa kunnan kohteista oli joko sijoitusyhtiön tai yksityishenkilön omistuksessa. Tavoitteenani oli tutkia oliko sijoitusyhtiöiden omistamilla kohteilla yhdenmukaisuutta muuttotrendien kanssa, esimerkiksi sijoittavatko yhtiöt vain kasvukeskuksiin? Mitään erityistä trendiä en kuitenkaan aineiston perusteella nähnyt, sillä monissa pienissäkin muuttotappiokunnissa oli merkittävän paljon sijoitusyhtiöiden kohteita. Jätin tästä pienestä tutkimuksesta pois kaikki kunnat joissa oli <10 kohdetta vuokraovessa. Jätin myös laskematta kohteet joiden omistajaa en saanut helposti selville. Kaikki data löytyy alla olevasta taulukosta "Asuntojenhintatiedot (Vuokraovi.com)."

Päätin visualisoida asuntokysynnän, koska ajattelin että siitä ehkä saisi irti jotakin kiinnostavaa, varsinkin jos sen yhdistäisi muuttovirtaan (kerron tästä tarkemmin alla). Halusin toteuttaa projektin kartalla, koska kuntien ja kohteiden vertailu tuntui siten varsin luontelvalta. Löysin mm. vanhan kuntarajakartan joka on käsittääkseni Plus-deskin tuottama vuodelta 2013, ja liitin sen LeafletJS-karttaan. Valitettavasti kuntarajat eivät nyt tässä tilanteessa taida sopia vuoden 2014-2015 kuntaliitosten kanssa yhteen, mutta tämän voisi korjata laatimalla uuden geojson kartan vuodelta 2014. Käytin ensin koko LeafletJS kartan Proj4Leaflet:in kautta saadakseni siihen EPSG:3067 -karttaprojektion, mutta päädyin kuitenkin käyttämään EPS:3006 -projektiota hiemän Suomen ylle käännettynä. Tein tämän, koska ajankäytöllisesti katsottuna näyttävin, kattavin ja työhön sopivin TMS-karttapalvelu löytyi Ruotsista.

Kartta on suunniteltu erityisesti mobiililaitteille, mutta se on myös testattu mahdollisimman monella muulla laitteella ja selaimella.

# Data/Lähteet:

* [Asuntojenhintatiedot (Vuokraovi.com)](https://docs.google.com/spreadsheets/d/17w4sWustD0ZeTeIXgyk5lFLFEhZ0Sb_2RESbG0zie6s/edit?usp=sharing), sisältää myös muuta keräämääni dataa, sekä tekemääni analyysiä.
* [Tilastokeskus: Vuoden 2014 keskiväkiluku](http://pxnet2.stat.fi/PXWeb/pxweb/fi/StatFin_Passiivi/StatFin_Passiivi__vrm__vaerak/statfinpas_vaerak_pxt_019_201400_fi.px/?rxid=1b16dd56-e6e8-450f-b281-f0b58ed20ed0)
* Vuoden 2013 kuntarajat GEOJSON: [datajournalismi.blogspot.fi](http://datajournalismi.blogspot.fi/2013/02/suomen-kuntarajat-2013-kml-formaatissa.html) http://datajournalismi.blogspot.fi/2013/02/suomen-kuntarajat-2013-kml-formaatissa.html ja [kuntakartta.org](http://kuntakartta.org/)
* [Leaflet](https://github.com/Leaflet/Leaflet)
* [Proj4Leaflet](https://github.com/kartena/Proj4Leaflet)

# Jatkoa

Olisi kiinnostavaa (ja aikomukseni oli) rakentaa versio jossa voisi vertailla asuntokysyntää kuntien muuttovirtaan. Esim: onko kunnassa A vähemmän "kysyntää" asunnoille, koska sieltä väestö muuttaa kuntiin B, C ja D? Tai kenties sinne muuttaa kunnista E ja F, mutta kunta/kaupunki rakentaa jatkuvasti uusia asuntoja kysynnän tarpeisiin? Tämän saisi esitettyä näyttävästi vaikkapa animoiduilla, kuntien välisillä viivoilla.

Käytin tehtävän tekemiseen noin 16 tuntia. Aika kävi viikonlopulla kuitenkin vähiin niin tämä jäi vain haaveeksi; koodissa on jo alkua tälle, kommentoitu vain piiloon koska tämä vaihe jäi kesken. Toteutin kuitenkin tästä [pienen GIF:in](http://www.lauramatilda.com/dataFinn/img/jatkoa.gif) joka toivottavasti esittelee idean kiitettävästi. Tätä jatkoa varten oleelliset lisäosat olisivat:

* [Tilastokeskus: Kuntien välinen muutto](http://pxnet2.stat.fi/PXWeb/pxweb/fi/StatFin/StatFin__vrm__muutl/statfin_muutl_pxt_003.px/?rxid=9aa4e5ab-b8b2-47e5-ae12-defc3ee56895)
* [Leaflet Canvas Flowmap Layer](https://github.com/jwasilgeo/Leaflet.Canvas-Flowmap-Layer)
