# DJAngoTask

Aloitin tehtävien tekemisen 26.2.2023 klo 13.22.

## a)

### Djangon ja kehitysympäristön asennus

uuden kehitysympäristön asennus ja luominen:

      sudo apt-get -y install virtualenv
      virtualenv --system-site-packages -p python3 env/
      source env/bin/activate

sitten luodaan requirements.txt -tiedosto

      micro requirements.txt
      
Tänne kirjoitin sisään "django"
![kuva](https://user-images.githubusercontent.com/105205141/221407705-ebae41e5-4340-43b7-8969-a34c1f51ab5b.png)

Tämän jälkeen asensin djangon

      pip install -r requirements.txt
      
### djangon käyttö klo 13.29

djangoon loin projektin ja käynnistin sen seuraavilla komennoilla:

      django-admin startproject seikkutest
      cd seikkutest
      ./manage.py runserver
      
![kuva](https://user-images.githubusercontent.com/105205141/221407856-75f9df76-7849-44f5-92ff-d651c8d0e13d.png)

sitten yhdistin kyseiseen IP-osoitteeseen:

![kuva](https://user-images.githubusercontent.com/105205141/221407902-160ca985-d706-473e-9e75-1e91740ce2af.png)

hankkiuduin eroon varoituksista komennoilla: 

        ./manage.py makemigrations
        ./manage.py migrate
        
Jonka jälkeen konsoli palautti tämän: 
![kuva](https://user-images.githubusercontent.com/105205141/221408035-32ee4a6c-5d21-47fa-b9e2-9db0adad2ca7.png)

Tämän jälkeen loin uuden superuserin:

      ./manage.py createsuperuser
      
Täytin username ja password kentät, muut jätin tyhjiksi.

Tämän jälkeen yhdistin admin-sivulle kirjoittamalla selaimeeni:

(IP-osoite)/admin/

![kuva](https://user-images.githubusercontent.com/105205141/221408218-07666e43-2d78-4d30-9f4f-da7c6abe0dc2.png)

kirjauduin sisään tekemilläni superuser tunnuksilla

## Tietokannan tekeminen 26.2.2023 klo 13.39

Loin djangoon uuden appin:

            ./manage.py startapp testapp

komennolla ls löydän uuden luomani appin "testapp". Lisään uuden appini projektini settings.py tiedostoon:

            cd seikkutest
            micro settings.py
            
![kuva](https://user-images.githubusercontent.com/105205141/221408960-00cad4b5-989f-4b25-9eca-e085551ee166.png)

siirryin testappiini ja avasin models.py tiedoston ja kirjoitin tiedostooni Users-mallin.

            cd ../
            cd testapp
            micro models.py
            
 ![kuva](https://user-images.githubusercontent.com/105205141/221409147-2379fcaf-b733-448d-b37e-ea46bf1786a3.png)
 
 
Tämän jälkeen päivitin tietokannat

![kuva](https://user-images.githubusercontent.com/105205141/221409199-e821d365-5ab8-453d-91b0-4da983cca29b.png)

Nähdäkseni uuden tietokannan testapp, joudun rekisteröimään tämän tietokannan.
Tämä tehdään siirtymällä admin.py tiedostoon, johon rekisteröinnin suoritin täten:

![kuva](https://user-images.githubusercontent.com/105205141/221409516-a5b70298-d172-429e-a4e3-d7214d5833b4.png)

Käynnistin uudelleen projektini ja kirjauduin admin-sivulle. Täällä minua odotti yllätys.

![kuva](https://user-images.githubusercontent.com/105205141/221409599-349f6f61-ded3-48d2-ac07-4869f85a9fa1.png)

Tauluni on tullut sinne näkyviin! Ainoa ongelma että se on älykkäästi laittanut s-kirjaimen taulun nimen perälle. Olisipa varmaan pitänyt tehdä yksikkömuodossa taulun nimi. Menenpäs siis korjaamaan tämän.


Muokkaan tiedoston testapp -nimen User-nimeksi pysyäkseni kärryillä kaikesta. saman teen settings.py tiedostoon sekä apps.py tiedostoon. 
Avasin sitten microlla models.py tiedostoni uudelleen ja muokkasin tekstin Users --> User
Tallensin ja poistuin

Törmäsin ongelmiin nimeämisen kanssa ja totesin kokeilla User nimisen muuttujan sijasta Product -nimellä. 
Muokkasin apps.py, settings.py, models.py ja admin.py sen mukaisesti, sekä tiedostoni nimen mv-komennolla

Tämän jälkeen migratesin uudelleen muutokset ja käynnistin palvelimen.

![kuva](https://user-images.githubusercontent.com/105205141/221410400-4c6df094-6b87-465f-8654-6793f2bb6de3.png)

Nyt taulu näyttää järkevältä.

Kun kokeilin luoda Add -painikkeella uuden esineen tauluun niin se tulostaa sen nimeksi:

![kuva](https://user-images.githubusercontent.com/105205141/221410493-34d0b39d-902f-4f11-bd45-ac85405286ea.png)

Tätä varten kävin avaamassa models.py tiedoston ja lisäsin seuraavan osan: 

![kuva](https://user-images.githubusercontent.com/105205141/221410567-ef1cb6b4-8392-4592-b269-a4a921a5632a.png)

sitten taas tein migrate komennot ja käynnistin uudelleen:

       ./manage.py makemigrations
       ./manage.py migrate
       ./manage.py runserver
       
kirjauduin taas admin sivulle ja katsoin taulua:

![kuva](https://user-images.githubusercontent.com/105205141/221410644-c4693d6d-1045-4542-86b2-bb56a886f362.png)

Ja nyt objektin nimi näkyy! Loistavaa. 
Lopetin tehtävän a) klo 14.32.

