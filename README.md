# VG-uppgifterna
Då var det äntligen dags för vg-uppgifterna. Ni har jobbat med att importera, manipulera och visa upp data och det är nu dags att göra den sista kopplingen.
Det är nu dags att göra fakturorna!
## Uppgift 1
Fakturan skall vara ännu en modell i ditt system. En faktura skall:
1. Ha ett fakturadatum. Fakturadatumet är datumet då fakturan färdigställs.
2. Förfallodatum. Förfallodatum skall vara 30 dagar efter att fakturan färdigställts.
3. Ha ett kund-id. Varje faktura är kopplad till en kund.
4. Totalsumma utan moms.
5. Total moms för fakturan.
6. Total frakt utan moms.
7. Total moms för frakt.
8. Totalsumma för både frakt och beställningar inklusive moms.
9. En flagga för om fakturan är fakturerad eller inte.
10. Ett serienummer.
11. En eller flera ordrar/beställningar kopplade till sig.
Observera att du får ha fler kolumner på din faktura men dessa kolumner är obligatoriska.
## Uppgift 2
Serienummer i fakturavärlden är lite speciellt. Det finns bokföringsregler som gör att man inte kan göra som man vill utan dessa regler måste följas.
Dessa regler är:
1. En faktura måste vara del av en obruten serie. Det betyder att det inte får finnas några hopp i fakturanumrena utan serien måste gå 1,2,3 etc.
2. Det går däremot bra att ha flera olika serier och serien behöver inte börja på 1. Man kan tex börja på 1000.
För vår del så skall serienumret bestå av två delar, nämligen de sista två siffrorna av det nuvarande året följt av fyra siffror.
Första fakturan skall alltså ha serienumret 170001 om året är 2017. Nästa faktura skall ha serienumret 170002 osv.
När det blir 2018 så skall serien börja om på 180001.
## Uppgift 3
Nu är det dags att skriva konsollkommandon!
Börja med att göra ett kommando som bara skapar en faktura. En ny faktura har inga kopplingar och är nollad.
Ge kommandot signaturen invoice:create
## Uppgift 4
Gör ett kommando som kopplar ihop en faktura och en beställning.
Ge kommandot signaturen invoice:connect och låt den ta två argument.
Om jag skriver invoice:connect 1 1 så kopplar vi ihop fakturan med id 1 med beställningen med id 1.
## Uppgift 5
Skriv ett kommando som färdigställer en faktura.
Ge kommandot signaturen invoice:finish och låt den ta ett argument.
invoice:finish 1 skall då färdigställa fakturan med id 1.
När en faktura färdigställs så skall det hända ganska mycket saker.
1. Fakturadatum skall sättas till dagens datum.
2. Förfallodatum skall sättas till 30 dagar från dagens datum.
3. Totala summor för beställningar och frakt skall räknas ihop genom att gå igenom beställningarna och lägga ihop summorna från varje beställning.
4. Serienummer skall sättas. För att sätta serienumret så behöver du hämta ut det senaste serienumret och avgöra utifrån det vad nästa serienummer blir.