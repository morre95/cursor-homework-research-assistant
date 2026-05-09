# HW-6: AI och energiförbrukning

# AI och energi: problemet är inte bara hur mycket el som används

## Inledning

Moderna AI-system kräver mycket el eftersom de bygger på enorma mängder datakraft. Stora språkmodeller tränas på mycket data, med många parametrar och tusentals eller tiotusentals GPU:er. Sen näör moidellen tas i bruk så fortsätter elförbrukningen. Min ståndpunkt är att AI:s elförbrukning kan vara försvarbar, men bara under vissa villkor: datacenter bör byggas där elen är fossilfri, företagen bör betala för den nätkapacitet de kräver, och delar av AI-arbetet bör kunna flyttas till tider och platser där elen är ren och billig.

## Vad är det som gör att AI kräver så mycket el

AI kräver el både vid träning och efter att den tagits i bruk. Träning är den stora engångskostnaden när modellen lär sig från stora datamängder. För en populär modell kan modellen få svara på miljontals eller miljarder frågor vilket kräver stora mängder energi. Scaling laws har också drivit utvecklingen: större modeller, mer data och mer beräkning har länge gett bättre resultat. Därför har företag fortsatt bygga större GPU-kluster. Problemet är att detta inte är gratis då det inte bara kräver GPU:er utan också kylning, elnät, vatten, mark och kapital.

Ett konkret exempel visar skillnaden mot biologisk intelligens. En GPU-server med 8 NVIDIA B200-GPU:er, till exempel en DGX B200, kan dra ungefär 14.3 kW vid maxlast. GPU:erna själva står för omkring 8 kW. Den mänskliga hjärnan använder ungefär 20 W. Det betyder inte att hjärnan och en AI-server gör samma sak, men jämförelsen visar hur energitung dagens digitala intelligens är. Precis som man gjorde i flygindustrin när man sprängde ljudvallen. Alltså att man använde sig av naturens krafter för att flyga snabbare och inte bara förlita sig på rå kraft så tror jag att man behöver hitta ett sätt att använda naturens krafter även här och inte bara förlita sig på den energi som vi kan tillverka. 

## Datacenter i Norden eller Mellanöstern

Miljöeffekten av ett datacenter beror mycket på var det byggs. Norden har flera fördelar: kallare klimat ger lägre kylbehov, elmixen är ofta fossilfri eller nästan fossilfri, och spillvärme kan ibland återanvändas i fjärrvärmesystem. Sverige, Norge och Finland har mycket vattenkraft, kärnkraft och vindkraft. Därför kan ett datacenter i Norden få lägre klimatpåverkan än ett datacenter i ett varmt område där elen i större utsträckning kommer från fossil gas.

Mellanöstern har också fördelar, särskilt mycket solenergi och stora investeringsmöjligheter. Men regionen har extrem värme, vilket ökar kylbehovet. Kylning kan dessutom kräva vatten, och i torra områden är vatten redan en btist vara. Och om vattnet måste komma från avsaltning krävs ännu mer energi. Därför är det inte självklart att solpaneler räcker för att göra ett datacenter hållbart. Man måste också räkna med kylning, vatten, material, reservkraft och nätanslutning.

## Hur mycket drar ett stort AI-datacenter?

Ett modernt större datacenter kan dra tiotals eller hundratals MW. De största AI-satsningarna planeras nu i GW-skala. 1 GW motsvarar 1000 MW och är ungefär samma storleksordning som en normal svensk kärnreaktor. Sveriges reaktorer ligger ungefär mellan 1.1 och 1.4 GW el per reaktor. Om ett AI-campus kräver 1 GW betyder det alltså nästan en hel reaktor. Ett projekt på 5 GW skulle motsvara flera svenska reaktorer. Därför är AI-datacenter inte bara en IT-fråga, utan också en energipolitisk och industriell fråga.

## Stabil el, volatil el och buffertar

Olika energislag fungerar olika i elnätet. Sol och vind är svåra att beräkna, eftersom de beror på väder och tid på dygnet. De är billiga och har låga utsläpp, men de skapar svängningar som måste balanseras. Kärnkraft är stabil och fossilfri, men fungerar bäst som planerbar baskraft snarare än snabb reglerkraft. Vattenkraft med magasin är särskilt värdefull eftersom den både är fossilfri och kan regleras snabbt. Fossil gas är också reglerbar och kan balansera vind och sol, men den ger stora CO2-utsläpp och bör därför inte vara huvudlösningen.

Datacenter skulle kunna öka andelen sol och vind om de blir mer flexibla. Alla AI-jobb är inte lika brådskande. Träning, batchjobb, videobearbetning och vissa bakgrundsuppgifter kan flyttas till timmar när det blåser mycket eller solen skiner. De kan också flyttas geografiskt mellan datacenter i olika elområden. Däremot är vanlig användning lite svårare att flytta då användaren oftast väntar på svar. Datacenter är därför beroende av elavtal, mjukvara och flexibla nätregler för att de ska vara lönsamma.

## Sverige exporterar el men säger ändå nej

