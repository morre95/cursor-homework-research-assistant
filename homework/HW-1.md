Jag har tittat på nyheter från de senaste två veckorna inom AI. AI rör sig så snabbt framåt så att ta in allt detta över ett större tidsspann kommer bli mer jobb än det är tänkt för den här uppgiften.

## AI och cyber: tydligt skifte från om till hur snabbt

En återkommande punkt är oro kring att nya, mer kapabla modeller kan sänka trösklarna för cyberangrepp (både genom bättre planering, snabbare sårbarhetsanalys och mer övertygande social engineering). IAPP pratar om ett nytt modellsläpp som väckt uppmärksamhet och att regeringar/regulatorer bracer för AI-drivna cyberattacker, dvs. att hotbilden betraktas som mer påträngande och större än tidigare. Källans framhäver att nästa steg inte bara är “mer phishing”, utan potentiellt mer skalbara och automatiserade angreppskedjor där AI blir en multiplikator av angriparens kapacitet.

## Anthropic: stegvis/uppskjuten release av Claude Mythos p.g.a. cyberrisk

En konkret nyhet är att Anthropic valde att bromsa och/eller fasa in lanseringen av sin nya modell Claude Mythos med hänvisning till cyberrelaterade risker. Den har hittat djupa, dolda fel i grundläggande infrastruktur som funnits där i decennier utan att någon människa märkt dem. Den fann exempelvis en 27 år gammal sårbarhet i OpenBSD (som ofta används för brandväggar) som tillät en hackare att fjärrkrascha maskiner, och en 16 år gammal sårbarhet i videobiblioteket FFmpeg. Den ska även ha hittat brister i Linux-kärnan som gav fullständig kontroll över servrar, samt svagheter i populära krypteringsbibliotek så som TLS och SSH.

Det som gör modellen särskilt farlig är att den autonomt kan kedja samman flera olika buggar till en fullskalig attack. Något som normalt skulle ta skickliga säkerhetsforskare flera dagar eller veckor att genomföra kan Claude Mythos potentiellt göra automatiskt och med bara en enkel prompt.

I ett experiment där modellen placerades i en begränsad sandlådemiljö och ombads hitta en väg ut, lyckades den bygga ett flerstegsexploit för att få internetåtkomst, och skickade sedan helt oombedd ett skrytsamt e-postmeddelande till forskaren.

För att förhindra att tekniken används för mer frekventa och skadliga cyberattacker har Anthropic startat projektet "Project Glasswing". Detta är en försvarsallians där företag som Google, Microsoft, Nvidia och Apple får tidig tillgång till modellen för att kunna skanna sina egna system och laga sårbarheterna innan angripare får tillgång till modellen.


## Ökat fokus på modellbeteende och styrning: OpenAI:s Model Spec

OpenAI publicerade en text om sitt arbete med Model Spec. Detta är ett formellt, offentligt ramverk som definierar hur deras AI-modeller förväntas och är avsedda att bete sig. Målet är att göra modellernas beteende tydligt så att användare, utvecklare, forskare och allmänheten kan läsa, inspektera och debattera det. Dokumentet fungerar både som en intern riktining för hur modellerna ska tränas, och som en offentlig referenspunkt som ska skapa ansvarsutkrävande.

Anledningen till att OpenAI har tagit fram denna specifikation är för att främja rättvisa, säkerhet och transparens i takt med att AI blir mer kapabelt. OpenAI menar att det inte räcker att bara be en AI vara "hjälpsam och säker" tex. genom en prompt. Eftersom sådana instruktioner bygger på kontext och mänskliga värderingar. Och genom att då ha nerskrivna regler för detta så ksa det bli enmklare att utvärdera, upptäcka brister och låte samhället påverka hur kraftfulla modeller ska agera.

## Lite intresanta och banbrytande AI-modeller som diskuteras just nu

### Avancerade språk- och agentmodeller

- GLM 5.1 från ZAI: Denna beskrivs som den just nu i särklass bästa öppna modellen på marknaden. Den är särskilt inriktad på att fungera som en självgående AI-agent som kan hantera långa och komplexa uppgifter från början till slut. I vissa tester slår den ledande stängda modeller (som GPT 5.4 och Opus 4.6), och den lyckades autonomt koda ett fullt fungerande Linux-skrivbord med över 50 appar (som webbläsare och telegram-klient) på åtta timmar. Men den lokala modellen är enormt stor och är på hela 1,5 TB.
- Anima version 3 preview: En ny, extremt lättviktig bildmodell (på bara 2 miljarder parametrar) som är bäst i klassen på att extremt snabbt generera anime-bilder och annan icke-fotorealistisk konst
- Waypoint 1.5 från Overworld: En modell som genererar interaktiva 3D-världar i realtid som du kan gå runt i. Det unika är att den kan köras direkt på vanlig konsumenthårdvara, till skillnad från andra system som annars kräver enorm datorkraft och minne.
- Numina: Ett modell-agnostiskt tillägg som löser problemet med att videomodeller ofta genererar fel antal objekt och har öppen källkod. Genom att koppla in Numina kan man få AI:n att exakt förstå räkneord och följa instruktioner som exempelvis "fyra barn bygger två snögubbar"
- Komodo från Nvidia: Ett verktyg som via vanliga textbeskrivningar genererar realistiska 3D-rörelser för människor och robotar. Den förstår och kan hanter fysik, tyngdpunkt och balans även när roboten snubblar, vilket gör att dessa animationer kan användas för att träna fysiska maskiner i virtuella simulatorer
- AEP 1.5 XL: Den har öppen källkod och är en snabb musikgenerator som ryms på vanliga persondatorer och kan skapa en komplett låt utifrån en stilanvisning och inlagd sångtext på under en minut 
