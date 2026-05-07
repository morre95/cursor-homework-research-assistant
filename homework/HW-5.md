# HW-5: AI Evaluation

# AI-utvärdering: bäst modell är inte alltid smartast val

## Inledning

När moderna AI-system utvärderas är det lätt att fastna i frågan: vilken modell är bäst? I praktiken är det ofta fel fråga. En modell som får högst poäng på ett offentligt benchmark är inte automatiskt bäst för en skola, ett företag, en vårdapp eller en myndighet. Den viktigare frågan är: fungerar systemet tillräckligt bra för just detta användningsfall, för dessa användare och kanske dessa risker? Min syn är att smart AI-utvärdering handlar mindre om att jaga högsta möjliga modellpoäng och mer om att välja en modell som är tillräckligt bra för uppgiften.

## Benchmarks och deras gränser

Offentliga benchmarks är användbara eftersom de ger något att utgå ifrån. De gör det möjligt att jämföra modeller på samma test och kan visa om en modell är stark på exempelvis matematik, kodning eller språkförståelse. Problemet är att sådana tester lätt får för stor betydelse. Om en modell har tränats på frågor som liknar benchmark-frågorna kan resultatet bli missvisande. Modellen kan då verka intelligentare än den är, ungefär som en elev som har sett provfrågorna i förväg.

Ett annat problem är att benchmarks ofta mäter modellen isolerat, inte hela AI-systemet. Ett system består också av instruktioner, användargränssnitt, säkerhetsfilter, datakällor, verktyg, mänsklig kontroll och hur användare faktiskt tolkar svaret. En chatbot kan prestera bra på ett test men ändå ge dåliga råd i en stressig kundsupportmiljö. Därför bör offentliga benchmarks ses som första signaler, inte som bevis. Bäst praxis är att komplettera dem med egna testfall, privata testset, mänsklig granskning för att utverdera om modellen passar in i systemet den är tänkt för.

## Klassiska mått och moderna AI-system

Klassiska ML-mått är fortfarande viktiga. Accuracy visar hur ofta modellen har rätt totalt, men kan bli missvisande om datan är ojämn. Om 95 procent av fallen är ofarliga kan en modell få hög accuracy genom att nästan alltid svara "ofarligt", men ändå missa de viktiga riskfallen. Precision handlar om hur många av modellens positiva svar som faktiskt är rätt. Recall handlar om hur många verkliga positiva fall modellen hittar. F1-score balanserar precision och recall.

Vilket mått som är viktigast beror på konsekvensen av fel. I spamfilter kan några felaktigt blockerade mejl vara irriterande, men i medicinsk screening är ett missat sjukdomsfall mer allvarligt. För LLM-system räcker inte heller klassiska mått alltid. Öppna svar kan vara delvis rätt, hjälpsamma men osäkra, eller språkligt övertygande men faktamässigt fel. AI-system är ofta bra på att låta övertygande även när dom har fel. Då behövs även automatiserade tester för hallucinationer, säkerhetstester och mänsklig utvärdering.

## EU AI Act och ansvar

EU AI Act visar att utvärdering också är en juridisk och etisk fråga. För högrisk-AI krävs bland annat riskhantering, dokumentation, mänsklig tillsyn, och cybersäkerhet. Särskilt viktigt är kraven på data: tränings-, validerings- och testdata ska vara relevanta och representativa, så att systemet inte förstärker diskriminering. Det betyder att organisationer inte bara kan fråga "hur bra är modellen i genomsnitt?", utan också "för vilka grupper fungerar den sämre?".

Detta är viktigt eftersom ett genomsnitt kan dölja orättvisa. Ett system för rekrytering kan ha bra total precision men ändå missgynna vissa grupper. Ett kreditbeslutssystem kan verka effektivt men skulle kunna bygga på historiska mönster som redan innehåller bias. Därför måste bias-testning, dokumentation och mänsklig möjlighet att ingripa vara en del av utvärderingen, särskilt när beslut påverkar människors rättigheter och möjligheter.

## Att välja rätt LLM

För en praktiker bör modellval börja med användningsfallet. Om modellen ska sammanfatta interna mötesanteckningar kanske snabbhet, kostnad och integritet är viktigare än att den kan reolera på ett maximalt sätt. Om modellen ska hjälpa jurister, läkare eller elever krävs högre krav på korrekthet, källor, spårbarhet och mänsklig kontroll. En generell princip är att välja den minsta och billigaste modell som klarar uppgiften med acceptabel kvalitet och risknivå. Större modeller kan vara bättre på svåra resonemang, men de är också dyrare, långsammare och kan till och med vara onödiga i sammanhanget.

Organisationer bör därför mäta mer än bara svarskvalitet. De bör mäta feltyper, svarstid, kostnad, användarnas förtroende, säkerhetsrisker, bias, hur ofta människor behöver korrigera modellen och vad som händer när modellen misslyckas. Ett AI-system som påstås aldrig göra fel är orealistiskt. Det viktiga är i stället att felen är förstådda, begränsade, upptäckbara och hanterbara.

## Avslutning

Att utverdera ett AI-system går inte bara ut på att ta del av offentliga benchmarks, accuracy, precision, recall och F1-score. Dessa verktyg är användbara men räcker sällan till för att avgöra om ett AI-system är pålitligt eller inte för uppgiften. I slutändan handlar utverderingen mer om omdömme och egna test resultat i rätt miljö.


