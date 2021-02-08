# Certiport-testikeskuksen pystyttäminen

Tämä ohjeistus neuvoo, miten testikeskus otetaan käyttöön _1+n_ työasemalla, joista yksi toimii testikeskuksen serverinä ja loput _n_ työasemaa testikoneina. Huomaa, että serverillä ei voi suorittaa testejä.

Ennen testikeskuksen pystyttämistä kannattaa tutustua testikeskuksen tilavaatimuksiin, jotka löydät osoitteesta https://certiport.pearsonvue.com/Educator-resources/Exam-policies/Administration. 

## Etukäteisvalmistelut

Ajan säästämiseksi varmista, että sinulla on saatavilla seuraavat asiat ennen asennusprosessiin ryhtymistä.

 * Vähintään Organization Member -tason oikeudet Certiport-palveluun, jotta saat ladattua Compass-sovelluksen.

 * Pöytäkoneet tai kannettavat, jotka täyttävät Compass-sovelluksen vaatimukset. Laitteistovaatimukset löydät osoitteesta https://certiport.pearsonvue.com/Support/Technical-requirements.aspx. Huomaa, että MOS-testit asettavat lisävaatimuksia perusvaatimustason lisäksi. Jos laitteissa on esiasennettu Windows, niin sen tulee olla englanninkielinen, amerikkalaisilla alueasetuksilla. Näppäimistöasettelu voi olla suomalainen.
 
 * Windowsin pääkäyttäjän tunnukset, jotta pääset asentamaan ja käyttämään Compass-sovellusta. 

