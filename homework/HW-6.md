# HW-6: AI och energiförbrukning

## Uppgift och krav

Diskutera energiförbrukning i samband med moderna AI-system. Texten ska bland annat ta upp datacenter i Norden jämfört med Mellanöstern, effektförbrukning i stora AI-datacenter, svensk kärnkraft, olika energislags stabilitet, datacenter som flexibel last, satellitdatacenter, svensk elbrist trots elexport, GPU-servrar, hjärnans energiförbrukning, dödsfall och CO2 per producerad TWh, framtida elbehov och möjliga lösningar. Minst hälften av de extra frågorna om AI:s compute-behov, träning/inferens, scaling laws, produktivitetsnytta, hållbarhet, geopolitik, effektivare modeller och vem som ska betala miljökostnaden ska också behandlas.

## Vald tes

AI:s elförbrukning kan vara försvarbar om datacenter byggs där elen är fossilfri, nätkostnader betalas av företagen och arbetslaster görs flexibla.

## Tidigare feedback

Ingen feedbackmapp hittades, så ingen tidigare lärarfeedback har använts.

## Research notes

- IEA uppskattar att datacenter använde ungefär 415 TWh el globalt 2024 och kan öka till ungefär 945 TWh 2030.
- Svenska reaktorer ligger ungefär kring 1.1-1.4 GW el per reaktor. Sveriges sex reaktorer har tillsammans cirka 7 GW installerad effekt.
- Ett större modernt datacenter kan ligga på hundratals MW, medan nya AI-projekt planeras i GW-skala. 1 GW är ungefär samma storleksordning som en normal svensk kärnreaktor.
- En NVIDIA DGX B200-server med 8 B200-GPU:er har ungefär 14.3 kW maximal systemeffekt.
- Den mänskliga hjärnan använder ungefär 20 W, och hårt tänkande ändrar inte förbrukningen dramatiskt.
- Our World in Data anger ungefär följande dödsfall per TWh: kol 24.6, olja 18.4, gas 2.8, vattenkraft 1.3, vind 0.04, kärnkraft 0.03 och sol 0.02.
- IPCC/Our World in Data anger ungefärliga livscykelutsläpp: kol cirka 820 gCO2e/kWh, olja cirka 720, gas cirka 490, sol cirka 48, vattenkraft cirka 24, kärnkraft cirka 12 och vind cirka 11.
- Sverige exporterade rekordmycket el 2024, cirka 33.4 TWh netto, men kan ändå ha lokala effekt- och nätkapacitetsproblem.

## Slutdraft

# AI och energi: problemet är inte bara hur mycket el som används

## Inledning

Moderna AI-system kräver mycket el eftersom de bygger på enorma mängder beräkningar. Stora språkmodeller tränas på mycket data, med många parametrar och tusentals eller tiotusentals GPU:er. Sedan fortsätter elförbrukningen när modellen används i praktiken, alltså vid inferens. Min ståndpunkt är att AI:s elförbrukning kan vara försvarbar, men bara under vissa villkor: datacenter bör byggas där elen är fossilfri, företagen bör betala för den nätkapacitet de kräver, och delar av AI-arbetet bör kunna flyttas till tider och platser där elen är ren och billig.

## Varför AI kräver så mycket el

AI kräver el både vid träning och inferens. Träning är den stora engångskostnaden när modellen lär sig från stora datamängder. Inferens är kostnaden varje gång någon använder modellen. För en populär modell kan inferensen i längden bli större än träningen, eftersom modellen svarar på miljontals eller miljarder frågor. Scaling laws har också drivit utvecklingen: större modeller, mer data och mer beräkning har länge gett bättre resultat. Därför har företag fortsatt bygga större GPU-kluster. Problemet är att förbättringarna inte är gratis. De kräver chip, kylning, elnät, vatten, mark och kapital.

Ett konkret exempel visar skillnaden mot biologisk intelligens. En GPU-server med 8 NVIDIA B200-GPU:er, till exempel en DGX B200, kan dra ungefär 14.3 kW vid maxlast. GPU:erna själva står för omkring 8 kW. Den mänskliga hjärnan använder ungefär 20 W. Det betyder inte att hjärnan och en AI-server gör samma sak, men jämförelsen visar hur energitung dagens digitala intelligens är.

## Datacenter i Norden eller Mellanöstern

Miljöeffekten av ett datacenter beror mycket på var det byggs. Norden har flera fördelar: kallare klimat ger lägre kylbehov, elmixen är ofta fossilfri eller nästan fossilfri, och spillvärme kan ibland återanvändas i fjärrvärmesystem. Sverige, Norge och Finland har mycket vattenkraft, kärnkraft och vindkraft. Därför kan ett datacenter i Norden få lägre klimatpåverkan än ett datacenter i ett varmt område där elen i större utsträckning kommer från fossil gas.

