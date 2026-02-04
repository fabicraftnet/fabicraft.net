---
title: Rakennusten suojaus
description: Rakennusten suojaaminen
---

Omat rakennelmat kannattaa aina suojata, jotta muut pelaajat eivät pääse tuhoamaan niitä.
Suojaaminen onnistuu tonttien avulla.

Pelaajalla on alussa **100 tonttipalikkaa**.
Tonttipalikoita saa lisää pelaamalla FabiCraftin survivalissa (100 per tunti). Vapaiden tonttipalikoiden määrä voi tarkkailla komennolla `/claimblocks`.

## Tontin luonti

Oman tontin luominen onnistuu oikeaklikkaamalla kultalapiolla suojattavan alueen kahta vastakkaista kulmaa.

Aloita klikkaamalla kultalapiolla ensimmäistä kulmaa, jonka jälkeen kulma muuttuu timanttipalikaksi.

![claim-creation-1](../../../assets/docs/survival/protection/claim-creation-1.png)

Tämän jälkeen klikkaa vastakkaista kulmaa.
Tontin rajat ilmestyvät nyt näkyviin merkaten, että tontti on luotu.

![claim-creation-2](../../../assets/docs/survival/protection/claim-creation-2.png)

Tontin voi myös luoda komennolla `/claim <säde>`, kun kultalapio on kädessä. 

## Tontin koon muokkaus

Tontin kokoa on mahdollista muuttaa myös jälkikäteen.
Tämä onnistuu myös kultalapiota käyttämällä.

Voit käyttää tikkua hahmottaaksesi missä tontti on.
Kun oikeaklikkaat tikulla kohti tonttia, näyttää se tontin rajat.
Voit myös mennä kyykkyyn klikatessasi, jolloin tikku näyttää kaikki lähellä olevat tontit.

![claim-resize-1](../../../assets/docs/survival/protection/claim-resize-1.png)

Ota kultalapio käyteen ja klikkaa tontin kulmaa, jonka paikkaa haluat vaihtaa.
Chattiin tuleva viesti kertoo muokkaavasi tontin kokoa.

![claim-resize-2](../../../assets/docs/survival/protection/claim-resize-2.png)

Seuraavaksi klikkaa palikkaa, johon haluat kulman siirtyvän. Valmis :)

![claim-resize-3](../../../assets/docs/survival/protection/claim-resize-3.png)

:::note
Kulmaa siirrettäessä kultalapion täytyy olla koko ajan kädessä tai valinta nollaantuu.
:::

Tontin laajentaminen katsottuun suuntaan onnistuu myös komennolla `/extendclaim <määrä>`.

## Tonttien poisto

Voit poistaa tontin seisomalla sen sisällä ja kirjoittamalla komennon `/abandonclaim`.
Mikäli haluat poistaa kaikki tonttisi, voit tehdä sen kirjoittamalla `/abandonallclaims`.

:::note
Omistettujen tonttien listan näkee komennolla `/claimslist`.
:::
## Oikeuksien jakaminen

Koska rakennuksesi on nyt suojattu muilta pelaajilta, vain sinä voit rakentaa siellä.
Muille pelaajille voi kuitenkin jakaa eritasoisia oikeuksia, jotka oikeuttavat heitä tekemään tiettyjä asioita tontillasi.

Alla listattuna kyseiset oikeudet:

| Oikeus | Kuvaus | Komento |
| --- | --- | --- |
| Hallinnointi | Antaa oikeuden hallita tontin asetuksia ja luoda alitontteja | `/permissiontrust <pelaaja>` |
| Rakentaja | Antaa oikeuden rakentaa tontilla | `/trust <pelaaja>` |
| Varastonhoitaja | Antaa oikeuden avata arkkuja ja muita tavaralaatikoita | `/containertrust <pelaaja>` |
| Pääsy | Antaa oikeuden käyttää ovia, nappuloita, vipuja yms. | `/accessortrust <pelaaja>` |

Saat poistettua pelaajalta oikeudet komennolla `/untrust <pelaaja>`.

:::note 
Voit määrittää kaikkien pelaajien oikeuksia pistämällä `#public` aikaisempien komentojen `<pelaaja>` kohtaan.
:::

## Alitontit

Tonttien sisälle on mahdollista luoda alitontteja, joiden avulla pelaajaoikeuksien säätäminen voidaan tehdä vielä tarkemmin.
Esim. Haluat luoda farmin, jota kaikki pelaajat voivat käyttää.

Alitonttien luonti toimii samalla tavalla kuin tavallisten tonttien luonti: kultalapion avulla.
Luotu alitontti tulee näkyviin tontin sisälle rautapalikoilla.

![subclaims-1](../../../assets/docs/survival/protection/subclaims-1.png)

Alitontteja luodaksesi tulee sinun ottaa käyttöön alitonttitila komennolla `/subdivideclaims`.

![subclaims-2](../../../assets/docs/survival/protection/subclaims-2.png)

Esim. Pelaajan tarvitsee päästä käsiksi vain muutamaan arkkuun tontin sisällä, mutta tontilla on myös muita arkkuja joihin he eivät saa koskea.
Voit tällöin luoda alitontin, jonka sisälle voit antaa oikeudet arkkujen avaamiseen (containertrust), jolloin muut tontin arkut jäävät silti suojatuksi.

Oletuksena, tontin oikeudet siirtyvät sen sisällä oleviin alitontteihin. Tämän saa vaihdettua seisomalla alatontin sisällä ja käyttämällä komentoa `/restrictclaim`.

Pääset takaisin tavalliseen tonttitilaan kirjoittamalla komennon `/claim`.

![subclaims-3](../../../assets/docs/survival/protection/subclaims-3.png)


## Ryhmät

Sen sijaan, että määrittää jokaisen pelaajan oikeudet yksitellen jokaiselle tontille, voit luoda ryhmiä joille voi määrittää oikeudet. Ryhmät ovat pelaaja kohteisia, mutta hallinointi oikeudelliset voivat nähdä ja käyttää tontin omistajan ryhmiä oikeuksien antamisessa.

Pelaajia saa lisättyä ryhmään komennolla `/group <ryhmä> add <pelaaja1> <pelaaja2>`. Komennolla saa lisättyä yhden tai useamman pelaajan kerralla. Jos ryhmää ei ole olemassa, se luodaan automaattisesti.

Ryhmän jäseniä saa tarkkailtua komennolla `/group <ryhmä>`.

Jäseniä saa poistettua komennolla `/group <ryhmä> remove <pelaaja>`. Samalla tavalla kuin lisätessä, voit poistaa yhden tai useamman jäsenen kerralla.

Ryhmän saa poistettua komennolla `/group <ryhmä> delete`.

Ryhmiä saa käytettyä kaikissa oikeus komennoissa korvaamalla `<pelaaja>` kohdan ryhmällä  `@<ryhmä>` muodossa.

Esim. `/accessortrust  @<ryhmä>`

Tontin oikeudellisia ryhmiä ja pelaajia saa tutkittua komennolla `/claiminfo`.


## Porttikiellot
Voit estää pelaajien tulemista tontille komenolla `/claimprivate`. Tällöin vain pelaajat joille on myönnetty oikeuksia voivat astua tontille.

vaihtoehtoisesti voit antaa tietylle pelaajatte porttikiellon komennolla `/claimban ban <pelaaja>`. Porttikiellon saaneet pelaajat näkyvät komennolla `/claimban list`. Pelaajia saa päästettyä takaisin tontille komennolla `/claimban unban <pelaaja>`.