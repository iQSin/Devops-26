Produktens livscykel

Under kursen har jag fått följa hur en tjänst utvecklas från den första committen till en applikation som kan köras i produktion genom en automatiserad kedja till en viss grad, jag gjorde endast till milstolpe 7. I början låg fokus främst på att få applikationen att fungera och att förstå hur koden och projektets olika delar hänger ihop. Med Git och GitHub kunde jag versionshantera arbetet, spara förändringar och följa utvecklingen över tid.

När vi arbetade vidare med tester, containrar och CI blev det tydligare hur viktigt det är att kunna kontrollera att ändringar inte förstör befintlig funktionalitet. I stället för att enbart lita på att applikationen fungerar efter en ändring kan automatiska kontroller användas för att upptäcka problem tidigare. Containrar gjorde det dessutom enklare att paketera applikationen så att den kan köras i en mer konsekvent miljö.

Ett viktigt steg var arbetet med den virtuella maskinen i cPouta under M7. Där behövde jag förstå flera delar manuellt: SSH-nycklar, säkerhetsgrupper, floating IP, Docker och konfigurationen av containrarna. Det räcker inte att applikationen fungerar lokalt. Jag behövde också se till att tjänsten gick att nå utifrån och kontrollera att hälsokontrollen svarade korrekt. Det gav mig en bättre förståelse för vad som faktiskt krävs för att driftsätta en applikation.

När kedjan sedan byggs vidare med CI och CD förändras arbetssättet. I stället för att själv upprepa alla steg kan arbetsflödet utföra kontroller och hantera driftsättningen enligt en bestämd process. Automation ersätter inte förståelsen för systemen, utan bygger på att de manuella stegen först har konfigurerats och förståtts.

Vad går sönder utan automation?

En konkret del där automation gör stor skillnad är testningen och CI-pipelinen. Om jag skulle behöva testa applikationen manuellt efter varje ändring skulle jag behöva komma ihåg vilka kontroller som ska utföras och själv avgöra om resultatet är korrekt. Det finns en risk att jag missar ett test, testar fel sak eller inte upptäcker ett problem innan ändringen integreras med resten av projektet.

Under arbetet med driftsättningen blev det också tydligt hur många detaljer som måste stämma för att tjänsten ska fungera utanför den lokala utvecklingsmiljön. Fel konfiguration av en port, en säkerhetsgrupp eller en container kan göra att applikationen inte går att nå, även om koden i sig är korrekt. Om hela driftsättningen skulle göras manuellt varje gång skulle det ta längre tid att felsöka och vara lättare att upprepa samma misstag.

Med en automatiserad kedja blir processen mer konsekvent och problemen kan upptäckas närmare den ändring som orsakat dem. Det gör det enklare att förstå vad som gått fel och minskar beroendet av att komma ihåg varje enskilt kommando. Samtidigt har jag lärt mig att automation inte garanterar att allt fungerar. Om exempelvis konfigurationen eller själva arbetsflödet är fel kan felet upprepas automatiskt. Därför behövs både tester, tydliga loggar och förståelse för varje steg.

Min viktigaste lärdom är att driftsättning och underhåll inte är separata aktiviteter efter utvecklingen, utan en del av produktens hela livscykel. En bra lösning ska inte bara fungera en gång, utan också kunna kontrolleras, uppdateras och driftsättas på ett tillförlitligt sätt.