Mellanöstern har också fördelar, särskilt mycket solenergi och stora investeringsmöjligheter. Men regionen har extrem värme, vilket ökar kylbehovet. Kylning kan dessutom kräva vatten, och i torra områden är vatten redan en knapp resurs. Om vattnet måste komma från avsaltning krävs ännu mer energi. Därför är det inte självklart att billiga solpaneler räcker för att göra ett datacenter hållbart. Man måste också räkna med kylning, vatten, material, reservkraft och nätanslutning.

## Hur mycket drar ett stort AI-datacenter?

Ett modernt större datacenter kan dra tiotals eller hundratals MW. De största AI-satsningarna planeras nu i GW-skala. 1 GW motsvarar 1000 MW och är ungefär samma storleksordning som en normal svensk kärnreaktor. Sveriges reaktorer ligger ungefär mellan 1.1 och 1.4 GW el per reaktor. Om ett AI-campus kräver 1 GW betyder det alltså nästan en hel reaktor. Ett projekt på 5 GW skulle motsvara flera svenska reaktorer. Därför är AI-datacenter inte bara en IT-fråga, utan också en energipolitisk och industriell fråga.

## Stabil el, volatil el och buffertar

Olika energislag fungerar olika i elnätet. Sol och vind är volatila, eftersom de beror på väder och tid på dygnet. De är billiga och har låga utsläpp, men de skapar svängningar som måste balanseras. Kärnkraft är stabil och fossilfri, men fungerar bäst som planerbar baskraft snarare än snabb reglerkraft. Vattenkraft med magasin är särskilt värdefull eftersom den både är fossilfri och kan regleras snabbt. Fossil gas är också reglerbar och kan balansera vind och sol, men den ger stora CO2-utsläpp och bör därför inte vara huvudlösningen.

Datacenter kan faktiskt hjälpa till att öka andelen sol och vind om de blir mer flexibla. Alla AI-jobb är inte lika brådskande. Träning, batchjobb, videobearbetning och vissa bakgrundsuppgifter kan flyttas till timmar när det blåser mycket eller solen skiner. De kan också flyttas geografiskt mellan datacenter i olika elområden. Däremot är vanlig inferens, där användaren väntar på ett svar direkt, svårare att flytta. Datacenter är därför inte automatiskt en buffert, men de kan bli det om elavtal, mjukvara och nätregler gör flexibilitet lönsam.

## Sverige exporterar el men säger ändå nej

Det kan låta motsägelsefullt att Sverige exporterar el samtidigt som företag får nej till att bygga datacenter på grund av elbrist. Förklaringen är att elbrist ofta handlar om effekt och nätkapacitet, inte bara årsproduktion. Sverige exporterade cirka 33.4 TWh netto 2024, men elen produceras inte alltid där den behövs och inte alltid vid rätt tidpunkt. Norra Sverige har ofta överskott, medan södra och mellersta Sverige kan ha kapacitetsproblem. Elnätet har flaskhalsar mellan elområden och lokala nät kan vara fulla.

Ett datacenter kräver dessutom garanterad effekt dygnet runt. Det räcker inte att Sverige i genomsnitt producerar mer el än landet använder. Om ett företag vill ansluta hundratals MW i ett område där nätet redan är ansträngt kan anslutningen ändå nekas. Detta visar varför datacenterföretag bör betala för nätförstärkningar och gärna bidra med egen produktion eller flexibilitet.

## Datacenter i satelliter

Elon Musk har föreslagit datacenter i rymden, i form av satelliter. Tanken är att rymden erbjuder nästan konstant solenergi, inga markkonflikter och ingen vanlig elnätsbegränsning. Satelliter skulle kunna drivas av solpaneler och möjligen kyla bort värme genom att stråla ut den i rymden. Det låter lockande eftersom energi och kylning är två av de största problemen för AI-datacenter på jorden.

Nackdelarna är ändå stora. Det är dyrt att skjuta upp hårdvara, svårt att reparera trasiga komponenter, och elektronik i rymden utsätts för strålning. Rymdskrot och kollisioner är också risker. Dessutom försvinner inte värmeproblemet bara för att systemet är i rymden: värme måste strålas bort med stora radiatorer. Latens och dataöverföring kan också bli problem. Därför ser satellitdatacenter mer ut som en möjlig framtidsidé än en lösning på AI:s energiproblem de närmaste åren.

## Risker, geopolitik och rättvisa

AI:s energifråga handlar inte bara om klimat. Den handlar också om geopolitik och rättvisa. De länder och företag som har tillgång till avancerade chip, billig el, mark, vatten och elnät får ett övertag. Det kan göra AI-utvecklingen mer koncentrerad till USA, Kina, Gulfstaterna och länder med stark energiinfrastruktur. Sverige och Norden kan bli attraktiva för hållbar AI, men bara om nätet byggs ut och om datacenter inte konkurrerar ut viktig elektrifiering av industri och transporter.

