# 📝 AI-verktyg för att generera alt-texter till bilder 

## 🧭 EXPLORE - Problemdefinition:
*Överlag så finner jag AI som analyserar bilder väldigt intressant och det är någonting jag skulle vilja lära mig mer om.*

Jag arbetar som fullstack-utvecklare men med fokus på webben, och just nu så arbetar jag på en tidning och et återkommande problem som jag ser är att många bilder saknar alt-texter. En alt-text är en kort beskrivning av vad bilden föreställer och används av exempelvis skärmläsare för att ge personer med synnedsättning möjlighet att förstå bildens innehåll. Genom att inkludera alt-texter gör vi webben mer inkluderande och tillgänglig för alla, oavsett förmåga att se bilderna direkt.

Bilder är ett kraftfullt verktyg för att förmedla nyheter, och därför är alt-texter avgörande för att säkerställa att även de som använder skärmläsare får en komplett upplevelse och förståelse av nyhetsinnehållet. Alt-texter förbättrar inte bara tillgängligheten, utan också webbplatsernas SEO. Tyvärr är det vanligt att alt-texter saknas eller inte håller den kvalitet som krävs för att ge en korrekt beskrivning av bilden, särskilt i medie- och nyhetsbranschen, och detta är någonting som jag tänker att jag kan förbättra med mitt projekt. 

Därför är målet med detta projekt att utveckla ett AI-baserat verktyg som hjälper journalister och innehållsskapare att snabbt generera förslag på alt-texter. Genom att använda detta verktyg kan redaktionen enkelt skapa korrekta alt-texter som både sparar tid och förbättrar tillgängligheten på webbsidorna, samtidigt som det säkerställer att tillgänglighetsstandarderna följs.

## 👩🏼‍🏭 DEFINE - Problemlösning:

### MODELL 
#### Bildklassificeringsmodell: 
Vad jag har förstått så är användningen ev ett CNN (Convolutional neural network) ett av de vanligaste sätten som man använder när man vill bygga en bildklassificeringsmodell, så därför tänker jag använda mig av detta för att skapa modellen som klassificerar och analyserar bilder. Jag tänker att detta är ett bra första steg för att se om jag lyckas med en implementation, sedan så krävs det ytterligare steg om jag vill att modellen ska generare själva alt texterna. 

#### Naturlig språkbehandling:
När bildklassificeringsmodellen har byggts och testats kommer nästa steg vara att integrera en språkgenereringskomponent. Denna komponent kommer att ta bildklassificeringsresultaten och generera textbeskrivningar (alt-texter) för varje bild. För detta bör jag använda en NLG (Natural language generation), vilket producerar skrifliga beskrivningar av mitt dataset vilket kommer att vara alt-texten som jag vill skapa. 

#### Integrering av bildklassificering och textgenerering:
Det sista steget blir att integrera dessa två modeller så att systemet kan ta en bild, klassificera den och sedan generera en korrekt alt-text baserat på klassificeringen.

### DATA
- **Flickr8k**: Bildbibliotek med labelled data. https://www.kaggle.com/datasets/adityajn105/flickr8k
  
För att kunna skapa en modell som analyserar bilder och genererar en textbeskrivning av bilden så behöver jag självklart tillgång till bilder, och för att träna modellen så underlättar det om dessa är labelled. Det finns många dataset online som man kan använda sig av, och eftersom scopet på projektet inte är så stort så tänkte jag använda mig av Flickr8k-datasetet, som innhehåller 8000 bilder som redan har labels - vilket gör att detta inte är någonting som jag själv måste producera. Om jag senare vill utveckla min produkt och förbättra den så är det nog en bra ide att använda sig av ännu mer data, då det kan säkerställa en mer precis modell - jag kanske även märker redan under skapandet av denna att jag behöver flera bilder att träna modellen på, vi får se. 

### BEARBETNING AV DATA 
**För att säkerställa hög prestanda på bildklassificeringsmodellen så krävs det en del preprocessing av bilderna**
#### Datainsamling:
Datasetet från Flickr8k innehåller bilder med textbeskrivningar. Dessa labels kommer initialt användas för att träna modellen i att känna igen olika objekt och scenarion i bilderna. I detta steg kan vi fokusera på att klassificera bilderna i övergripande kategorier (djur, landskap, människor etc).
#### Förbehandling av bilder:
- Skalning av bilder: För att säkerställa att alla bilder har en standardstorlek (t.ex. 224x224 pixlar) innan de matas in i modellen.
- Normalisering av pixelvärden: Pixelvärdena normaliseras till intervallet [0, 1] för att underlätta modellträningen.
- Borttagning av brus: Eventuella bilder med låg kvalitet, suddiga motiv eller felaktiga format rensas bort.
#### Utforskning av datasetet (EDA):
- Datakvalitet: Kontrollera om alla bilder har tillhörande beskrivningar och om det finns några avvikande datapunkter.
- Datafrekvens: Hur fördelningen av olika kategorier ser ut och om datasetet är tillräckligt balanserat.
#### Konvertering till numeriskt format:
- Bilderna konverteras till numeriska format genom vektorisering, vilket möjliggör att de kan bearbetas av maskininlärningsmodellen.

### FEATURES
- Samla data och preprocessing av bilder för att säkerställa att de alla har rätt format
- Modellen tränas (CNN) och alt texter genereras baserat på klassificerade bilder (NLG)
- Ett användargränssnitt som man kan ladda upp egna bilder (?)
- Alt-text generering baserat på användarens input (i detta fallet kanske det är jag som lägger till bilder i programmet) 



## 🤔 EVALUATE - Utvärdera begränsningar:
Jag tror att projektet ska vara implementerbart, men det är också därför jag funderar på att dela upp det i två steg för att se hur mycket tid det krävs. Jag kommer att testa mig fram ocg förhoppningsvis så kommer jag att kunna skapa en första implementation av en modell som klassificerar bilder som sedan får genererade bildbeskrivningar. 

### BEGRÄNSNINGAR
- Tid
- Kunskap, det är svårt att sätta scopet när jag inte helt vet vad jag kommer ha tid till eller vad mina begränsningar ligger inom förståelse av AI 
- Datakvalitet och datamängd
- Kvalitet på bildbeskrivningarna, det kan vara svårt att generera beskrivningar som är både korrekta och naturliga.

## 🤠 IMPLEMENT & ITERATE:
Dett ska jag börja med och aktivt arbeta med!




