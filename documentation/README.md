# Janin linkkilaatikko

##Sovellus: https://afternoon-inlet-85980.herokuapp.com/
##Travis:  ![Travis status](https://api.travis-ci.org/jjanii/wepa.svg?branch=master) https://travis-ci.org/jjanii/wepa

### Idea 
Sovellukseni ideana on, että kuka tahansa voi luoda oman "linkkilaatikon" jonne voi lisätä talteen hyödyllisiä linkkejä esimerkiksi tärkeää opiskelumateriaalia. Jokaisen linkkilaatikon voi luoda vain kerran samalla nimellä. 

### Käyttöohje
Sovelluksen käyttö on hyvin yksinkertaista, etusivulla on ohjeet sovelluksen käyttöön. Oman linkkilaatikon luominen tapahtuu siirtymällä selaimella osoitteeseen https://afternoon-inlet-85980.herokuapp.com/linkki_laatikkosi_nimi , jolloin luodaan linkki_laatikkosi_nimi niminen linkkilaatikko. Linkkilaatikossa voit lisätä linkkejä, linkin lisääminen vaatii kuvauksen ja nimen antamisen linkille, sekä validin url osoitteen (alkaa http:// jne.). Linkkejä voi myös poistaa klikkaamalla linkin kuvauksen vieressä olevaa x nappia. Kuka tahansa voi ilmiantaa linkkilaatikon mikäli kokee sen sisällön asiattomaksi. Jokaisen linkkilaatikon voi ilmiantaa vain kerran, ja mikäli kyseinen laatikko on jo ilmiannettu, tulostetaan käyttäjälle viesti "Sivu on jo ilmiannettu".

### Tarkennuksia
Jokaisella linkkilaatikolla on myös oma vieraskirja, jonne vierailijat voivat jättää viestejä. Viestien ja nimimerkkien pituus on rajoitettu, joten pitkiä viestejä ei pysty lähettämään. Kommentit on järjestetty niin, että uusin on aina ylimpänä. Myös kommentoinnissa nimimerkki sekä kommentti ei voi olla tyhjä.

Koska oletuksena kaikki linkkilaatikot näkyvät etusivulla olevassa listassa, on jokainen linkkilaatikko mahdollista piilottaa etusivun listasta klikkaamalla linkkilaatikon sivulla olevaa piilota nappia. Sivun voi myös palauttaa näkyville klikkaamalla taas näytä nappia.

Sovelluksella on myös adminpaneeli, jossa admin näkee logit ja adminilla on mahdollisuus poistaa jokin tietty linkkilaatikko. Adminpaneelin pääsee käsiksi menemällä osoitteeseen https://afternoon-inlet-85980.herokuapp.com/admin ja kirjautumalla tunnuksilla admin:admin. Adminpaneelissa on erikseen myös sivut kaikille luoduille sivuille, jossa näkyy myös piilotetut sivut, sekä sivu ilmiannetuille sivuille, jotka voidaan poistaa suoraan adminpaneelin kautta.

### Tietokanta
Ohjelma käyttää 5 eri tietokantataulua

|   | Create  |  Read  | Update  |  Delete |
|---|---|---|---|---|
| [Sivu](https://github.com/jjanii/wepa/blob/master/src/main/java/wad/domain/Sivu.java)  |  x | x  |   | x  |
| [Linkki](https://github.com/jjanii/wepa/blob/master/src/main/java/wad/domain/Linkki.java)  | x  | x  |   | x  |
| [Kommentti](https://github.com/jjanii/wepa/blob/master/src/main/java/wad/domain/Kommentt.java)  | x  | x  |   |   |
| [Logi](https://github.com/jjanii/wepa/blob/master/src/main/java/wad/domain/Logi.java)  |  x | x  |   |   |
| [Ilmianto](https://github.com/jjanii/wepa/blob/master/src/main/java/wad/domain/Ilmianto.java)  | x  | x  |   | x  |

### Lisäyksiä
Sovellus on mielestäni kattava, ja toteutin kaikki ominaisuudet jotka itse koin tarpeellisiksi. Kuitenkin jatkokehitystä varten esimerkiksi tietyn ip-osoitteen estäminen häiriköinnin tms takia voisi olla suotavaa. Sivutus olisi myös yksi mahdollinen lisäys tulevaisuutta varten, varsinkin logeille koska ne saattavat kasvaa huomattavan kokoisiksi. Tällä hetkellä logit lisätään scrollattavaan elementtiin, joten sivun pituus ei kasva mikäli logien määrä kasvaa suureksi.

Myös jatkoa varten jokainen sivu voisi vaatia sivun luonnin yhteydessä tunnistautumisen, esimerkiksi pelkän salasanan asettamisen, jolloin vain sivun luoja pystyisi lisäämään/poistamaan linkkejä, sekä asettamaan sivun näkyville/piiloon etusivulta.
