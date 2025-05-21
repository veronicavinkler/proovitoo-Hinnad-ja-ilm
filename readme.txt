Proovitöö FE/BE

Magneto 2 allalaadimiseks pidi tegema 4 sammu:
  *Esimene oli  XAMPP installimine Windows jaoks. XAMPP laadimise käigus leidsin, et php polnud lisatud enviromental variables path-ile, seega lisasin selle.
  *Teine samm oli Composer allalaadimine, mis oli valikuline, seega seda ma ei teinud.
  *Kolmas samm oli Magento 2 Pack allalaadimine.
  *Neljas samm oli Magento 2 installimine. Selleks pidi minema aadressile http://localhost/magento2 siis oli võimalik alustada installimise protsessiga. Esialgul aadressile minnes anti teade Unable to connect.

Vea eemaldamiseks sisestasin juhtnööride saamiseks ChatGPT-sse küsimuse: "Tere, üritasin installida Magento 2, selleks sisestasin brauserisse http://localhost/magento2, kuid sain vastuseks "Unable to connect", mis selleks põhjuseks võib olla, kas on alternatiive kuidas aadressile ligipääseda. Magneto2 asub arvutis aadressil C:\XAMPP\htdocs\magento2 (extractitud). Kas on võimalik, et olen laadimisel tähtsa sammu ka vahele jätnud?"
Vastuseks sain, et ilmselt on vea põhjuseks veebiserveri (Apache) mitte aktiivsus. Juhiste järgi avasin XAMPP Control Panel ja jooksin Apache mooduli. Sain vea teate: Error: Apache shutdown unexpectedly.
Kõigepealt kontrollisin GPT juhisel portide 80 ja 443 hõivatust cmd-s käskude: "netstat -ano | findstr :80" ja "netstat -ano | findstr :443" abil. Port 80 oli vaba ja 443 hõivatud. Lahenduseks läksin faili httpd-ssl.conf, ning rea Listen 443 tuli muuta "Listen 4443" (post oli vaja muuta).
Kuna viga ei olnud võimalik eemaldada pärast pikkasid dialooge ChatGPT ja Gemini AI-ga otsustasin kõik installitud eemaldada ja luua virtuaal masina VirtualBox kasutades OS Ubuntuga, kuna antud operatsioonisüsteemil on Magneto 2 officiali tagatud.