Frågan är också om AI:s elförbrukning är motiverad av produktivitetsvinsterna. Mitt svar är: ibland, men inte alltid. AI som hjälper forskning, medicin, programmering, utbildning, energieffektivisering eller industriplanering kan vara värd sin elförbrukning. Men AI som mest används för spam, övervakning, lågkvalitativ reklam eller onödig massgenerering är svårare att försvara. Därför bör användarna och företagen som tjänar pengar på AI också betala miljökostnaden, till exempel genom elpriser, nätavgifter, krav på fossilfri el och rapportering av energiförbrukning.

## Dödsfall, utsläpp och framtida lösningar

När man jämför energislag bör man titta på verkligt utfall, inte bara känslor. Our World in Data visar att fossila bränslen orsakar mycket fler dödsfall per producerad TWh än kärnkraft och moderna förnybara energislag. Ungefärliga siffror är: kol 24.6 dödsfall/TWh, olja 18.4, gas 2.8, vattenkraft 1.3, vind 0.04, kärnkraft 0.03 och sol 0.02. Skillnaden beror framför allt på luftföroreningar från fossila bränslen.

CO2-bilden pekar åt samma håll. Kol ligger runt 820 gCO2e/kWh, olja runt 720 och gas runt 490. Vind, kärnkraft, vattenkraft och sol ligger mycket lägre över livscykeln, ungefär i storleksordningen 10-50 gCO2e/kWh. Det betyder att den viktigaste klimatfrågan inte är om AI använder el, utan vilken el den använder och vad den tränger undan.

Elbehovet kommer sannolikt att öka. IEA räknar med att datacenters elanvändning kan mer än fördubblas till 2030, samtidigt som elbilar, värmepumpar, elektrifierad industri och klimatanpassning också kräver mer el. De mest lovande lösningarna är därför en kombination: mer fossilfri produktion, utbyggda elnät, vattenkraft och batterier som flexibilitet, smartare datacenter, effektivare AI-modeller och tydligare krav på att AI-företag betalar för den kapacitet de använder.

## Avslutning

AI:s energiförbrukning är stor och kommer troligen att växa. Men slutsatsen bör inte vara att all AI är ohållbar. Den rimligare slutsatsen är att AI måste behandlas som tung industri. Den behöver fossilfri el, starka elnät, effektiv kylning, öppen rapportering och ekonomiskt ansvar. Datacenter i Norden kan vara bättre än datacenter i varma fossilberoende regioner, men bara om de byggs utan att skapa lokala elproblem. För mig är den bästa vägen framåt inte att stoppa AI, utan att göra energikraven synliga och styra utvecklingen mot mindre, effektivare och mer flexibla system.

## Referenser

International Energy Agency. (2025). *Energy and AI*. https://www.iea.org/reports/energy-and-ai

International Energy Agency. (2025). *Electricity 2025 / Electricity 2026*. https://www.iea.org/reports/electricity-2025

Our World in Data. (n.d.). *What are the safest and cleanest sources of energy?* https://ourworldindata.org/safest-sources-of-energy

Intergovernmental Panel on Climate Change. (2014). *Climate Change 2014: Mitigation of Climate Change, Annex III*. https://www.ipcc.ch/report/ar5/wg3/

NVIDIA. (2024). *NVIDIA DGX B200 User Guide*. https://docs.nvidia.com/dgx/dgxb200-user-guide/

Svenska kraftnät. (2024). *Grid development plan 2024-2033*. https://www.svk.se/

Svenska kraftnät. (2025). *Sveriges nettoexport av el minskar*. https://www.svk.se/

World Nuclear Association. (2025). *Nuclear reactor database: Sweden*. https://world-nuclear.org/nuclear-reactor-database/summary/Sweden

Google. (2020). *We now do more computing where there is cleaner energy*. https://blog.google/outreach-initiatives/sustainability/carbon-aware-computing-location/

## Checklista

- Besvarar miljöeffekter av datacenter i Norden jämfört med Mellanöstern.
- Jämför stort AI-datacenter med svensk kärnreaktor.
- Förklarar volatila, stabila och buffrande energislag.
- Diskuterar om datacenter kan hjälpa vind och sol genom flexibilitet.
- Tar upp satellitdatacenter och deras för- och nackdelar.
- Förklarar svensk elexport samtidigt som anslutningar kan nekas.
- Jämför 8x B200-server med hjärnans energiförbrukning.
- Tar upp dödsfall/TWh, CO2-utsläpp och framtida elbehov.
- Behandlar flera extra teman: compute-behov, träning/inferens, scaling laws, produktivitetsnytta, hållbarhet, geopolitik, effektivare modeller och vem som bör betala miljökostnaden.
