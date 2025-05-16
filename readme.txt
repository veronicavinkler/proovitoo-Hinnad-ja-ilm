Proovitöö FE/BE kevad 2025

Luua Magento 2 keskkond koos Alokai OS (endine Vue Storefront) front-end lahendusega (Vue Storefront 2).
Eesmärk on hinnata kandidaatide infopädevust, oskust kiiresti omandada uusi tehnoloogiaid, kasutada tehisintellekti töö kiirendamiseks ning teha arendust versioonihalduse ja koostöö reegleid järgides. 
Töö käigus saab kandidaat hinnata kas antud tehnoloogiatega töötamine võiks neile sobida.


1. Ülesande esimene osa: Magneto + Alokai/Vue storefront (open source) install
Eesmärk: panna püsti toimiv Magento 2 keskkond koos Alokai front-endiga.
Tegevused:

  1. Paigalda Magento 2 ja Alokai (endise Vue Storefronti) arenduskeskkond.
Magneto 2 paigaldamiseks jälgiti juhiseid lehel: https://www.mageplaza.com/devdocs/how-install-magento-2-windows.html
Magneto 2 allalaadimiseks pidi tegema 4 sammu:
  *Esimene oli  XAMPP installimine Windows jaoks. XAMPP laadimise käigus leidsin, et php polnud lisatud enviromental variables path-ile, seega lisasin selle.
  *Teine samm oli Composer allalaadimine, mis oli valikuline, seega seda ma ei teinud.
  *Kolmas samm oli Magento 2 Pack allalaadimine.
  *Neljas samm oli Magento 2 installimine. Selleks pidi minema aadressile http://localhost/magento2 siis oli võimalik alustada installimise protsessiga. Esialgul aadressile minnes anti teade Unable to connect.

Vea eemaldamiseks sisestasin juhtnööride saamiseks ChatGPT-sse küsimuse: "Tere, üritasin installida Magento 2, selleks sisestasin brauserisse http://localhost/magento2, kuid sain vastuseks "Unable to connect", mis selleks põhjuseks võib olla, kas on alternatiive kuidas aadressile ligipääseda. Magneto2 asub arvutis aadressil C:\XAMPP\htdocs\magento2 (extractitud). Kas on võimalik, et olen laadimisel tähtsa sammu ka vahele jätnud?"
Vastuseks sain, et ilmselt on vea põhjuseks veebiserveri (Apache) mitte aktiivsus. Juhiste järgi avasin XAMPP Control Panel ja jooksin Apache mooduli. Sain vea teate: Error: Apache shutdown unexpectedly.
Kõigepealt kontrollisin GPT juhisel portide 80 ja 443 hõivatust cmd-s käskude: "netstat -ano | findstr :80" ja "netstat -ano | findstr :443" abil. Port 80 oli vaba ja 443 hõivatud. Lahenduseks läksin faili httpd-ssl.conf, ning rea Listen 443 tuli muuta "Listen 4443" (post oli vaja muuta).
Kuna viga ei olnud võimalik eemaldada pärast pikkasid dialooge ChatGPT ja Gemini AI-ga otsustasin kõik installitud eemaldada ja luua virtuaal masina VirtualBox kasutades OS Ubuntuga, kuna antud operatsioonisüsteemil on Magneto 2 ametlikult toetatud.
Kõigepealt oli vaja laadida dependecies: php, mysql (samuti ametlikult toetatud andmebaas), mysql extensions, composer. Need sai laetud terminali kaudu.

  2.Kasuta versioonihaldust: kogu töö peab olema GitHubis avalik repo (või  privaatne, kui ligipääs antakse hindajatele).
  3. Jaga commit'e väikesteks sammudeks. Iga commit peab kirjeldama täpselt tehtud muudatust.
  4. Eelista GitHubi töövoogu, kus iga suurem muudatus käib läbi pull request’i.
  5. Kasuta AI tööriista (nt ChatGPT või mõnda muud) abi paigalduse juures. Ole valmis jagama oma AI prompt’e ja põhjendama nende kasutamist.
  6. Lisapunkte annab: paned VUE Storefront 2-e suhtlema läbi vahevara elastic-ga. Custom API Endpoint (Middleware) - NUXT3 vms peal.

2. Back-End arendaja suund: Hinnad ja ilm
Eesmärk: luua Magento 2 moodul, mis:
  1. kasutab ilmateate API't,
  2. muudab tooteinfot Magento-s dünaamiliselt sõltuvalt ilmast (vali ise, soovitatav hind)

3. Versioonihaldus ja tehniline dokumentatsioon
  1. Kasuta GitHubi või mõnda muud Git-teenust.
  2. Hoia commit'e loogilises jaotuses.
  3. Lisa README fail, mis kirjeldab:
    3.1. kuidas lahendus tööle panna,
    3.2. millised AI prompt’id kasutati ja miks,
    3.3. kas esines probleeme ja kuidas neid lahendati.




