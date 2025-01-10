# NetJava
const __dirname = path.dirname(new URL(import.meta.url).pathname);

const __dirname = path.dirname(new URL(import.meta.url).pathname); 
 ^^^^^ should be vvvvvv
const __dirname = fileURLToPath(new URL('.', import.meta.url))

1 POST /api/orders
Total Amount får summan av vad priset på ett item är, dvs endast kostnaden för ett item. Rätt lösning är att priset per item ska multipliceras med kvantiteten för att få rätt summa (item.price * item.quantity)
Det finns inget som sparar en order, därav förblir orders.json tom. WriteOrdersToFile bör skrivas om till __dirname. 
CreatedAt genererar felaktig tidsstämpel för lagd order, ändra detta till new LocalTimeDate().

2 GET /api/orders/:id 
Loggar ingenting

3 PATCH /orders/:id 
Endpoint bör ändras till PUT då den ändrar flera saker samtidigt.
Visar en timmas tidsfel 
Timeout kan plockas bort då det endast lägger till kompileringstid i onödan.

4 POST /orders/:id/process 
Onödigt att beräkna belopp när totalbelopp redan finns

5 POST /orders/:id/calculate 
Summan på calculate-funktionen blir felaktig. Loopen itererar 1000 gånger istället för items x quantity. 


6 GET /orders 
Använder ett query men är inte konfigurerad för att söka i fälten kund-ID och status. Istället är frågan inställd på standard, vilket betyder att den gör sökningar i ID-fältet.

7 PUT /orders/:id 
Bör vara en patch då den bara ändrar en grej 
Kommer alltid att kasta fel eftersom beställningar inte sparas 
Bör vara "Det finns inga beställningar"

8 POST /orders/bulk-process 
Fungerar inte då den är beroende av POST 1

9 POST /orders/link/:id 

10 POST /orders/:id/start-process 
Har ingen felhantering för null id param
POST går igenom oavsett om ID finns eller inte vilket är fel, då endpointen bör kräva att man har ett ID för att det ska fungera som tänkt. 

Hjälpfunktionen Calcuate
Bör iterera items.quantity istället för 10000
