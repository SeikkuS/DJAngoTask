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




