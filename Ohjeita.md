## Työn aloitus

Tarkista, että psql toimii omalla koneella komennolla  
`psql`

Mikäli tarpeellista, käynnistä palvelin ensin, esimerkiksi jos käytit tsohan local-pg-skriptaa, täytyy avata yhteys komennolla  
`start-pg.sh`

Navigoi miniprojektin kansioon ja  
`git pull`

Jos projektiin on lisätty tauluja tai schema.sql on muuten muuttunut, lisää muutokset myös omaan tietokantaasi esim.  
`psql < src/schema.sql`

Siirry virtuaaliympäristöön, esimerkiksi komennolla  
`python3 -m poetry shell`  
Riippuen poetryn asennuksesta voi riittää  
`poetry shell`

Käynnistä sovellus  
`flask run`

Voit ensin joutua asettamaan polun appiin  
`export FLASK_APP=src/app.py`

### Puhdas aloitus

Jos on ollut ongelmia saada projektia toimimaan omalla koneella, voit kokeilla aloittaa puhtaalta pöydältä:

1. Poistu virtuaaliympäristöstä ja poista koko paikallinen projektikansio

2. Kloonaa se uudestaan haluamaasi paikkaan  
`git clone [ssh- tai html-osoite GitHubista] nimirepolle`  
Huomaa, että poetryn asennukset saattavat säilyä, jos kloonaat tasan samaan sijaintiin ja samalla nimellä kuin aiemmin, siksi on ehkä hyvä antaa uusi nimi.

3. Mene kansioon, siirry virtuaaliympäristöön

4. Asenna riippuvuudet  
`poetry install -E development`  
Jos tuosta tulee jotain herjaa, laita ensin  
`poetry update`  
ja kokeile uudestaan

5. Lisää omaan projektiisi .env (varmuuden vuoksi sekä juurikansioon että src-kansioon), jonka sisältö on  
> DATABASE_URL="postgresql+psycopg2://"
> SECRET_KEY="salainenavain"

6. Aseta polku ja käynnistä flask

## Pull Request -työtapa

Jos homma toimii, hyvä! Voit siirtyä työskentelemään

Kun aloitat työskentelyn tietyn uuden ominaisuuden parissa:  
`git checkout -b omanbranchinnimi`

Tee selkeitä committeja

Kun olet valmis näyttämään työsi tulokset muille, pushaa branchisi remoteen  
`git push origin omanbranchinnimi:julkinenbranchinnimi`

Käy GitHubissa tekemässä Pull Request, kerro siinä mitä uusi koodisi tekee

Huikkaa vielä Discordissa, että joku tulisi vilkaisemaan koodia

Tarkista, onko jollain muulla Pull Request, ja katselmoi, kommentoi, ja mahdollisesti hyväksy ja mergeä
