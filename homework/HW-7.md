# HW-7: Hälso- och sjukvård, sjukdom och modern AI

### Modern AI i mötet mellan sjukdom och sjukvård

Modern AI används i sjukvården för att tolka bilder, prioritera remisser, stödja läkemedelsutveckling och analysera stora biologiska datamängder. Sjukdomar framträder ofta som mönster i data — röntgenförändringar, genuttryck, riskfaktorer — och eftersom vi äniskor är sämre påå astt hitta mänster i stora mänder data så är maskininlärning ett bra kompliment, men sällan helt ersätta ett mäskligt omdöme.

**När “nästan lika bra” räcker.** Även om ett AI-system diagnostiserar något sämre än en erfaren specialist gör. Så kan det ändå vara värdefullt. En AI kan vara en tillgång och tillföra tempo vid tex. förstegsscreening, triage av akutmottagning, uppföljning av kroniska patienter, eller när alternativet är långa köer eller ingen specialist på plats. Då kan AI vara en resurs och frigöra tid, fånga fler som behöver vidare utredning och minska väntan under förutsättning att misstänkta fall alltid eskaleras till en människa. I situationer med sällsynta symptomer och där den enskildes livskvalitet sätts på spel är det nödvändigt med mänsklig specialistkompetens och helhetsbedömning.

**Exempel där AI gett stor praktisk nytta.** AI-stödd lungröntgen-screening har i fält satts in mot tuberkulos och relaterade avvikelser; rapporterade framgångar handlar mindre om att AI är “magi” och mer om att den skalar screening där radiologresurser saknas så att fler fall hittas och fler kan kopplas till behandling. Hos unga och diabetiska studier har autonoma AI användning kraftigt ökat andelen som får ögonbottenfoto och uppföljning, jämfört med sedvanlig vård. Vilket är en ren folkhälsovinst när underlag annars uteblir. Liknande logik gäller satsningar på primärvårdens ögonscreening där AI kan minska glapp mellan grupper med olika mycket tillgång till sjukvård (tex. skillnaden mellan rika och fattaiga områden).

**Styrkor och svagheter.** Styrkor: lägre kostnad per analys, snabb hantering av standardfall, 24/7-tillgänglighet i teorin, stöd till forskning och molekyldesign. Svagheter: höga fasta kostnader för utveckling och kvalitetssäkring, risk att komplexa fall hamnar fel om modellen övergeneraliserar eller rent av halisunerar, patientens information och samtycke måste vara tydliga och att integrerade arbetsflöden kräver utbildning så att personal inte blint litar eller blint avfärdar förslag.

**Diagnostik, läkemedel och forskning.** AI kan hitta signaturer i bilddata och biomarkörer, accelerera hypotesprövning i den medicinska forskningen och sålla molekyler i läkemedelsutveckling. Som en mäniska annars skulle ha svårt att hitta. I vissa ej så definierade uppgifter kan maskiner matcha eller överträffa genomsnittsläsaren (t.ex. vissa bildklassificeringsuppgifter under förusättning att träningsdatan är bra), men “bättre än människa” är inte samma sak som “ersätter läkare” eftersom sjukvård kräver kontext, etik och ansvar. Och i det avsendet har en LLM svårare att prestera på ett tillförliteligt sätt.

**Hallucinationer och fel råd.** Språkmodeller kan fabricera “källor” och ge trovärdiga men felaktiga rekommendationer. Därför är de olämpliga som enskild källa för behandlingsbeslut utan mänsklig validering (humen in the loop). Särskilt för patienter som söker råd på egen hand och kanske inte har den utbildning och förståelse för vad AI är.

**Integritet och data.** Hälsojournaler och bilddata är känslig data. En AI-analys kan förbättra vården men ökar också risken för dataläckor, **sekundär användning** och krav på tydliga gränser och övervakning av AI-systemet av en mäniska.

**Bias.** Det är extra vilktigt att träningsdatan är bra. Om träningsdata domineras av vissa populationer kan modeller fungera sämre för andra — det kan ge **orättvis** diagnostik och felprioritering. Så det ställer höga krav på att alla steg i processen är rätt av vägda.

**Ansvar.** När AI-assisterad vård misslyckas blir frågorna snabbt juridiskt och etiskt svåra: tillverkare, vårdgivare, kliniker som godkänt förslaget eller avvikit från rutin kan alla bli involverade. Samhället behöver tydligare **roller och processer** (CE-märkning, kliniska rutiner, dokumentation).

**Verktyg eller ersättare.** Ett rimligt arbetsflöde är AI som **beslutsstöd**: människa har ansvar och ha sista ordet medans AI flaggar risker. Att ersätta professioner helt förutsätter acceptans, robust klinisk evidens och system för eskalation. Annars ökar risken för fel och alienation för patienter.

**Global tillgänglighet.** AI kan underlätta viss screening om infrastruktur, utbildning och regulatoriska villkor finns. Utan det blir skillnaden mellan rika och fattiga regioner snarare större.

**Prediktiv medicin och övervakning.** Prediktion av risk kan förebygga sjukdom men också leda till **diskriminering**, överdiagnostik och övervakningssamhälle om riskpoäng används och missbrukas av arbetsgivare eller försäkringsbolag utan skydd detta.

**Vad är saliency maps?** En saliency map (sv: ofta *salienskarta* eller “förklaringsheatmap”) är en visualisering som visar **vilka delar av en bild (eller indata) som tycks ha störst inflytande** på modellens utfall. Tex. vilken lungröntgen-region som fick modellen att föreslå pneumoni. I sjukvårds-AI är det särskilt viktigt för **transparens och kvalitetssäkring**: kliniker kan se om modellen fokuserar på sjukliga förändringar eller på artefakter som märken eller beskärning. Det ökar möjligheten att upptäcka bias och bygga förtroende, även om en karta inte i sig bevisar att modellen “förstår” sjukdomen.

**Skulle jag vilja bli diagnostiserad av AI?** Ja, i **screening och förstegsbedömning** när AI är validerad, dokumenterad och kopplad till mänsklig översyn — särskilt om väntetiden annars är lång. Nej, som enda beslut vid livshotande eller oklara symtom avgör bedömningen. I **utvecklingsländer** skulle min acceptans av AI i vissa lägen kunna vara **högre**, eftersom alternativet ofta är ingen undersökning alls. Och där kan då en välfungerande screening vara räddande. Samtidigt ökar kraven på enkel infrastruktur, utbildning och etiska skyddsregler vid dessa situationer. Eftersom fel och data missbruk kan slå hårdare där rättsstat och vårdens ekonomiska buffertar är svagare.

Sammantaget visar modern AI vägar till snabbare och mer jämlik vård. Särskilt genom bildscreening — men den kräver ärlighet om begränsningar, stark dataetik och att människa och maskin samarbetar istället för att ersätta varandra utan någon slags ansvarskedja.