Det äör lite motsägelse fullt att Sverige exporterar el samtidigt som företag får nej till att bygga datacenter på grund av elbrist. Detta beror inte bara på vilken årskapacitet eltillverkningen har utan snareare på effekt och kapacitet. Sverige exporterade cirka 33.4 TWh netto 2024, men tyvärr produceras inet alltid elen där den behövs och häller inte alltid vid rätt tidpunkt. Norra Sverige har ofta överskott, medan södra och mellersta Sverige kan ha kapacitetsproblem. Elnätet har flaskhalsar mellan elområden och lokala nät kan vara fulla medans andra kan har mycket kapacitet över.

Ett datacenter kräver dessutom garanterad effekt dygnet runt. Det räcker inte att Sverige i genomsnitt producerar mer el än landet använder. Om ett företag vill ansluta hundratals MW i ett område där nätet redan är ansträngt kan anslutningen ändå nekas. Här är något jag tycker datacenterföretag bör ta sitt ansvar i större utsträckning och betala för att förstärka upp nätet och gärna bidra med egen produktion eller flexibilitet.

## Datacenter i satelliter

Elon Musk har föreslagit datacenter i rymden, i form av satelliter. Tanken är att rymden erbjuder nästan konstant solenergi, inga markkonflikter och ingen vanlig elnätsbegränsning. Satelliter skulle kunna drivas av solpaneler och möjligen kyla bort värme genom att stråla ut den i rymden. Detta kasnke kan låter lockande eftersom energi och kylning är två av de största problemen för AI-datacenter på jorden.

Nackdelarna är ändå stora. Det är dyrt att skjuta upp hårdvara, svårt att reparera trasiga komponenter, och elektronik i rymden utsätts för strålning. Rymdskrot och kollisioner är också risker. Dessutom försvinner inte värmeproblemet bara för att systemet är i rymden. Eftersom vakum inte kan leda värme så behöver man strålas bort värmen med stora radiatorer. Latens och dataöverföring kan också bli problem. Därför ser satellitdatacenter mer ut som en möjlig framtidsidé än en lösning på AI:s energiproblem de närmaste åren.

## Risker, geopolitik och rättvisa

AI:s energifråga handlar inte bara om klimat. Den handlar också om geopolitik och rättvisa. De länder och företag som har tillgång till avancerade chip, billig el, mark, vatten och elnät får ett övertag. Det kan göra AI-utvecklingen mer koncentrerad till USA, Kina, Gulfstaterna och länder med stark energiinfrastruktur. Sverige och Norden kan bli attraktiva för hållbar AI, men bara om nätet byggs ut och om datacenter inte konkurrerar ut viktig elektrifiering av industri och transporter.

Frågan är också om AI:s elförbrukning är motiverad av produktivitetsvinsterna. Mitt svar är: ibland, men inte alltid. AI som hjälper forskning, medicin, programmering, utbildning, energieffektivisering eller industriplanering kan vara värd sin elförbrukning. Men AI som mest används för spam, övervakning eller reklam är svårare att försvara. Därför bör användarna och företagen som tjänar pengar på AI också betala miljökostnaden, till exempel genom elpriser, nätavgifter, krav på fossilfri el och rapportering av energiförbrukning.

## Dödsfall, utsläpp och framtida lösningar

När man jämför energislag bör man titta på verkligt utfall, inte bara känslor. Our World in Data visar att fossila bränslen orsakar mycket fler dödsfall per producerad TWh än kärnkraft och moderna förnybara energislag. Ungefärliga siffror är: kol 24.6 dödsfall/TWh, olja 18.4, gas 2.8, vattenkraft 1.3, vind 0.04, kärnkraft 0.03 och sol 0.02. Skillnaden beror framför allt på luftföroreningar från fossila bränslen.

CO2-bilden pekar åt samma håll. Kol ligger runt 820 gCO2e/kWh, olja runt 720 och gas runt 490. Vind, kärnkraft, vattenkraft och sol ligger mycket lägre över livscykeln, ungefär i storleksordningen 10-50 gCO2e/kWh. Det betyder att den viktigaste klimatfrågan inte är om AI använder el, utan vilken el den använder och vad den tränger undan.

Elbehovet kommer sannolikt att öka. IEA räknar med att datacenters elanvändning kan mer än fördubblas till 2030, samtidigt som elbilar, värmepumpar, elektrifierad industri och klimatanpassning också kräver mer el. De mest lovande lösningarna är därför en kombination: mer fossilfri produktion, utbyggda elnät, vattenkraft och batterier som flexibilitet, smartare datacenter, effektivare AI-modeller och tydligare krav på att AI-företag betalar för den kapacitet de använder.

## Avslutning

AI:s energiförbrukning är stor och kommer troligen att växa. Men slutsatsen bör inte vara att all AI är ohållbar. Den rimligare slutsatsen är att AI måste behandlas som tung industri. Den behöver fossilfri el, starka elnät, effektiv kylning, öppen rapportering och ekonomiskt ansvar. Datacenter i Norden kan vara bättre än datacenter i varma fossilberoende regioner, men bara om de byggs utan att skapa lokala elproblem. För mig är den bästa vägen framåt inte att stoppa AI, utan att göra energikraven synliga och styra utvecklingen mot mindre, effektivare och mer flexibla system.

