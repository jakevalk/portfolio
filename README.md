Name: Jake van der Valk

Studentnummer: 18064396

Leraren: J. Vuurens, R. Vermeij en T. Andrioli

Project: Wheels

---

Hallo, ik ben Jake van der Valk en ik studeer Software Engineering. Tijdens mijn studie heb ik met de gaafste technieken gewerkt. Hierdoor ben ik ook met Data en Artificial Intelligence in contact gekomen. Dit heb ik als zeer leuk ervaren. Toen ik achter deze minor kwam was de keuze ook al vrij snel gemaakt. In deze portfolio zal je meer te weten komen over mijn tijd tijdens deze minor.

# Inhoudsopgave
- [Research project](#Research-project)
- [Predictive Analytics](#Predictive-Analytics)
- [Domain knowledge](#Domain-knowledge)
- [Data preprocessing](#Data-preprocessing)
- [Communication](#Communication)
- [DataCamp & Reflection and evaluation](#DataCamp-&-Reflection-and-evaluation)
- [Bibliografie](#bibliografie)




# Research project
Ik heb aan het research project actief meegedaan. Mede omdat ik zelf 100% deze opdracht wilde. Ik heb deze project dan ook als leuk ervaren.
## Task definition

Binnen sport wil men altijd de beste zijn. De coaches willen daarom ook altijd weten of iemand optimaal presteert. Doormiddel van technologie probeert men dat te bereiken [[1]](#1). Binnen sporten als Rugby, Voetbal, Australian Rules Football, Hockey en American Football zijn fitness trackers al de normaalste zaak. Hiermee kunnen de coaches zien hoeveel een speler heeft gedaan. Ze kunnen dan ook de trainingen aanpassen zodat er geen overbelasting komt [[2]](#2). Deze trackers zijn speciaal gemaakt voor de gezond van lijf en leden zijn. Ze werken dus niet voor rolstoel sporten. Een stappenteller heeft namelijk weinig nut voor iemand in een rolstoel. Om dit wel mogelijk te maken zijn er IMU trackers op de rolstoel geplaatst. Hiermee kan de rotatie snelheden van de wiel en frame berekent worden. Door verschillende berekeningen kan men achter de snelheid en acceleratie komen [3]. Men wilde toen weten of hier bepaalde spelpatronen konden worden gehaald. Omdat dit handmatig heel veel werk is, werd machine learning als een mogelijke optie gezien. Hier zijn we bij ons project aangekomen.

Bij ons project was het de bedoeling dat we doormiddel van IMU data verschillende rolstoelbasketbal specifieke bewegingen identificeren. Dit zou kunnen worden gebruikt om vermoeidheid en overbelasting te voorspellen. Dit zou kunnen komen doordat beweging te vaak is uitgevoerd. Nadat we orienterende research hadden gedaan zijn wij tot de volgende researchvragen gekomen:

- Research question:
    - How can IMU data be used to identify wheelchair basketball-specific movements?
- Sub-questions:
    - Which form of data processing will be used?
    - Which specific movements can be detected?
    - Which sensor data is used for each movement?
    - Can movements be used to predict fatigue?
    - Can movements be used to detect overload?

Dit is te vinden in onze [plan van aanpak](https://github.com/jakevalk/portfolio/blob/main/Documenten/Plan%20of%20approach.pdf).

## Evaluation

Halverwege het project kamen we erachter dat dit niet haalbaar was. De dataset had ons teveel problemen gegeven. De videodata klopte niet waardoor we niet zeker konden zijn of we alles hadden. Om dit op te lossen hebben we twee modellen gebruikt en daar van de false positives vergeleken. Toen kwamen we erachter dat de overlap wel een positive value is. Daarom hebben wij ons onderzoek aangepast en verder oplossing gesproken. We hebben hier nieuwe vragen uit gekregen:

- Can an RFC and a RNN be used to classify sprints in partially defined IMU recordings?
    - Which form of data processing will be used?
    - Which sensor data is used to detect a sprint?

Deze vragen zijn beantwoord in onze research paper. We hebben ook aan de volgende stap gedacht:

Op dit moment werkt het enkel met sprints. Dit is maar één beweging. Het was onze bedoeling om dit ook nog voor de contact momenten en de rotaties te doen. Dit was  door tijdsgebrek helaas niet mogelijk. Deze bewegingen hebben wel duidelijke patronen. De sprints zouden gebruikt kunnen worden om vermoeidheid te identificeren. De zou gedaan kunnen worden door de snelheid van de sprints te vergelijken. Ook zouden de mogelijke repetities voor overload kunnen zorgen. Dit zou dan blessures kunnen veroorzaken. De technieken die we hebben gebruikt zijn niet enkel bij rolstoelbasketbal te gebruiken. De technieken zijn bruikbaar voor datasets waarin het berekenen van een ground truth voor een classificatie probleem niet goed werkt.

## Conclusions

In dit project hebben we een methode ontworpen die rolstoelbasketbal sprints classificeert doormiddel van een RNN en een RFC. Deze methode maakt het mogelijk om sprints te classificeren in een dataset dat maar voor een deel gedefineerd is. Dit wordt gedaan door de resultaten te vergelijken tussen de twee modellen. Door het vergelijken van de resultaten zijn we van 2.3% naar 17.3% gegaan, dit is hoeveel de dataset uit sprints bestaat.
Tijdens het validatieproces is gebleken dat de RFC nu 90.4% van alle getagde sprints kan vinden. Dit doet de RFC met een precision van 89%. Dit hebben we vervolgens getest op een andere speler. De RFC had een precision van 91.67% bij de dataset van de andere speler. Dit laat zien dat het model goed werkt, en het mogelijk maakt om sprints te classificeren doormiddel van meerdere modelen.

## Planning
Ik heb tijdens het project veel met scrum gewerkt. Ik was namelijk de scrummaster. Ik was de scrummaster omdat ik degene was die het meeste ervaring had van scrum. Ik heb bij het project mijn best gedaan om de best practice regels van scrum te volgen. Dit was niet altijd even makkelijk. Tijdens het project waren er steeds momenten dat het niet helemaal perfect ging. Het verdelen van punten zorgde namelijk voor verwarring. Om dit op te lossen had ik besloten om scrumpoker te gebruiken. Dit is een methode waarin dit een stuk eenvoudiger wordt gedaan. Iedereen vult namelijk op een website een getal in en dit wordt vervolgens weergegeven. Dit is misschien heel simpel maar het heeft wel veel geholpen. 

Tijdens het project hebben we verschillende retrospectives gehad. Hierin konden we allemaal vertellen waar we mee zaten. In het begin schreef ik dit allemaal op in een word document. Ik kwam er vrij snel achter dat dit niet effectief was. Ik moest namelijk steeds alles doen. Hierdoor moesten mensen soms iets twee keer zeggen. Hierdoor besloot ik om een betere methode te vinden. Ik vond toen een website die dit goed kon. Hier kon elk groepslid zelf dingen toevoegen en zag het er ook een stuk beter uit. Dit werd goed ontvangen.
















# Predictive Analytics
Ik heb tijdens het project aan vele verschillende modellen gewerkt. Dit heb ik gedaan om veel ervaring te krijgen binnen de stof. Dit heb ik uiteraard allemaal met een reden gedaan.
## Selecting a Model

Binnen het project was het al vrij snel duidelijk dat we een classification model nodig hadden. Dit kwam omdat we verschillende datapunten als sprints moesten classificeren. De no free lunch theorem[[4]](#4) stelt dat je niet van te voren kan weten welke model goed is, daarom wilde we als groep meerdere dingen proberen. Aan de start van het project hebben ik en twee groepsgenoten ieder model genomen en deze toegepast op de dataset. Dit deden we om een model op een echte dataset te gebruiken. Hierin zouden we dan achter mogelijke problemen kunnen komen. De modellen waarvoor we gekozen hadden waren:

- KNearestNeighbours
- Gaussian Naive Bayes
- Decision Tree

Hier bij had ik toen zelf voor de Gaussian Naive Bayes gekozen. Dit heb ik gedaan omdat GNB goed werkt met tijdsgebonden data. Het was de bedoeling van onze proef om verschillende soorten modellen te gebruiken. Een GNB is één van de simpelste Bayes modellen. De Bayes theorie [[5]](#5) is een formule dat voorspelt dat de kans op een gebeurtenis gebaseerd is op de kennis over condities die te maken hebben met deze gebeurtenis. Ik was van mening dat dit bij sprints ook zou kunnen helpen.

De resultaten per model was:
| Model | accuracy  |
|---	|---	|
|KnearestNeighbours	|0.9997976349230234|
|Gaussian Naive Bayes|0.9950939440953502|
|Decision Tree|0.9999974055759362|

Alle modellen waren uiteindelijk zeer accuraat. Dit kwam mede doordat we een extreem simpele target variabel hadden gebruikt. Uiteindelijk hebben we in het model een decision tree gebruikt. Dit had ik toen van te vooren niet verwacht omdat het zo simpel is. De Occams Razor theorie stelt dat de simpelste oplosing vaak het best werkt. Toendertijd wist ik nog niet van deze theorie (maar nu wel :) ).

## Configuring a Model


Het is belangrijk dat de juiste features en hyperparameters gebruikt worden. 
Bij de contact momenten heb ik een RFC gebruikt. Dit is een veel voorkomende model van scikit-learn.  Om de juiste features te krijgen heb ik verschillende features uitgeprobeerd. Ik heb vervolgens een feature importance functie over het model laten lopen. Dit rangschikte features op volgorde van effectiviteit. ![feature importance](https://github.com/jakevalk/portfolio/blob/main/afbeeldingen/featureimportance.png)
 Ik heb hier de beste features uitgeprobeerd.
 Ik heb vervolgens het model door een gridsearch [[6]](#6) heen gehaald. Dit gaf de optimale hyperparamaters.

## Training a model

Het trainen van het model voor de contact momenten heeft mij veel problemen gegeven. Om dit werkend te kunnen krijgen heb ik een hoop technieken moeten gebruiken om dit relatief goed te maken. De dingen die ik gedaan heb zijn:
- Data balanceren. 
- Gridsearch toepassen om de hyperparameters te krijgen.
- Totaal aantal features verminderen.
- Data in 75% en 25% opgesplitst.

Bij de sprints was het zo berekend dat het bij een bepaalde situatie boven een bepaald niveau moest zijn. Dit was qua tijd bij de contact momenten niet mogelijk. Hierom is ervoor gekozen om de data rondom de getagde gebeurtenis te gebruiken. Omdat een contact heel veel van elkaar verschilt heeft dit waarschijnlijk voor problemen gezorgd. Ik ben dan ook van mening dat het model goed gemaakt is maar het probleem bij de data ligt. Dit maakt het uiteraard niet goed. 

Dit is de [notebook]().

## Evaluating a model

Het is belangrijk dat een model goed geevalueerd wordt. Indien dit niet zorgvuldig gedaan wordt is er een grote kans dat een model eigenlijk niet goed is. Bij mij is het opgevallen dat tijdens de interne presentaties klasgenoten het enkel hadden over de accuracy. Ik ben er vanzelf achter gekomen dat de accuracy bij een complexe dataset eigenlijk helemaal niks zegt. Mijn RFC geeft een accuracy van 0.98. Dit klinkt alsof het een hele goede model is. Dit is het namelijk niet. Als je naar de confusion matrix kijk zie je iets heel anders:
![confusion matrix]()
Het is eigenlijk totaal niet goed. Dit is waarom er ook naar de precision en recall moet worden gekeken. De RNN van een groepsgenoot die over de sprints heeft bijvoorbeeld een accuracy van 0.90, maar wel een precision van 0.86 en een recall van 0.91. De accuracy is dus wel wat lager, maar het model is wel stukken beter. Het voorspelt namelijk wel degelijk iets.

Het is daarom belangrijk om een confusion matrix  te gebruiken. Als ik dit niet had gedaan was ik waarschijnlijk heel trots geweest op een model dat eigenlijk niet werkt.
## Visualizing the outcome of a model (explanatory)

### To DO
























# Domain knowledge
Tijdens mijn studie ben ik licht in contact gekomen met Artificial Intelligence. Ik heb dit toen als leuk ervaren. Ik wilde hier dan ook meer van leren. Dit was ook een van de redenen dat ik voor deze minor had gekozen. Ik heb tijdens deze minor veel geleerd. Hieronder zal ik hier meer over vertellen.

## Introduction of the subject field

*"Knowledge is power."* - Francis Bacon

Al eeuwen lang is het zo dat degene met alle kennis de macht zal hebben. In het verleden waren dit nobelheden maar in deze eeuw zijn het vooral grote bedrijven. Een goed voorbeeld hiervan zijn de [Big Tech](https://en.wikipedia.org/wiki/Big_Tech#FAANG) bedrijven. Deze bedrijven beschikken over gigantisch veel data. Doordat zij zoveel data hebben kunnen zij dit gebruiken om voorspellingen mee te maken. Dit wordt ookwel data science genoemd.

Binnen data science wordt doormiddel van AI een vraagstuk beantwoordt. Dit soort vraagstukken kan verschillen van "Wat is dit?" tot "Wanneer is dit?". Dit kan gebruikt worden om een betere kennis te hebben van de huidige wereld en de toekomst.

Binnen sport wil men ook alles weten. Het is dan ook logisch dat sportteams allemaal analysten in dienst hebben. Doormiddel van trackers en videobeelden bezitten de analysten over heel veel data. Hier uit is dan ook gekomen dat sportteams ook data science zijn gaan gebruiken om patronen in het eigen spel te vinden maar ook die van de tegenstander. Anticiperen is namelijk beter dan reageren.

Bij rolstoelen is het vrij eenvoudig om er een tracker op te plaatsen. De gebruiker merkt hier weinig van. Veel universiteiten hebben dan ook een research afdeling speciaal voor rolstoeltechnieken. Omdat het vrij eenvoudig is om te meten is het makkelijker om hier voortgang in te hebben. Omdat deze rolstoelen heel veel data verzamelen zou het mogelijk zijn om hier data science op te gebruiken. Dit is waar wij nu te maken mee hebben.
## Literature research

Bij deze minor is er heel veel research gedaan. Hier heb ik verschillende soorten literatuur voor gebruikt. Dit verschilt van websites tot research papers. Hieronder zal ik er meer over vertellen:

- **Websites**
Bij dit project is het meerdere keren voor gekomen dat ik snel iets wilde opzoeken. Op het internet staan veel websites waar dingen summier staan uitgelegd. Deze websites refereren vaak aan research papers. Of het is de website van een library (pandas of numpy). Dit zijn websites waar ik vaak gebruik van heb gemaakt:
    - *Tutorial sites*
        - https://machinelearningmastery.com
        - https://towardsdatascience.com/
        - https://curiousily.com/posts/build-your-first-neural-network-with-pytorch/
        - https://www.datacamp.com
    - *Library sites*
        - https://pandas.pydata.org/docs/user_guide/index.html#user-guide
        - https://scikit-learn.org/stable/user_guide.html
        - https://pytorch.org/docs/stable/index.html
        - https://seaborn.pydata.org/introduction.html
- **Les stof**
Indien ik vast liep kon ik best vaak geholpen worden door de lesstof. Vaak waren de powerpoints een snelle bron van informatie. De notebooks waren soms helpvol bij de syntax gerelateerde problemen. Het was some fijn om te zien hoe het werkte.
- **Research papers**
Als ik langere research deed dan maakte ik vaak gebruik van research papers. Deze meeste papers vond ik via google scholar of via referenties. De research papers staan onderaan in dit document (klik [hier](#bibliografie) om er snel heen te gaan).
## Explanation of Terminology, jargon and definitions

- **Datasets** Een dataset is een tabel waarin data staat. Deze bestaat uit rijen en kolommen. Hierbij zijn de rijen de verschillende datapunten en de kolommen de features. de datasets worden in objecten ingeladen waarna de modellen hun werk hier op kunnen doen.
    - **Features** Een feature is een meetbaar stuk data dat gebruikt wordt voor de analyse. Denk hierbij aan dingen als: "tijd", "snelheid", "kosten", "actie" en leeftijd.
- **Machine Learning** Machine learning is een onderdeel van Artificial Intellegence. Hierbij maken algoritmes modellen die gebaseerd op data voorspellingen en beslissingen kunnen maken.
    - **Model**
    Een model is het bestand dat getraind wordt om verschillende patronen te herkennnen.
        - **Classification** Bij classification wordt een label voorspelt op basis van de input. Het wordt gebruikt om verschillende objecten van elkaar te onderscheiden. Dit wordt vervolgens in categorieën gestopt. 
        Dit zijn classification modellen:
            - KNearestNeighbours
            - Gaussian Naive Bayes
            - Decision Tree
            - RFC
        - **Regression** Bij regression wordt er bepaalde waarde voorspelt. Denk hierbij aan de temperatuur of de koerswaarde van een aandeel. Dit zijn regression modellen:
            - Linear Regression
            - Polynomial Regression
        - **Ranking** Bij ranking wordt er een bepaalde volgorde voorspelt. Denk hierbij aan een zoek algoritme waarbij op basis van voorkeuren een volgorde wordt voorspelt.
        - **Clustering** Bij clustering worden vergelijkbare datapunten gegroepeerd. Dit wordt vaak bij algoritmes gebruikt voor marketing. Hier worden dan personen op basis van eigenschappen gesplitst en in groepen gestopt.
        - **Overfitting**
            Bij overfitting is er sprake van dat het model te goed getraind is op de dataset. Dit is een probleem omdat het dan ook enkel werkt op die ene dataset. Hierdoor is het model niet gebruikbaar voor andere datasets. het model zal enkel de patronen uit de oude dataset herkennen. Dit is te verminderen door technieken als cross-validation te gebruiken.
        - **Underfitting** Bij underfitting is er sprake van een model dat niet heel erg goed is in het identificeren van een patroon in de data. Het is eigenlijk het tegenovergestelde van overfitting. Het betekend dat het model te simpel voor de data. Dit is oplosbaar door een nieuwe set features te gebruiken of gewoon een nieuwe model te gebruiken.
    - **Neural Network** een neural netwerk is een ander soort model. Dit soort model lijkt veel op de hersenen van een mens. Een NN bestaat uit meerdere lagen met nodes. Deze nodes hebben een input en een output. Iedere node kan een wiskundige berekening uitvoeren. Door deze nodes aan elkaar te koppelen kan de NN hele ingewikkelde dingen. Dit is vergelijkbaar met de mens.
        - **Epochs**
        Bij het trainen van een NN maak je gebruik van een epoch. Bij één epoch wordt het model één keer getraind met de dataset. Het is de bedoeling dat er meerdere epochs zijn. Dit betekend dat er meerdere keren over de dataset heen wordt gegaan. in het geval dat er 300 epochs zijn zal de NN 300 keer de dataset zien.
        - **Learning rate**
        De learning rate is de snelheid waarmee een NN leert. Als het laag is duurt het heel lang. Als het hoog is gaat het snel maar er is een kans dat de optimum niet bereikt wordt. 
        - **Linear layers**
        Een NN bestaat uit 1 of meer lagen. Dit is waar de nodes in zitten. Des te meer lagen er zijn, des te complexer het wordt. Een NN met 3 lagen kan meer dan een NN met 1 laag. Het duurt wel langer om te trainen dan een NN met 1 laag.
- **Preprocessing** Om een model te gebruiken moet de data eerst goed verwerkt zijn. Als de dataset een rotzooi is zal het niet goed werken. Dit wordt gedaan om de effectiviteit van een model te verbeteren en/of om te zorgen dat het model überhaupt werkt. Dit kan gedaan worden met de volgende stappen:
    - **Cleaning** Vaak is een dataset een rotzooi. Het is daarom belangrijk dat de dataset wordt opgeschoond. Er zijn vaak waardes die niet kloppen of niet aanwezig zijn. Tijdens de cleaning zorg je ervoor dat de NaN waardes worden weggewerkt en dat de verkeerde data wordt opgelost.
    - **Scaling** Het is belangrijk dat één soort feature niet op twee verschillende manieren wordt weergegeven. Eén centimeter is namelijk kleiner dan één inch. Het is daarom belangrijk om de data te schalen zodat één soort waarde niet onbedoeld het model beinvloed.
    - **Balancing** Indien de positieve en negatieve rows in een dataset niet goed gebalanceerd zijn zal de dataset minder goed werken. Als bijna alle rows negatief zijn zal het model zeggen dat alle rows negatief zijn. Dit wil je voorkomen. Er zijn meerdere manieren om dit te balanceren. Als er ongeveer even positieve als negatieve rows zijn zal dit een stuk beter werken.
    - **Numeric** Een model werkt niet goed met een combinatie van getallen en woorden. Indien beide voorkomen zal het model crashen. Dit is te voorkomen door het woord een getal aantewijzen. 
    - **Outliers** Soms zijn er waardes die niet realistisch zijn. Als er bijvoorbeeld gemeten wordt dat een auto 400 km/h gaat klopt er iets niet. Dit zou het model kunnen verwarren. Dit wordt een outlier genoemd.
- **Evaluation** Nadat een model is getraind is het belangrijk dat het model ook daadwerkelijk nut heeft. Daarom is het belangrijk dat het geevalueerd wordt. Dit zijn dingen die hiervoor belangrijk zijn:
    - **Cross Validation** De dataset wordt in tweeen gesplitst: een trainings set en een validatie set. Hierbij traint men het model op de trainings set en valideert het model op de validatie set. Vaak wordt het zo gesplitst: 75% training, 25% validatie.
    - **Confusion Matrix** Bij een classificatie model wordt een confusion matrix gebruikt. Hierin staat hoeveel goed is voorspelt en hoeveel fout. ![confusion matrix](https://github.com/jakevalk/portfolio/blob/main/afbeeldingen/confusionmatrix.png) Doormiddel van deze waardes kan de Accuracy, Precision en Recall berekend worden. De accuracy geeft weer hoevaak het goed was ((TP + TN)/ N). Precision is hoe precies de model is (TP /(TP+FP)). en de recall is hoevaak het een positieve waarde heeft geantwoord (TP /(TP + FN)). 
    - **Loss** De loss is de hoeveelheid dat het model afwijkt van wat het moet zijn. Dit is nodig voor een regression model. Des te hoger de loss des te slechter is het model. 
- **IMU** Een IMU is een apparaat dat bestaat uit verschillende accelerometers en gyroscopen waarmee rotaties en krachten kunnen worden gemeten/uitgevoerd.
- **Scrum** Scrum is een werkmethode waarbij flexibel tot een eindproduct wordt gewerkt. Hierbij wordt er in korte stappen steeds werkende stukken software opgeleverd. Samenwerking is bij deze methode heel belangrijk.
    - **Scrummaster** De scrummaster is een persoon die er voor zorgt dat Scrum goed toegepast wordt. Hij/zij lost hierbij mogelijke knelpunten op en zorgt ervoor dat de rest zich 100% op het project kan focussen.
    - **Sprint** De fase van een paar weken waarin men tot een tussenproduct komt. Deze fase duurt vaak twee weken en bevat zowel ontwerp, realisatie als testen. Bij een sprint wordt vaak een bord gebruikt met de volgende kolommen: To do, doing, done. Hierin plaatst men de user stories.
        - **User story** Een user story is iets dat gebruikt wordt om een wens te weergeven. Hierbij wordt een statement opgesteld die zo gaat: "Als {titel van persoon} wil ik dat {de wens} omdat {reden}". In een user story staat precies wat er moet gedaan zijn zodat de wens volbracht kan worden.
        - **Retrospective** Een retrospective is een meeting waarin over de afgelopen sprint wordt gereflecteerd. Elk groepslid krijgt hierin de kans om zijn mening over de sprint te geven. Hierbij wordt met drie kolommen gewerkt: Start, keep doing en stop. In start worden alle punten gezet die ze nieuw willen zien. Keep doing zijn de punten die goed gaan. En stop zijn de punten waarmee gestopt moet worden. Als men dit goed doet zal het een hoop irritaties verkomen.
        - **Sprint planning** Aan de start van de sprint worden alle user stories voor de volgende sprint ingepland. Dit gebeurd tijdens de sprintplanning.
        - **Daily standup** Dit is de dagelijkse meeting waarin de voortgang wordt besproken. Hierbij worden de volgende dingen verteld: "Wat heb ik gisteren gedaan?", "Wat ga ik vandaag doen?" en "Heb ik problemen?". Iedereen moet dit vertellen. Als iedereen dit heeft verteld is de meeting klaar. Bij deze meeting is het de bedoeling dat je staat (daarom heet het ook standup). Hierdoor is het een korte meeting van maximaal 15 minuten.
    - **MVP** Het Minimal Viable Product is het minst mogelijke wat toegestaan wordt. Het is dan ook de doel om dit minimaal te halen. 
























# Data preprocessing
Tijdens het project heb ik veel met modellen gewerkt. Dit is zowel tijdens de prototype fase gebeurt als bij de "echte" project.

## Data exploration
In het begin van het project was de dataset compleet onduidelijk. Om dit duidelijker te krijgen heb ik voor meerdere features besloten om deze te visualiseren. Hierbij nam ik verschillende columns en gaf dit weer in combinatie met de TimeLine. Dit komt omdat het een time series is. Dit betekend dat het tijd gebruikt om de data te structureren. Ik heb vervolgens hiervoor meerdere data punten samen gevisualiseerd. Dit gaf mij toender tijd een goed beeld van de situatie.

Om een beter beeld te krijgen ben ik begonnen met experimenteren met de dataset. Dit heb ik toen gedaan omdat er tijdens dit proces verschillende problemen opkomen dat is dan dan vervolgens worden verwerkt. [zie hier er meer over](https://github.com/jakevalk/portfolio/blob/main/Notebooks/data%20exploration.ipynb)

Voor de contact momenten heb ik een functie gebruikt om deze te weergeven. Deze functie is geschreven door een groepsgenoot. Ik heb hier wel dingen moeten aanpassen om dit voor mijn doel te kunnen gebruiken. Het was hier de bedoeling om een patroon te vinden in de grafieken van de contact momenten. Het was hier vrij snel duidelijk dat er een patroon in zit. De patroon is wel steeds licht verschillend. Dit komt doordat bijna elke contact moment anders is. Bij bijna alle contact momenten was er een schudding in het frame en plotselinge snelheidsverschil. Het zou dus mogelijk moeten zijn om hier een model voor te schrijven.

## Data cleansing

De dataset van het project was verre van perfect. Sommige dingen klopte gewoon niet. Hier had ik bij de collisions veel last van. Dit kwam voornamelijk doordat de dataset getagd was door een persoon. Het was dus subjectief. Ik ben toen vervolgens langs alle datapunten heen gegaan en gecheckt of de tijd klopte. Dit was van de 30 samples maar 8 keer het geval. Het klopte dus 22 keer niet. Dit heb ik vervolgens in de dataset aangepast. De accurate tijd was van belang omdat er in model steeds blokjes van 1 seconde worden gestopt. Indien er een seconde naast wordt gezeten zal dit natuurlijk niet accuraat zijn. Er wordt dan het verkeerde moment in het model gestopt. Dit kan je [hier](https://github.com/jakevalk/portfolio/blob/main/afbeeldingen/DataCleaning%20time%20fix.pdf) zien.

Tijdens het proces kwam ik er achter dat er sommige dingen getagd waren waar eigenlijk niks gebeurd. Als er bij de gevallen al iets gebeurde was het extreem licht. Dit was dusdanig licht dat er niks te zien was in de data. Deze datapunten zorgden er dus voor dat verkeerde data als positief werd voorspelt. Het moest dus worden verwijderd. Uiteindelijk waren van de 30 getagde contact momenten maar 19 overgebleven. Uiteindelijk klopte dus 42,11% niet.
## Data preparation

Ik heb tijdens het project meermaals de NaN waardes verwijderd. Dit was gelukkig alleen maar bij categorische variabelen. dit kon dus makkelijk worden opgelost met np.fillna(0). Ik had hier dus geen problemen mee.

Het is belangrijk dat de data gebalanceerd is. Dit was aan het begin uiteraard niet het geval. Omdat er meer negatieve waardes dan positieve waardes zijn heb ik voor een oversampler gekozen. Deze sampler kopieert willekeurige positieve samples zodat er een evenwicht komt. Deze sampler heeft de totale aantal positieve waardes van 53 naar 4747 verhoogd. ![code voor sampler](https://github.com/jakevalk/portfolio/blob/main/afbeeldingen/sampler%20image.png)
## Data explanation

Bij project werden er twee datasets gebruikt. hierbij bestond één van de datasets uit de data die kwam van de rolstoel (IMU data) en was de andere dataset een lijst waarin bij elke actie stond wie wat gedaan heeft, dit was de video data. Hieronder vertel ik er meer over.

#### **IMU Data**
De IMU data is de dataset dat van de rolstoel afkomt. Het is een lineare dataset. De IMU heeft een gyroscoop in zich zitten die voor gegevens zorgt als: RotationSpeed en RotationAngle. Dit is voor alle drie de assen (x,y,x). Deze data is er voor zowel het frame als de rechterwiel. Doormiddel van deze data kunnen andere dingen berekend worden zoals: snelheid en acceleratie. Dit was berekend door Rienk [[3]](#3). In totaal bevat de dataset 16 features en heeft 860409 rows.

#### **Video Data**
Voor deze dataset heeft een stagiair naar een wedstrijd gekeken en bij elke actie dit genoteerd. Dit heeft hij in een speciaal programma gedaan. Hier kwam vervolgens een csv bestand uit. De acties die hij heeft genoteerd zijn:

- ball posesion
- contact zelf gestopt
- contact zelf veroorzaakt
- contact met eigen team
- fast break
- fast defense
- off court
- on court
- score

Hierbij staat er per elke actie aangegeven op welk moment dit plaatsvindt en hoelang het duurt.  
bij alles behalve fast break, fast defense, score en ball possesion staat er aangegeven welke speler dit is. Want bij de andere gaat het om de hele team.

In totaal bevat de dataset 7 features en 808 rows. 

## Data visualization (exploratory)

Elke beweging heeft zijn eigen patroon. Het is alleen niet bekend in welke features dit zit. Daarom ben ik via trail and error de verschillende features gaan weergeven tijdens deze momenten. Hier kwam ik er achter dat bij de contact momenten de X en Y assen van bewogen. Omdat er eerst in één plot zowel de wheelrotation als de framerotation werd weergegeven heb ik besloten om dit op te splitsen. Het was anders niet te zien. Dit kan je in [deze notebook](https://github.com/jakevalk/portfolio/blob/main/Notebooks/Visualisation%20function%20Collision.ipynb) zien.

Achteraf bleek dat dit klopte want uit een feature importance functie bleek dat frameRotationalX feature heel belangrijk was. ![feature importance](https://github.com/jakevalk/portfolio/blob/main/afbeeldingen/featureimportance.png)

















# Communication
Mede omdat ik ICT doe zijn mijn communicatie skills niet perfect. Ik heb hier tijdens deze minor veel op kunnen oefenen. 

## Presentations
Presenteren is niet één van mijn sterkste punten. Dit is natuurlijk voor een ICT student niet heel gek maar het is wel iets waar ik beter in wilde worden. Om hier meer ervaring in op te doen heb ik er voor gekozen om meerdere presentaties te geven. Zowel voor de klas als voor enkel het projectgroepje. De presentaties die ik heb gegeven zijn: 
- [presentatie internal 4 oktober](https://github.com/jakevalk/portfolio/blob/main/presentaties/Internal%20presentation%204%20okt.pdf) 
- [presentatie internal 22 november](https://github.com/jakevalk/portfolio/blob/main/presentaties/Internal%20presentation%2011%20nov.pdf) 
- [presentatie internal 20 december (Samen met Alex)](https://github.com/jakevalk/portfolio/blob/main/presentaties/Internal%20presentation%2020%20dec.pdf)

Ik was van plan om nog een vierde presentatie te geven. Dit heb ik helaas niet kunnen doen. Ik had de dag ervoor een hersenschudding gekregen. Omdat ik een dag complete rust nodig had moest een groepsgenoot de presentatie in mijn plaats doen.
- [poging tot presentatie 6 november](https://github.com/jakevalk/portfolio/blob/main/presentaties/Internal%20presentation%206%20nov.pdf)



## Writing paper
Ik heb actief meegedaan met het schrijven van de paper. Dit heb ik voornamelijk gedaan om een goede groepsgenoot te zijn. Ik heb aan verschillende stukken gewerkt. Bij ons groepje was het zo dat iedereen steeds zijn werk afmaakt en dat een ander dit vervolgens op basis van de feedback verbeterd/uitwerkt.
Dit zijn de verschillende punten:
#### Discussion/Recomendation
Ik heb de de eerste versie van de recommendation geschreven. Ik heb hierbij de feedback van mijn groepsgenoten verwerkt om het zo goed mogelijk te maken.
#### Data preperation
Bij het data preparation stuk heb ik twee stukken samengevoegd. Deze waren eerder door andere geschreven. Ik heb deze stukken vloeiend laten lopen en heb deze verder uitgebreid. Dit is later door een ander overgenomen.
#### problem description
Na de eerste feedback ronden kwamen we er als groep achter dat het problem description gedeelte moest worden vernieuwd. Ik heb dit toen samen met Alex gedaan. We hebben de problem description opnieuw geschreven en nieuwe research (sub)questions geformuleerd. De research question is op een later moment nog verder veranderd. 

#### Verdere kleine uitwerkingen
Toen het verslag was hebben we als groep het verslag doorgenomen en de docenten om feedback gevraagd. Hieruit heb ik aan verschillende delen gewerkt: discussie, introductie en probleemdescriptie. Ook heb ik meerdere keren het verslag doorgenomen en feedback gegeven.
















# DataCamp & Reflection and evaluation
## DataCamp
Aangezien ik Software Engineering doe heb ik programmeren altijd al leuk gevonden. Ik had enkel geen ervaring met Python. Hierom heb ik steeds voor de deadline mijn datacamp opgaves gemaakt. De opgaves kan je [hier](https://github.com/jakevalk/portfolio/blob/main/afbeeldingen/DataCamp%20proof.PNG) vinden.

Tijdens mijn studie heb ik met veel verschillende talen gewerkt. Dit maakte het eenvoudiger om een nieuwe taal te leren. Ik had hierom dus ook niet heel veel moeite met de vragen. Ik had met de volgende dingen de meeste problemen:
- DataFrame slicing
- indentation
- Soms haalde ik talen door elkaar

Dit zijn natuurlijk simpele dingen. De ingewikkelde dingen werden goed uitgelegd en kon door de videos te kijken makkelijk worden gemaakt. Ik was verrast hoe eenvoudig het was om een machine learning functie aan te roepen. Ik kon dan ook sneller dingen dingen doen dan ik eigenlijk had verwacht.


## Reflection and evaluation
### Reflection on own contribution to the project.
#### **Situatie**
Tijdens mijn minorperiode wilde ik actief meedoen aan het project. Ik heb hierbij zowel mijn eigen punten tot mij genomen als mijn groepsgenoten ondersteund.

#### **Taak**
Door mijn achtergrond als Software Engineer heb ik veel ontwikkel gerelateerde taken op mij genomen. Ook ben ik de scrummaster van de groep. Ik heb voor deze belangrijke taak gekozen omdat ik aanvoelde dat ik het meeste ervaring had met scrum. Dit kwam doordat de groep qua opleidingsachtergrond vrij divers was (2x Electrical Engineering, 1x Bewegingstechnologie en 2x ICT (waarvan ik er één was)).

#### **Actie**
Als ontwikkelaar heb ik verschillende dingen gedaan. hierbij heb ik veel oriënterende taken op mij genomen. Ik heb actief meegedaan aan het maken van de verschillende prototypes. Ook heb ik de modellen van onze project gebruikt voor een andere beweging: contact momenten.

Ik heb ook de verschillende omgevingen opgezet. Dit waren Azure DevOps en twee GitHub repos. Ik heb ook mijn groep een masterclass in git gegeven. Dit kwam omdat mijn groepsgenoten nog geen kennis hadden van git.

Als scrummaster heb ik er actief voor gezorgd dat scrum correct en effectief werd uitgevoerd. Ik heb hierbij alle user stories aangemaakt (totaal ongeveer 200). En heb ik alle scrum meetings ingepland. De meetings waren de retro, sprintplanning en alle daily standups. Dit heb ik uiteraard gedaan op basis van feedback van de groep. Indien er sommige dingen niet goed liepen heb ik dit aangepast zodat dit effectiever ging. Voorbeelden hiervan zijn: 
-	vaste volgorde bij de daily standup.
-	Het invoeren van scrumpoker om effectiever de storypoints te aanwijzen.

Het gebeurde soms wel zo dat dingen niet zo liepen dan als hoe het eigenlijk zou moeten. Dit is verder geen probleem, Door flexibiliteit en open communicatie konden de kleinste problemen eenvoudig worden opgelost.

#### **Resultaat**

Door mijn uitgebreide contributie heb ik verschillende dingen gemaakt. De verschillende prototypes hebben een basis gelegd voor de uiteindelijke eindproducten. Er is voornamelijk door gewerkt op wat er al was.
De contact momenten zijn helaas door problemen met de tijd niet gelukt. Dit kwam voornamelijk doordat het rest langer duurde dan gehoopt en er vrij weinig contact momenten zijn in een wedstrijd. Het waren er maar ongeveer 30. Dit is veels te weinig data. Hierdoor was er sprake van underfitting. Om dit te verkomen was de data gebalanced. Dit gaf toen wel betere resultaten maar dit was al te laat. Met een maand extra had dit wel qua kwaliteit goed genoeg geweest (maar dit zegt men altijd :) ).

De git heeft uiteindelijk niet veel nut gehad. Eigenlijk niemand maakte er gebruik van. Omdat dit een extra was is dit geen probleem. De Azure DevOps omgeving is wel veel gebruikt. Dit gebruikten we voor scrum.
Scrum is effectief toegepast. We zijn tot aan mooi eindproduct gekomen. Doordat ik er op pushte dat scrum goed werd gebruikt hebben we als groep een hoop stress vermeden. Onze eindproduct was eigenlijk een tussenproduct. Als we een andere projectsvorm hadden gebruikt dan had dit waarschijnlijk niet gelukt. Doordat we eerder konden stoppen hebben we voor ons zelf de opties open gehouden.	


#### **Reflectie**
Ik ben tevreden met mijn contributie tot het project. Ik ben van mening dat ik een hoop heb gedaan. Ik heb helaas wel wat dingen door persoonlijke omstandigheden gemist. Ik had namelijk een (lichte) hersenschudding. Nadat ik deze had gekregen heb ik een week rust gehouden en vervolgens zo veel mogelijk gedaan. Dit was uiteraard gedaan in overleg met de sportfysio en mijn groepsgenoten. Dit was natuurlijk niet ideaal maar het heeft mijn minor periode niet anders laten lopen.

### Reflection on own learning objectives.
#### **Situatie**

In mijn laatste schooljaar moest ik een minor kiezen om mij verder te ontwikkelen zowel op academisch als persoonlijk vlak.

#### **Taak**

tijdens mijn minor periode wilde ik mijn verder oriënteren op het vlak van artificial intelligence, hierbij wou ik de kennis die ik al had uitbreiden en nieuwe kennis vergaren. verder wilde ik mij ook op een persoonlijk vlak verder ontwikkelen, bij een minor zitten namelijk ook niet IT’ers.

#### **Actie**

Om mij beter te ontwikkelen was een actieve werkhouding nodig. Ik heb gezorgd dat ik op schema bleef zodat ik niet inhaalslag moest maken. Ik heb daarom de DataCamp oefeningen allemaal voor de deadlines gemaakt. En ben naar alle lessen gegaan waar dat mogelijk was. Hierdoor merkte ik dat ik up-to-date was met mijn kennis en daardoor actief mee kon doen aan het project. 
Om mijn softskills te verbeteren heb ik meerdere presentaties gegeven. Ook heb ik veel samengewerkt met groepsgenoten.


#### **Resultaat**

Ik heb bij de minor veel nieuwe dingen geleerd. Ik heb een nieuwe taal geleerd (python). Ik heb geleerd hoe machine learning in de basis werkt. Ik ben ook op een persoonlijk vlak vooruit gegaan. Ik ben beter geworden in presenteren en ik heb veel van mijn groepsgenoten geleerd. 

#### **Reflectie**

Eerder in mijn studie ben ik in contact gekomen met Artificial Intelligence. Dit heb ik altijd heel erg gaaf gevonden. Ik wou hier dus ook meer over weten. De kennis die ik al had ging voornamelijk over Game AI, denk hierbij aan iets als Reinforced learning. Het was zeker interessant om te zien hoe AI op een andere manier gebruikt kon worden. Ik was soms verbaasd om te zien hoe een model vergelijkingen kon trekken uit een dataset. Ook vond ik het bijzonder om te zien dat het model gedeelte qua code nog het simpelst is en de data preproccessing het ingewikkeldst. Ik had het zelf andersom verwacht. Machine learning is natuurlijk iets wat voor een leek heel onbekend is [https://royalsociety.org/-/media/policy/projects/machine-learning/publications/public-views-of-machine-learning-ipsos-mori.pdf].

Ik heb mij veel op een persoonlijk vlak kunnen verbeteren. Ik heb meerdere keren voor de klas gestaan voor een presentatie en ik heb ook met de groep veel leuke dingen gedaan. Dit was door corona helaas niet altijd mogelijk.

Ik heb het gave moment meegemaakt dat ik aan een oud klasgenoot kon uitleggen hoe Image Recognition werkte want hij moest hiermee werken bij zijn minor (en kregen hier gek genoeg helemaal geen uitleg over?!?).

Ik ben blij dat ik voor deze minor heb gekozen omdat ik veel heb geleerd.



### Evaluation on the group project as a whole.
#### **Situatie**

Tijdens de minor periode werd er met een groep samengewerkt. Door de verschillende achtergronden van de studenten is dit heel interessant geworden. geen enkele groepsgenoot was namelijk hetzelfde, Elke groepsgenoot had zowel zijn sterkte punten als zijn zwakte punten.

#### **Taak**

Ons projectgroep is zeer divers,  het bestond uit verschillende nationaliteiten en achtergronden. Het was dus ook de bedoeling om deze verschillen te overbruggen zodat er een goed resultaat komt. Het was  de bedoeling om er voor te zorgen dat iedereen beter uit het project komt, zowel cultureel als educationeel. Het was ook de bedoeling dat de taal barrière binnen de groep overkomen werd. Eén groepslid was namelijk Spaans en de rest Nederlands. Ook was het belangrijk om de verschillende sterkte punten van de mensen te benutten. En de zwakte punten te verbeteren.

#### **Actie**

Als groep hebben we besloten om als voertaal Engels te spreken. Dit is de taal die iedereen sprak. Als we met enkel met Nederlanders in gesprek waren was de voertaal Nederlands (als alleen Nederlanders er waren). Ook zijn we na school een aantal keer iets leuks gaan doen. We hebben vaak mensen die goed konden programmeren laten programmeren. Degene die hier minder ervaring mee hadden hielpen hier dan mee. Als er vragen waren binnen de groep hielp iedereen elkaar. Ik ben daarom ook meerdere keren naar school gegaan op een thuiswerkdag om iemand te helpen met zijn DataCamp oefeningen.

#### **Resultaat**

De Engelse voertaal ging vaak goed. Soms vergaten we het en toen zei iemand hier iets van. Dit heeft verder niet voor problemen gezorgd. De onderlinge communicatie binnen de groep was goed. Iedereen gaf zijn mening las hij het er niet mee eens is. Dit zorgde soms wel voor lange meetings. Door de communicatie was men niet bang om vragen te stellen. Dit zorgde voor een betere werkomgeving.

#### **Reflectie**

Ik ben tevreden hoe het met de groep ging. Al vrij vlot kwam iedereen achter elkaars sterkte en zwakte punten. Hier werd dan ook gebruik van gemaakt. Indien iemand vragen had werden deze beantwoord en iedereen had tijd over om iemand te helpen. Alle problemen die er waren in de communicatie werden vrij snel opgelost. Soms reageerden mensen niet op whatsapp berichtjes en soms hadden mensen discussies terwijl ze hetzelfde standpunt hadden maar het iets anders brengen. Dit heeft niet echt voor problemen gezorgd omdat het na één opmerking al opgelost was. De groepsmeetings op school waren leuk en effectief. Ik heb op school veel verschillende projectsgroepen gehad die de één van die dingen waren maar nooit allebij. Ik ben dus heel tevreden met deze groep.

Ook toen ik mijn hersenschudding hadden de groepsgenoten veel begrip en gaven mij de mogelijkheid om mij de korte rust te gunnen (ongeveer 1 week). Zodat ik effectief kon herstellen zodat ik weer op mijn oude niveau kon presteren. Ik ben hier ook heel dankbaar voor.



# Bibliografie
# 1 https://www.researchgate.net/profile/Lucy-Parrington-2/publication/311166052_The_impact_of_technology_on_elite_sports_performance/links/584f3b1408aed95c25099824/The-impact-of-technology-on-elite-sports-performance.pdf

# 2 https://simplifaster.com/articles/use-gps-technology-team-sports/

# 3 https://repository.tudelft.nl/islandora/object/uuid:d8cffad9-efaf-400b-8e36-5d8eb8becc86?collection=research

# 4 https://ti.arc.nasa.gov/m/profile/dhw/papers/78.pdf

# 5 https://plato.stanford.edu/archives/spr2019/entries/bayes-theorem/

# 6 https://ieeexplore.ieee.org/abstract/document/9649207

# 7 https://www.mdpi.com/1424-8220/14/4/6819

# 8 https://www.mdpi.com/1424-8220/21/8/2601

# 9 https://www.koreascience.or.kr/article/JAKO201232155110113.pdf

# 10 https://www.mdpi.com/1424-8220/16/11/1847/htm

# 11 https://www.mdpi.com/1424-8220/14/4/6891/htm

# 12 https://www.sciencedirect.com/science/article/pii/S1877705815014502

# 13 https://www.mdpi.com/1424-8220/19/10/2237