## Windows

 Compass-sovelluksen toiminnan kannalta on tärkeää, että kaikki testissä käytettävät ohjelmat (käyttöjärjestelmä, Compass, Office) on asennettu samalla kielellä. Kokeet ovat englanniksi, joten kaikki ohjelmat asennetaan englanninkielisinä Windowsia myöten.

 * Mahdollisimman uusi 64-bittinen versio, editiolla ei ole merkitystä. Education-version aktivointiavaimet saa tarvittaessa tietohallinnolta.

 * Tarvitset pääkäyttäjätunnukset Compass-ohjelman asentamiseen. Nämä tunnukset syötetään myös Compass-ohjelmaan, jolla Compassille annetaan pääkäyttäjän oikeudet.

 * Asennusvaiheen valinnat:
     - Language to install: _English (United States)_
     - Time and currency format: _English (United States)_
     - Keyboard and input method: _Finnish_
     - Region: _United States_
     - Keyboard layout: _Finnish_
     - lisäkilkkeet voi jättää määrittelemättä

 * Määrittele Suomen aikavyöhyke: _Region Settings_ > _Date & Time_ > _Time zone: (UTC+02:00) Helsinki, ..._ Älä muuta päivämäärän tai kellonajan esitysmuotoa.

 * Jos kone luodaan suljettuun ympäristöön (esim. labraan) ja koneessa on paikallinen pääkäyttäjä, niin luo koneelle myös tavallinen käyttäjä, jossa Compass-ohjelmaa käytetään. Labraympäristössä pääkäyttäjäksi luotiin Pääjehu ja tavalliseksi käyttäjäksi Kokelas. Kokelas-käyttäjälle ei määritelty salasanaa.

 * Koneen nimi kannattaa nimetä järkevästi ja niin, että työasema on tunnistettavissa, esimerkiksi _HAYO-LABRA18-1_. Koneen nimi näkyy testien suorituslistoissa.

 * Koneen verkkoasetukset:
    - HAYO:n labrassa käytössä staattiset verkko-osoitteet, myös DHCP-asetukset toimivat. Helpointa, jos serveri on staattisilla asetuksilla.
    - Esimerkkinä labran verkkoasetukset:
      - IP-osoite: 10.84.0.70 (server) ja 10.84.0.71-74 (clientit)
      - Subnet mask: 255.255.255.0
      - Gateway: 10.84.0.1
      - DNS: 10.84.0.4
    - Palomuuriasetuksiin ei tarvitse tehdä muutoksia, paitsi palvelimen osalta (tästä tarkemmat ohjeet myöhemmin).

 * Acrobat Reader, asenna englanninkielinen versio (https://get.adobe.com/reader).

 * Koneessa pitää olla tulostin, Microsoft XPS Document Printer riittää.

 ## Office O365 Apps

  * Asenna englanninkielinen O365 Apps:
     - Kirjaudu portal.office.com-ympäristöön omilla tunnuksillasi.
     - Valitse Asenna Office > Muut asennusasetukset > Näytä sovellukset ja laitteet.
     - Valitse kieleksi _English (United States)_, versioksi _64-bittinen_ ja klikkaa Asenna Office.
     - Asenna Office suoritamalla ladattu tiedosto.

 * Määrittele Officen versio Compassin kanssa toimivaksi.
     - Löydät lisätietoa dokumentista https://certiport.pearsonvue.com/Support/PDFs/QRG-Office-365-FAQ.pdf.
     - Käynnistä komentorivi pääkäyttäjän oikeuksilla.
     - Syötä komentoriville sitä Office-versiota vastaavat komennot, johon haluat O365-version lukita. Komennot löydät dokumentista https://certiport.pearsonvue.com/Support/PDFs/MOS-365-Versioning-Three.pdf.

 * Avaa jokainen testattava sovellus (Word, Excel, PowerPoint ja Access) niin pitkälle, että pääset tyhjään työpohjaan, johon voisi lähteä tekemään omia lisäyksiä. Tämä varmistaa sen, että nämä ohjelmat eivät kysele mitään ylimääräisiä aloitukseen liittyviä asioita testin alussa. Tämä läpikäynti kannattaa tehdä myös aika ajoin.

 * Office-ohjelmia ei tarvitse aktivoida, Compass toimii ilman aktoivoimista.

 * Office-pakettia ei tarvitse asentaa Serverille, koska siinä ei voi suorittaa testejä.

 ## Compass Server

 * Lataa Compass ja asenna se englanninkielisenä oletushakemistoon. Compassin saa ladattua Certiportin palvelusta, kun olet kirjautunut ja roolina on _Organization Member_. Sovellus löytyy kohdasta _TRAINING & TOOLS_ > _Compass_.

 * Käynnistä Compass ja kirjaudu sisään Certiportin tunnuksillasi. Compass menee ensimmäisellä käynnistyskerralla asetusikkunaan, määritä serverille seuraavat asetukset:

   - Server-kohtaan valitse _Production Server_ (ei ole muita vaihtoehtoja), tämä valinta ei määrittele testikoneen roolia, vaan Certiportissa käytettävää ympäristöä.
   - Certiport ID: _SASKY KOULUTUSKUNTAYHTYMÄ (xxxxxxxx)_
   - Language: _English_
   - Admin Credentials
       - Syötä tähän käyttäjätunnus ja salasana, joilla on pääkäyttäjäoikeudet.
       - Älä muuta pääkäyttäjän salasanaa Windowsin puolella tämän jälkeen, tämä todennäköisesti estää Compass sovelluksen käynnistymisen jatkossa.
   - LAN Settings
       - _Compass Server_
       - Server Address: koneen IP-osoite (esimerkissä 10.84.0.70)
       - Server Port: _52525_
   - Update Frequency
       - Jätä oletus eli _Daily_
   - Proxy
       - Älä määrittele, jos ei ole pakko. Proxyn käyttö tuo aika paljon lisää muuttujia matkaan.

   - Kun tallennat edellä määritellyt asetukset, Compass sovellus käynnistyy todennäköisesti uudelleen ja pyytää sinua kirjautumaan uudelleen sisälle.
 
 * Lataa testikeskuksessa tarjottavat testit:
    - Mene kohtaan _Manage Exams_ ja valitse _Download Additional Exams_
    - Valitse ladattavat testit. Huomaa, että Microsoft Office Specialist -kategorian alla on useamman Office version testit, selkeyden vuoksi kannattaa valita ainoastaan uusimman version testit.
    - Valitse _Download Exams_ ja odota testien lataaminen.

 * Avaa portti palomuuriin:
    - Avaa Windows _Defender Firewall_ ja sieltä _Advanced Settings_.
    - Aktivoi _Inbound Rules_.
    - Valitse _New Rule..._
    - Rule Type -kohdassa valitse tyypiksi _Port_.
    - Protocol and Ports -kohdassa valitse protokollaksi _TCP_ ja syötä portiksi _52525_.
    - Action-kohdassa valitse _Allow the connection_.
    - Profile-kohdassa voit jättää valinnan kaikkiin kolmeen vaihtoehtoon (Domain, Private ja Public).
    - Name-kohtaan anna säännön nimeksi kuvaava nimi, esimerkiksi _Compass Server_.

## Compass Client

 * Lataa Compass ja asenna se englanninkielisenä oletushakemistoon. 

 * Käynnistä Compass ja kirjaudu sisään Certiportin tunnuksillasi. Compass menee ensimmäisellä käynnistyskerralla asetusikkunaan, määritä samat asetukset kuin palvelimelle, paitsi LAN Settings-kohta. 

   - LAN Settings
     - _Compass Client_
     - Server Address: serverikoneen ip (esimerkissä 10.84.0.70)
     - Server Port: _52525_
 
 * Käynnistymisen yhteydessä Compass tarkistaa löytyykö serveriltä uusia testejä ja lataa ne tarvittaessa. Serverin tulee olla siis päällä!

 * Tarkista, että asennettu Office on yhteensopiva Compass-sovelluksen kanssa menemällä kohtaan _Office Compatibility_. Ruudun tiedot kertovat, mikä versio Officesta on asennettu ja onko se yhteensopiva.

 * Tarkista LITA-testien (Live-in-the-application)toiminta:
    - Mene kohtaan _Manage Exams_
    - Suorita _Launch Config Exam_ kunkin Office-ohjelman osalta.
    - Config-testien tarkoituksena on testata, että Compass saa avattua testeissä tarvittavat Office-ohjelmat oikein ja testien suoritus onnistuu ongelmitta. Suorita koetestit noudattamalla ohjeita. Testissä olevaa tehtävää ei ole pakko suorittaa.

## Testikerran valmistelut

Testikerta kannattaa aloittaa seuraavasti:

 * Kertaa testivalvojan pikaohje, joka löytyy osoitteesta https://certiport.pearsonvue.com/Support/PDFs/QRG-Proctoring.

 * Testaajille suunnatut tutoriaalit testeihin löydät osoitteesta https://certiport.pearsonvue.com/Educator-resources/Exam-details/Exam-tutorials. Muun muassa MOS-testeihin löytyy lyhyt esittelyvideo, joka kuvaa testin toimintaa.

 * Käynnistä ensin Compass Server ja varmista, että serveri saa kaikki tarvittavat päivitykset ladattua. Käynnistä vasta tämän jälkeen Compass Client -koneet. Valvojan on hyvä käynnistää Compass-sovellukset, jotta tulee varmistettua, että Compass käynnistetään pääkäyttäjän oikeuksilla valitsemalla oikeuksien varmistusikkunasta _Yes_.

 * Jos otat vastaan MOS-testejä, niin testaa toimiiko testissä käytettävän Office-sovelluksen Config Exam -testi. Tällä varmistat, ettei testin suoritus kaadu ilmeiseen yhteensopivuusongelmaan.

## Hyödyllisiä linkkejä

 * [Become a Certiport Authorized Testing Center (CATC)](https://certiport.pearsonvue.com/Educator-resources/Get-started)

 * [Getting Started FAQ for New CATCs](https://certiport.pearsonvue.com/Support/PDFs/QRG-Getting-Started-FAQ-for-New-CATCs.pdf)

 * [Top 10 checks for the testing season](https://certiport.pearsonvue.com/CATCs/Top-10-checks-for-the-testing-session)

 * [Compass User Guide (Windows)](https://certiport.pearsonvue.com/Support/PDFs/Compass/Compass-User-Guide-Windows.pdf)

 * [Quick Reference Guides](https://certiport.pearsonvue.com/Support/Quick-reference-guides)

 * [Frequently asked questions (FAQs)](https://certiport.pearsonvue.com/Support/Support-for-CATCs/FAQs.aspx)

 * [Frequently Asked Questions - Certiadria](https://certiadria.com/frequently-asked-questions/)