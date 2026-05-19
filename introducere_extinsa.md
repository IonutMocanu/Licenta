# Introducere

## Contextul roboticii mobile inteligente și al realității augmentate în automatizare

Datorită avansului tehnologic din ultimele decenii, robotica a ajuns să cuprindă domenii foarte variate, de la inginerie mecanică, electronică și automatizări, până la inteligență artificială, viziune computerizată și interacțiune om-robot [26]. În prezent se observă un trend accentuat pentru dezvoltarea sistemelor robotice capabile să se deplaseze autonom, să perceapă mediul înconjurător și să execute sarcini de manipulare asupra obiectelor din acel mediu. Acest tip de sistem este cunoscut în literatura de specialitate sub denumirea de manipulare mobilă autonomă și este compus, în general, dintr-o platformă mobilă autonomă pe care este integrat un braț robotic de manipulare [1], [27].

Importanța acestor sisteme este dată de faptul că ele nu mai sunt limitate la o poziție fixă, așa cum se întâmplă în cazul multor roboți industriali clasici. Un robot mobil cu braț de manipulare poate naviga într-un spațiu, poate ajunge lângă obiectul de interes, poate efectua o operație de tip pick and place, iar apoi poate continua deplasarea către o altă zonă. Această mobilitate transformă robotul dintr-un echipament izolat într-un participant activ al procesului tehnologic. În aplicații de logistică, producție, mentenanță, agricultură sau chiar asistență medicală, un astfel de sistem poate prelua sarcini repetitive, dificile sau periculoase pentru om [1], [5].

În orice domeniu vital, roboții au devenit din ce în ce mai prezenți. Putem observa influența lor într-un magazin, unde pot fi utilizați pentru inventariere sau transport intern, într-o fabrică, unde pot participa la fluxuri de producție flexibile, sau într-o sală de operație, unde sistemele robotice asistă medicul în intervenții care necesită precizie ridicată. Integrarea roboților în aceste domenii nu a apărut doar din dorința de a folosi tehnologii moderne, ci mai ales ca urmare a unor nevoi reale ale stakeholderilor implicați: siguranță, repetabilitate, eficiență, reducerea efortului uman și creșterea calității procesului [4], [6].

În același timp, includerea roboților mobili autonomi în spații în care se află și oameni a dus la apariția unor cerințe suplimentare de siguranță și de predictibilitate [3]. Un robot care se deplasează autonom trebuie să își cunoască poziția, să evite obstacolele, să reacționeze la schimbări ale mediului și să ofere operatorului informații clare despre starea sa. Dacă aceste informații lipsesc sau sunt greu de interpretat, pot apărea situații neplăcute cauzate fie de defecțiuni tehnice, fie de erori umane, fie de o comunicare slabă între sistem și utilizator [2], [3].

În acest context, interacțiunea om-robot devine o componentă esențială. Nu este suficient ca robotul să funcționeze corect din punct de vedere tehnic; acesta trebuie să poată fi urmărit, înțeles și controlat de către operator. Într-o industrie în care accentul se pune tot mai mult pe colaborarea dintre om și tehnologie, interfața dintre utilizator și sistemul robotic are un rol foarte important [4]. O interfață bine proiectată poate reduce riscul de eroare, poate crește încrederea operatorului și poate transforma un sistem complex într-un instrument accesibil.

Una dintre direcțiile actuale pentru realizarea unor astfel de interfețe este realitatea augmentată, cunoscută și ca AR, de la termenul din limba engleză augmented reality. AR este o tehnologie imersivă care permite suprapunerea informațiilor digitale peste mediul real. În cazul roboticii, aceasta poate fi folosită pentru vizualizarea poziției robotului, a traiectoriilor planificate, a stării senzorilor, a zonelor de risc sau a comenzilor disponibile pentru utilizator [2], [5]. Față de o interfață clasică afișată pe un monitor, AR are avantajul că păstrează utilizatorul conectat la mediul real și adaugă peste acesta informația digitală necesară.

Realitatea augmentată permite în același timp utilizarea sau operarea robotului de către persoane care nu au neapărat cunoștințe tehnice avansate. Acest aspect este important mai ales în contextul Industry 5.0, unde accentul nu mai cade doar pe automatizare și eficiență, ci și pe soluții centrate pe om [4], [6]. Dacă Industry 4.0 a promovat conectivitatea, digitalizarea, sistemele cyber-fizice și analiza datelor, Industry 5.0 aduce în discuție colaborarea dintre om și robot, personalizarea și integrarea tehnologiei într-un mod mai natural pentru utilizator [6], [7], [8].

Conform direcțiilor actuale din literatura de specialitate, caracteristica principală a Industry 5.0 este orientarea spre utilizator și spre personalizarea proceselor [6], [7]. Într-un astfel de cadru, AR poate contribui prin interfețe vizuale intuitive, panouri interactive, feedback imediat și posibilitatea de a adapta modul de prezentare a informației în funcție de utilizator. Pentru un operator tehnic, interfața poate afișa topicuri ROS2, stări ale nodurilor, erori și parametri de planificare. Pentru un utilizator mai puțin tehnic, aceeași interfață poate afișa comenzi simple, starea generală a robotului și avertizări vizuale ușor de înțeles.

Astfel, tema acestei lucrări se află la intersecția mai multor direcții moderne: robotica mobilă autonomă, manipularea robotică, ecosistemul ROS2, planificarea mișcărilor cu MoveIt2, vizualizarea în Unity și interacțiunea prin realitate augmentată. Alegerea acestei teme a pornit de la ideea că un robot mobil cu braț de manipulare nu trebuie privit doar ca un ansamblu mecanic și software, ci ca un sistem integrat care trebuie să poată fi folosit și înțeles de către oameni.

## Manipularea mobilă autonomă și rolul ei în sistemele robotice moderne

Manipularea mobilă autonomă reprezintă o extensie naturală a roboticii mobile. O platformă mobilă autonomă poate naviga într-un mediu cunoscut sau necunoscut, poate evita obstacole și poate ajunge la un punct de interes. Totuși, fără un sistem de manipulare, aceasta rămâne limitată la activități de transport, inspecție sau supraveghere. Prin integrarea unui braț robotic, platforma capătă posibilitatea de a interacționa fizic cu mediul, de a ridica obiecte, de a le muta, de a le sorta sau de a le așeza în poziții definite [12], [13], [27].

Această combinație dintre mobilitate și manipulare este importantă deoarece multe sarcini reale nu se desfășoară într-un spațiu fix. Într-un depozit, obiectele pot fi așezate în zone diferite. Într-un laborator, componentele pot fi mutate între mese, rafturi sau echipamente. Într-un mediu industrial flexibil, poziția obiectelor se poate schimba în funcție de fluxul de producție. În aceste cazuri, un braț fix nu este suficient, iar o platformă mobilă fără braț nu poate finaliza sarcina. Sistemul rezultat trebuie să combine navigarea cu manipularea, iar această combinație ridică probleme tehnice specifice.

Prima problemă importantă este amplasarea brațului pe platformă. Brațul trebuie poziționat astfel încât să aibă un spațiu de lucru util cât mai mare, să poată ajunge la obiectul care urmează să fie ridicat, dar și la zona în care obiectul trebuie plasat. În același timp, montarea brațului modifică centrul de greutate al platformei, poate afecta stabilitatea în timpul deplasării și poate influența accesul la senzori, cabluri sau alte componente. Din acest motiv, analiza amplasamentului nu este doar o etapă de proiectare mecanică, ci o etapă de integrare a întregului sistem.

A doua problemă este legată de coordonarea dintre subsistemul de navigare și subsistemul de manipulare. Platforma mobilă trebuie să ajungă într-o poziție potrivită pentru ca brațul să poată executa mișcarea. Dacă robotul se oprește prea departe, brațul nu va ajunge la obiect. Dacă se oprește într-o orientare nepotrivită, soluția de cinematică inversă poate deveni dificilă sau imposibilă. De aceea, task-ul complet nu poate fi tratat ca două activități complet separate, ci ca un scenariu integrat: navigare autonomă către punctul de interes, poziționare, manipulare și reluarea navigării.

A treia problemă este legată de planificarea mișcării brațului. Un braț robotic trebuie să respecte limitele articulațiilor, să evite coliziunile cu platforma, cu mediul și cu obiectele, și să execute o mișcare suficient de precisă pentru a prinde obiectul. Framework-uri precum MoveIt2 sunt folosite pentru planificarea mișcării, calculul cinematicii și integrarea cu controlul robotului [13]. Pentru sarcini mai complexe, formate din mai multe etape, MoveIt2 Task Constructor oferă o abordare structurată, în care task-ul este împărțit în stagii precum deschiderea gripperului, apropierea de obiect, prinderea, ridicarea, deplasarea către zona de plasare și eliberarea obiectului [14].

În cazul lucrării de față, scenariul ales este un task de tip pick and place autonom, în care obiectul este preluat de pe jos și așezat într-un coș montat pe platformă. Alegerea acestui scenariu este justificată deoarece el pune în evidență principalele probleme ale manipulării mobile: poziționarea platformei, accesibilitatea obiectului, spațiul de lucru al brațului, integrarea mecanică a coșului, planificarea mișcării și coordonarea software a mai multor subsisteme. Deși task-ul pare simplu la nivel intuitiv, implementarea sa pe hardware real implică numeroase ajustări și verificări.

Un aspect important în dezvoltarea unui astfel de sistem este validarea treptată. Înainte de testarea fizică, modelul robotului poate fi verificat în simulare, de exemplu în Gazebo, pentru a observa dacă descrierea URDF este corectă, dacă articulațiile sunt configurate corespunzător și dacă mișcările planificate nu produc coliziuni [18]. Simularea nu înlocuiește testarea fizică, deoarece în mediul real apar toleranțe mecanice, erori de calibrare, latențe și limitări ale actuatorilor, dar ajută la reducerea numărului de încercări riscante pe robotul real.

În acest proiect, platforma mobilă autonomă utilizată este o resursă existentă, dezvoltată anterior în cadrul FIIR-UNSTPB, iar brațul de manipulare OMX-F este un kit comercial ROBOTIS pus la dispoziție de conducătorul științific [19], [20], [21]. Contribuția lucrării nu constă în proiectarea de la zero a platformei mobile sau a brațului robotic, ci în integrarea lor într-un sistem funcțional, în analiza amplasamentului brațului, în configurarea software în ROS2 Jazzy, în implementarea task-ului de manipulare și în realizarea unei interfețe de vizualizare prin Unity și AR.

## Realitatea augmentată în interacțiunea om-robot

Interacțiunea om-robot este una dintre componentele care fac diferența între un prototip tehnic și un sistem utilizabil. Un robot poate avea algoritmi performanți, poate naviga corect și poate executa mișcări precise, dar dacă utilizatorul nu poate înțelege ce face robotul sau nu poate interveni într-un mod clar, sistemul devine greu de folosit. Din acest motiv, interfața nu trebuie privită ca un element secundar, ci ca o parte a arhitecturii generale.

În cazul roboților mobili autonomi, interfața trebuie să ofere informații despre poziția robotului, starea navigării, obiectivele curente, erorile apărute și eventualele comenzi disponibile. În cazul unui robot mobil cu braț de manipulare, apar informații suplimentare: poziția articulațiilor, starea gripperului, traiectoria planificată, obiectul vizat, poziția de pre-grasp, poziția de place și rezultatul fiecărei etape a task-ului. Dacă toate aceste informații sunt afișate doar sub formă de valori numerice sau topicuri, utilizatorul are nevoie de experiență tehnică pentru a le interpreta.

Realitatea augmentată oferă o metodă mai naturală de reprezentare a acestor informații. Prin AR, utilizatorul poate vedea modelul virtual al robotului suprapus peste mediul real, poate urmări direcția de deplasare sau traiectoria planificată și poate primi feedback vizual direct în câmpul său vizual [2], [5]. În loc să urmărească simultan un terminal, o fereastră RViz, o scenă Unity și robotul fizic, operatorul poate primi o parte din informații direct în spațiul în care se află robotul.

O astfel de abordare este utilă mai ales pentru sisteme complexe, unde există multe surse de date. De exemplu, într-un scenariu de pick and place, interfața AR poate afișa obiectul detectat, zona în care robotul trebuie să se poziționeze, traiectoria brațului și starea fiecărui stagiu al task-ului. Dacă sistemul nu reușește să planifice mișcarea, interfața poate marca vizual problema: obiectul este în afara spațiului de lucru, există o coliziune, gripperul nu este deschis sau robotul nu este aliniat corespunzător.

În plus, AR poate fi folosită nu doar pentru vizualizare, ci și pentru control sau pentru colectarea demonstrațiilor. În loc să se folosească un sistem leader-follower fizic, în care un braț sau un dispozitiv separat este manipulat de operator, mișcările mâinii sau ale controlerului din spațiul AR pot fi capturate și transformate în demonstrații pentru un sistem de învățare prin imitare. Această direcție este încă una de dezvoltare și cercetare, deoarece apar probleme de calibrare, latență și precizie, dar este promițătoare pentru aplicații în care flexibilitatea este mai importantă decât rigiditatea unui echipament dedicat [2], [5].

În cadrul acestei lucrări, componenta AR are două roluri. Primul rol este de vizualizare și demonstrare parțială a sistemului robot prin Meta Quest 3, folosind o scenă Unity conectată cu ecosistemul ROS2. Al doilea rol este de direcție viitoare, prin proiectarea unei arhitecturi care poate permite colectarea demonstrațiilor prin AR. Implementarea completă a colectării demonstrațiilor nu face parte din obiectivul final al acestei etape, însă arhitectura este analizată pentru a arăta modul în care sistemul poate fi extins.

Pentru dezvoltarea componentei de vizualizare, Unity reprezintă o alegere potrivită deoarece oferă suport pentru modele 3D, scene interactive, integrare cu dispozitive XR și pachete dedicate comunicării cu ROS [9], [15], [16]. Prin intermediul ROS-TCP-Connector sau al componentelor din Unity Robotics Hub, datele din ROS2 pot fi transmise către Unity, unde sunt reprezentate sub formă de obiecte, transformări și animații [9], [15]. Astfel, starea articulațiilor brațului, poziția platformei, odometria sau alte mesaje ROS2 pot fi vizualizate într-un mediu grafic.

Meta Quest 3 oferă suport pentru aplicații de realitate mixtă, ceea ce permite combinarea mediului real cu elemente virtuale [17]. În contextul acestei lucrări, acest lucru înseamnă posibilitatea de a vedea robotul sau un model al acestuia în spațiul real, de a afișa panouri de control și de a construi o interfață mai apropiată de modul natural în care utilizatorul percepe mediul. Deși partea de AR este implementată parțial, ea este importantă deoarece diferențiază lucrarea de o simplă integrare hardware-software și adaugă o componentă de interacțiune modernă.

## Ecosistemul ROS2, MoveIt2, Nav2 și Unity

Pentru realizarea unui sistem robotizat complex este necesar un ecosistem software care să permită comunicarea între senzori, actuatori, algoritmi de planificare și interfețe de utilizator. În prezent, ROS2 este una dintre cele mai utilizate platforme pentru dezvoltarea aplicațiilor robotice, datorită arhitecturii distribuite, comunicării prin topicuri, servicii și acțiuni, dar și datorită comunității și pachetelor existente [10], [11]. ROS2 a fost proiectat pentru aplicații mai robuste și mai flexibile decât generația anterioară ROS1, având suport mai bun pentru sisteme distribuite și pentru cerințe moderne de comunicație [10].

În cadrul acestei lucrări se utilizează ROS2 Jazzy, deoarece platforma mobilă existentă și componentele de integrare sunt dezvoltate în acest ecosistem [11]. ROS2 are rolul de coloană vertebrală software pentru sistem. Prin el se transmit datele de la senzori, comenzile pentru platformă, starea brațului, acțiunile de navigare, rezultatele planificării și informațiile necesare interfeței Unity. Faptul că subsistemele comunică prin interfețe standardizate permite dezvoltarea modulară și testarea separată a componentelor.

Pentru navigarea autonomă a platformei se utilizează Nav2, stack-ul de navigare pentru ROS2 [12]. Nav2 oferă componente pentru localizare, planificare globală, planificare locală, control, evitare obstacole și executarea acțiunilor de tip NavigateToPose. Platforma mobilă folosită în proiect are deja un stack de navigare existent, iar lucrarea urmărește integrarea brațului și a task-ului de manipulare fără modificarea fundamentală a acestui stack. Acest lucru este important deoarece proiectul pornește de la o platformă reală existentă, nu de la o simulare ideală.

Pentru brațul robotic, MoveIt2 este framework-ul principal de planificare a mișcării [13]. MoveIt2 permite definirea modelului cinematic al robotului, configurarea grupurilor de planificare, calculul traiectoriilor și verificarea coliziunilor. Într-un task de pick and place, aceste funcții sunt necesare pentru ca brațul să se poată apropia de obiect, să îl prindă și să îl mute în coș. În plus, MoveIt2 se integrează cu ros2_control, ceea ce permite transmiterea comenzilor către hardware-ul fizic.

MoveIt2 Task Constructor este folosit pentru a organiza task-ul de manipulare în etape logice [14]. Această abordare este mai clară decât o comandă unică de mișcare, deoarece task-ul este împărțit în stagii care pot fi evaluate separat. De exemplu, pentru task-ul propus în lucrare pot exista stagii precum Current State, Open Gripper, Move To Pre-Grasp, Grasp, Pick, Move To Place, Place, Open Gripper și Return Home. Dacă un stagiu eșuează, se poate identifica mai ușor cauza și se pot ajusta parametrii corespunzători.

Gazebo este utilizat ca mediu de simulare pentru verificarea modelului și a comportamentului înainte de testarea pe hardware fizic [18]. Simularea are rolul de a reduce riscurile, de a testa descrierea robotului și de a observa dacă task-ul MTC poate fi executat în condiții controlate. Totuși, implementarea finală trebuie validată pe robotul real, deoarece hardware-ul introduce limitări care nu sunt întotdeauna reprezentate complet în simulator.

Unity și ROS-TCP-Connector formează partea de vizualizare și interfață [9], [15], [16]. Prin Unity se construiește o scenă 3D care include robotul mobil, brațul OMX-F, mediul de lucru, obiectul și coșul. Datele primite din ROS2 sunt folosite pentru a actualiza poziția elementelor din scenă, astfel încât utilizatorul să poată urmări starea sistemului într-un mod vizual. Această componentă reprezintă o punte între lumea roboticii, care este bazată pe topicuri, acțiuni și transformări, și lumea interfețelor grafice, care este mai ușor de înțeles de către utilizator.

Integrarea acestor tehnologii nu este doar o alăturare de pachete software. Fiecare componentă are propriile constrângeri: ROS2 are structura sa de noduri și mesaje, Nav2 lucrează cu hărți și acțiuni de navigare, MoveIt2 lucrează cu modele cinematice și scene de coliziune, iar Unity lucrează cu obiecte 3D, frame rate și coordonate specifice mediului grafic. De aceea, o parte importantă a lucrării constă în definirea fluxurilor de date, a interfețelor dintre module și a modului în care scenariul complet este orchestrat.

## Provocări tehnice ale integrării propuse

Integrarea unei platforme mobile autonome cu un braț robotic și cu o interfață AR presupune mai multe provocări tehnice care trebuie tratate încă din etapa de proiectare. Prima provocare este legată de diferența dintre un sistem analizat separat și un sistem integrat. Atunci când platforma mobilă este testată singură, criteriile principale sunt navigarea, localizarea și evitarea obstacolelor. Atunci când brațul este testat separat, criteriile principale sunt planificarea mișcării, controlul articulațiilor și precizia gripperului. După integrare, aceste criterii se influențează reciproc. Masa brațului poate schimba comportamentul platformei, poziția platformei poate limita spațiul de lucru al brațului, iar task-ul de manipulare poate impune condiții mai stricte de poziționare decât navigarea simplă.

A doua provocare este reprezentată de sistemele de coordonate. În robotică, fiecare componentă este definită într-un anumit frame: baza platformei, baza brațului, end-effectorul, camera, LiDAR-ul, harta și obiectul manipulat. Pentru ca robotul să execute corect task-ul, transformările dintre aceste frame-uri trebuie să fie coerente. O eroare mică în poziția brațului față de platformă poate produce o eroare mai mare la nivelul gripperului. În același timp, Unity și mediul AR folosesc propriul sistem de coordonate, ceea ce înseamnă că datele primite din ROS2 trebuie transformate într-un mod corect pentru vizualizare [9], [15], [16].

A treia provocare este legată de diferența dintre simulare și hardware-ul real. În simulare, modelul robotului poate fi ideal, fără jocuri mecanice, fără cabluri care limitează mișcarea, fără variații ale actuatorilor și fără erori de calibrare. Pe robotul real, aceste elemente apar în mod natural. De aceea, un task care funcționează în Gazebo nu este automat garantat pe hardware fizic [18]. În lucrarea de față, simularea este tratată ca o etapă necesară, dar nu ca o validare finală. Validarea finală trebuie realizată prin teste pe robotul fizic, cu obiectul și coșul real.

A patra provocare este latența. Într-un sistem distribuit, datele sunt transmise între noduri ROS2, controlere, Unity și dispozitivul AR. Pentru vizualizare, o latență moderată poate fi acceptabilă, deoarece utilizatorul urmărește starea sistemului. Pentru control direct sau colectarea demonstrațiilor, latența devine mult mai importantă, deoarece o întârziere între mișcarea operatorului și reacția robotului poate afecta precizia și siguranța [2], [5]. Din acest motiv, în lucrare componenta AR este tratată în principal ca vizualizare și demonstrație parțială, iar colectarea demonstrațiilor este propusă ca direcție viitoare.

A cincea provocare este siguranța în exploatare. Chiar dacă sistemul este dezvoltat într-un mediu de laborator, robotul are componente mobile și poate interacționa cu obiecte reale. Mișcarea platformei și mișcarea brațului trebuie coordonate astfel încât să se evite coliziunile. În plus, operatorul trebuie să știe când robotul execută un task, când a eșuat un stagiu și când este sigur să intervină. O interfață vizuală poate ajuta în acest sens, deoarece face starea sistemului mai ușor de observat.

O altă provocare este alegerea nivelului potrivit de automatizare. Un sistem complet autonom este atractiv din punct de vedere tehnic, dar în practică este util ca operatorul să poată vedea și înțelege deciziile robotului. În această lucrare, automatizarea este folosită pentru navigare și manipulare, iar interfața este folosită pentru vizualizare, control și feedback. Această combinație se potrivește cu direcția Industry 5.0, unde robotul nu înlocuiește complet operatorul, ci lucrează într-un sistem în care omul rămâne parte a procesului [4], [6].

Din punct de vedere software, provocarea principală este orchestrarea. Nav2 funcționează prin acțiuni de navigare, MoveIt2 Task Constructor funcționează prin stagii de manipulare, iar Unity funcționează prin actualizarea unei scene grafice. Pentru ca sistemul să fie coerent, este necesar un flux clar: robotul primește un obiectiv, ajunge la poziția de lucru, se oprește, execută task-ul de manipulare, verifică rezultatul și apoi continuă scenariul. Dacă una dintre etape eșuează, sistemul trebuie să poată raporta starea și să permită diagnosticarea problemei.

Din punct de vedere al utilizatorului, provocarea este ca sistemul să nu devină prea greu de urmărit. Un operator nu trebuie să fie obligat să citească permanent loguri sau să interpreteze valori numerice pentru a înțelege dacă robotul funcționează corect. Aici intervine rolul interfeței Unity și AR. Prin reprezentări vizuale, starea sistemului poate fi comunicată mai clar. De exemplu, poziția robotului, poziția brațului, obiectul țintă și coșul pot fi afișate într-o scenă 3D, iar informațiile relevante pot fi organizate în panouri.

Aceste provocări justifică abordarea integrată a lucrării. Proiectul nu urmărește doar testarea separată a unui braț sau a unei platforme mobile, ci construirea unui sistem în care componentele comunică și depind unele de altele. Din acest motiv, fiecare decizie de proiectare trebuie analizată nu doar local, ci și prin efectul asupra întregului sistem. Poziția brațului influențează task-ul MTC, poziția coșului influențează traiectoria de place, latența bridge-ului influențează calitatea vizualizării, iar stabilitatea platformei influențează repetabilitatea manipulării.

## Motivația temei și relevanța aplicativă

În cadrul acestei lucrări am pornit de la resurse deja existente puse la dispoziție de către conducătorul științific: platforma mobilă autonomă Xplorer-A, dezvoltată în cadrul FIIR-UNSTPB, și brațul robotic de manipulare OMX-F, un kit comercial ROBOTIS cu 5 grade de libertate și gripper [19], [20], [21]. Având la dispoziție aceste resurse, am avut oportunitatea de a realiza o integrare practică între o platformă mobilă autonomă și un braț de manipulare, în loc să rămân doar la nivel de simulare sau de analiză teoretică.

Motivația principală a temei este construirea unui sistem integrat care să demonstreze un flux complet: robotul navighează autonom, ajunge într-o zonă de interes, execută un task de pick and place și oferă utilizatorului posibilitatea de a urmări comportamentul printr-o interfață vizuală în Unity și realitate augmentată. Acest flux este relevant deoarece reproduce, la scară de laborator, probleme întâlnite în aplicații reale de logistică, producție flexibilă sau asistență robotică.

Un alt motiv pentru alegerea temei este faptul că sistemele robotice moderne nu mai pot fi analizate doar separat, pe componente. O platformă mobilă poate funcționa bine individual, iar un braț robotic poate funcționa bine pe banc, însă integrarea lor poate produce probleme noi. Montarea brațului schimbă masa și distribuția greutății, poate modifica comportamentul platformei la deplasare, impune trasee de cablare, influențează poziția obiectelor și necesită o sincronizare software atentă. Din acest motiv, integrarea propriu-zisă este o activitate cu valoare tehnică reală.

Tema este relevantă și din perspectiva educațională. Ea permite utilizarea mai multor tehnologii actuale într-un proiect unitar: proiectare 3D, descriere URDF, ROS2 Jazzy, Nav2, MoveIt2, MoveIt2 Task Constructor, Gazebo, Unity, ROS-TCP-Connector și Meta Quest. Prin combinarea acestor componente se obține o imagine mai apropiată de modul în care sunt dezvoltate sistemele robotice moderne, unde rareori există o singură tehnologie izolată.

De asemenea, proiectul are relevanță aplicativă prin faptul că task-ul ales, pick and place, este unul de bază în robotică, dar rămâne important în multe domenii. Ridicarea unui obiect și plasarea lui într-un container poate reprezenta un caz simplificat pentru sortare, colectare, transport, curățare sau manipulare de componente. În lucrarea de față, obiectul este preluat de pe jos și așezat într-un coș montat pe platformă, ceea ce permite testarea atât a brațului, cât și a modului în care acesta este poziționat față de platformă.

Interfața AR este motivată de nevoia de a face sistemul mai ușor de înțeles. În mod obișnuit, dezvoltarea robotică folosește instrumente precum terminale, RViz, grafice, loguri și fișiere de configurare. Acestea sunt foarte utile pentru dezvoltatori, dar nu sunt întotdeauna intuitive pentru un utilizator final. Prin Unity și Meta Quest se poate construi o interfață mai prietenoasă, în care robotul, obiectele și stările sistemului sunt reprezentate vizual. Astfel, componenta AR nu este adăugată doar pentru efect vizual, ci pentru a apropia sistemul de conceptul de interacțiune om-robot modernă [2], [4], [5].

Din punct de vedere al originalității, lucrarea se delimitează clar de componentele existente. Platforma mobilă autonomă nu este proiectată de la zero în cadrul acestei lucrări, iar brațul OMX-F este un kit comercial. Contribuțiile proprii sunt legate de analiza poziției optime a brațului pe platformă, integrarea mecanică și software, adaptarea modelului robotului pentru noua configurație, implementarea task-ului de manipulare cu MoveIt2 Task Constructor, realizarea bridge-ului ROS2-Unity și proiectarea arhitecturii de realitate augmentată.

Această delimitare este importantă deoarece arată exact unde se află contribuția lucrării. În proiectele de robotică, folosirea unor platforme existente nu reduce valoarea lucrării, atâta timp cât integrarea, configurarea, testarea și dezvoltarea scenariului sunt activități proprii. Din contră, utilizarea unor componente reale existente apropie proiectul de situațiile întâlnite în industrie, unde inginerul trebuie să combine echipamente, biblioteci și framework-uri diferite într-un sistem funcțional.

## Obiectivele proiectului

Plecând de la tema principală menționată anterior, lucrarea are ca obiectiv general proiectarea și implementarea unui sistem integrat de manipulare autonomă și interfață de realitate augmentată pentru un robot mobil cu braț de manipulare, în ecosistemul ROS2 Jazzy. Acest obiectiv general este împărțit în mai multe obiective specifice, fiecare corespunzând unei etape importante din dezvoltarea sistemului.

Primul obiectiv este analiza și identificarea poziției optime a brațului OMX-F pe platforma mobilă autonomă. Pentru acest obiectiv, în prima etapă se analizează variantele posibile de montare a brațului, ținând cont de spațiul de lucru, stabilitatea platformei, accesul la obiectul de pe jos, poziția coșului și traseul cablurilor. Această etapă este esențială deoarece poziția aleasă influențează toate etapele următoare. Dacă brațul este montat într-o poziție nepotrivită, task-ul de pick and place poate deveni dificil sau chiar imposibil, indiferent de calitatea algoritmilor software.

Al doilea obiectiv este integrarea fizică și software a brațului OMX-F pe platformă în ecosistemul ROS2 Jazzy. Integrarea fizică presupune montarea mecanică a brațului, fixarea corespunzătoare, alimentarea și verificarea comunicației cu actuatorii Dynamixel [23]. Integrarea software presupune configurarea pachetelor ROS2 pentru braț, adaptarea descrierii robotului, configurarea MoveIt2 și verificarea comunicației dintre componente [13], [19], [21]. Această etapă transformă brațul dintr-un kit separat într-o parte funcțională a sistemului mobil.

Al treilea obiectiv este implementarea task-ului de pick and place autonom cu MoveIt2 Task Constructor. Pentru acest obiectiv, task-ul este împărțit în stagii logice, cum ar fi deschiderea gripperului, deplasarea către poziția de pre-grasp, prinderea obiectului, ridicarea, deplasarea către coș și eliberarea obiectului [14]. Această abordare permite testarea fiecărei etape și ajustarea parametrilor geometrici în funcție de rezultatele obținute în simulare și pe hardware fizic. Task-ul ales este important deoarece demonstrează interacțiunea reală a robotului cu mediul.

Al patrulea obiectiv este implementarea unui bridge ROS2-Unity pentru vizualizarea și controlul robotului din Unity. Pentru această etapă se utilizează pachete dedicate comunicării dintre ROS și Unity, precum Unity Robotics Hub și ROS-TCP-Connector [9], [15]. Prin această conexiune, starea robotului poate fi transmisă către scena Unity, unde este reprezentată grafic. În același timp, anumite comenzi pot fi trimise din Unity către ROS2, ceea ce permite o formă de control și interacțiune cu sistemul.

Al cincilea obiectiv este proiectarea arhitecturii interfeței AR cu Meta Quest pentru vizualizare în realitate augmentată și demonstrarea parțială a acesteia. În faza de proiectare, accentul este pus pe o interfață intuitivă, care să permită utilizarea aplicației și de către persoane care nu au un background tehnic avansat. Meta Quest și Unity oferă cadrul necesar pentru dezvoltarea unei aplicații de realitate mixtă, iar sistemul ROS2-Unity oferă datele care trebuie vizualizate [16], [17].

Al șaselea obiectiv este integrarea scenariului complet: navigare autonomă cu Nav2, execuție pick and place cu MoveIt2 Task Constructor și reluarea navigării [12], [14]. Acest obiectiv este etapa de validare a întregului sistem, deoarece verifică dacă subsistemele pot funcționa împreună. Robotul trebuie să navigheze către un punct de interes, să se poziționeze corespunzător, să execute task-ul de manipulare și apoi să continue scenariul. Reușita acestui obiectiv demonstrează că sistemul nu este doar o colecție de module, ci un ansamblu integrat.

Pe lângă aceste obiective principale, lucrarea urmărește și documentarea procesului de dezvoltare, testarea componentelor și identificarea limitărilor. Deoarece proiectul include componente hardware și software, este normal ca în timpul implementării să apară probleme legate de compatibilitate, calibrare, latență sau precizie. Documentarea acestor probleme și a soluțiilor aplicate face parte din valoarea lucrării, deoarece arată parcursul real al dezvoltării, nu doar rezultatul final.

## Stadiul actual privind tematica proiectului

Stadiul actual al domeniului arată că robotica mobilă, manipularea robotică și interfețele imersive evoluează într-o direcție comună. Pe de o parte, platformele mobile devin mai autonome datorită progresului în localizare, cartografiere, planificare de traseu și fuziune senzorială [12], [24], [25], [28]. Pe de altă parte, brațele robotice devin mai accesibile prin kit-uri educaționale și comerciale, iar framework-uri precum MoveIt2 reduc efortul necesar pentru implementarea planificării de mișcare [13], [19].

În literatura de specialitate și în aplicațiile recente se observă o tendință de integrare a componentelor existente în sisteme robotice modulare. ROS2 joacă un rol important în această direcție, deoarece permite comunicarea standardizată între noduri și reutilizarea pachetelor existente [10], [11]. Nav2 este folosit pentru navigarea autonomă a roboților mobili, iar MoveIt2 pentru manipulare [12], [13]. Această separare pe module permite dezvoltarea independentă, dar și integrarea într-un scenariu complet.

MoveIt2 Task Constructor este relevant pentru task-uri de manipulare structurate, deoarece permite descrierea unei sarcini complexe prin etape succesive [14]. În loc ca dezvoltatorul să trateze task-ul ca o singură problemă mare, acesta poate analiza fiecare stagiu separat. Pentru un task pick and place, această abordare este potrivită, deoarece prinderea obiectului, ridicarea și plasarea lui într-un coș au constrângeri diferite. De exemplu, apropierea de obiect poate necesita o anumită orientare a gripperului, în timp ce plasarea în coș poate necesita evitarea coliziunii cu marginile acestuia.

În zona de interacțiune om-robot, cercetările recente arată interesul pentru utilizarea realității augmentate în vizualizare, control și colaborare [2], [5]. AR poate oferi operatorului informații contextuale direct în mediul de lucru, ceea ce poate reduce nevoia de a interpreta date tehnice complexe. În același timp, AR poate fi utilizată pentru instruire, simulare, validare de traiectorii și chiar pentru demonstrații ale mișcărilor dorite [2]. Această direcție este importantă mai ales în scenarii în care robotul trebuie să colaboreze cu oameni, nu să lucreze complet izolat.

Unity este frecvent utilizat pentru dezvoltarea de aplicații interactive și XR, iar pachetele de conectare cu ROS permit integrarea datelor robotice în scene 3D [9], [15], [16]. Această combinație este utilă pentru proiecte în care se dorește o reprezentare vizuală a robotului sau o interfață mai accesibilă decât instrumentele clasice. În lucrarea de față, Unity este folosit pentru vizualizarea sistemului robot și ca bază pentru interfața AR.

În ceea ce privește platforma mobilă autonomă utilizată ca bază de lucru, există deja cercetări și dezvoltări în cadrul FIIR-UNSTPB privind localizarea, navigarea și planificarea traseelor pentru roboți mobili [24], [25]. Aceste lucrări oferă contextul în care platforma Xplorer-A este utilizată. Prezenta lucrare nu urmărește reconstruirea acestor funcții, ci extinderea platformei prin integrarea unui braț de manipulare și a unei interfețe AR.

Brațul ROBOTIS OMX-F este un kit comercial care include componente hardware și documentație pentru asamblare, operare și simulare [19], [20], [21], [22]. Acest lucru permite pornirea de la o bază tehnică existentă, însă integrarea pe o platformă mobilă impune modificări și adaptări. Documentația oficială este utilă pentru înțelegerea structurii brațului și a modului de operare, dar nu rezolvă automat problemele specifice proiectului, cum ar fi poziționarea brațului pe platformă, definirea coșului, configurarea task-ului MTC sau sincronizarea cu Nav2.

Lacuna pe care lucrarea o adresează este tocmai această integrare practică într-un sistem unitar. Există documentație pentru platforme mobile, pentru brațe robotice, pentru MoveIt2, pentru Unity și pentru AR, dar provocarea apare atunci când toate aceste componente trebuie să funcționeze împreună pe un robot real. Lucrarea își propune să demonstreze un flux complet și să documenteze deciziile tehnice necesare pentru ca sistemul să fie funcțional.

## Delimitarea contribuțiilor proprii

Pentru claritatea lucrării, este importantă delimitarea contribuțiilor proprii față de resursele existente. Platforma mobilă autonomă Xplorer-A este un sistem existent, dezvoltat anterior în cadrul FIIR-UNSTPB. Ea reprezintă baza de lucru pentru proiect, iar contribuțiile acestei lucrări nu includ proiectarea sau construcția platformei mobile. În schimb, lucrarea analizează modul în care această platformă poate fi extinsă prin adăugarea unui braț de manipulare și prin integrarea unui scenariu de manipulare autonomă.

Brațul OMX-F este un kit comercial ROBOTIS, pus la dispoziție pentru realizarea proiectului [19], [20]. Contribuția lucrării nu constă în proiectarea hardware a brațului, ci în asamblarea, configurarea, amplasarea și integrarea lui în sistemul robot mobil. Această diferență este importantă deoarece un kit comercial oferă componente și documentație, dar integrarea lui într-o configurație nouă necesită analiză, adaptare și testare.

O contribuție importantă este studiul de amplasament al brațului pe platformă. Această etapă presupune evaluarea mai multor variante de poziționare și alegerea soluției care oferă un compromis potrivit între spațiul de lucru, stabilitate, accesibilitate și funcționalitate. Rezultatul acestei analize influențează poziția coșului, scenariul de pick and place, configurația URDF și parametrii de planificare.

A doua contribuție este integrarea hardware și software a brațului cu platforma mobilă. Aceasta include montarea fizică, conectarea electrică, configurarea comunicației, adaptarea modelului robotului și verificarea funcționării în ROS2 Jazzy. Integrarea este o etapă practică, în care apar adesea probleme care nu pot fi observate doar din documentație: poziții mecanice greu accesibile, cabluri prea scurte, interferențe între componente sau diferențe între modelul teoretic și sistemul real.

A treia contribuție este implementarea task-ului de pick and place cu MoveIt2 Task Constructor. Această componentă software definește modul în care brațul execută sarcina de manipulare și permite testarea etapelor individuale. Alegerea MoveIt2 Task Constructor este justificată de caracterul multi-stagiu al task-ului și de nevoia de a avea o structură clară pentru planificare și depanare [14].

A patra contribuție este implementarea bridge-ului ROS2-Unity și construirea scenei de vizualizare. Această etapă conectează ecosistemul robotic cu o interfață grafică, ceea ce permite urmărirea stării robotului într-un mod mai intuitiv. Prin Unity se pot reprezenta platforma, brațul, obiectul și coșul, iar prin conexiunea cu ROS2 se poate actualiza scena în timp real [9], [15].

A cincea contribuție este proiectarea arhitecturii AR cu Meta Quest și demonstrarea parțială a vizualizării în realitate mixtă. Această componentă oferă o direcție modernă de dezvoltare și creează baza pentru extensii ulterioare, cum ar fi colectarea demonstrațiilor prin mișcările operatorului în spațiul AR. Deși implementarea completă a acestei direcții rămâne pentru dezvoltări viitoare, includerea arhitecturii arată modul în care sistemul poate evolua.

## Structura lucrării

Lucrarea de față este organizată astfel încât să urmărească procesul complet de dezvoltare a sistemului, de la proiectare până la implementare și testare. Structura este împărțită în trei capitole principale, urmate de concluzii finale, bibliografie și documentație grafică.

Capitolul 1, intitulat „Proiectarea sistemului integrat de manipulare autonomă și interfață AR”, prezintă etapa de proiectare. În acest capitol sunt descrise platforma mobilă existentă, brațul robotic OMX-F, cadrul MoveIt2 și MoveIt2 Task Constructor, cadrul ROS2-Unity și conceptele de realitate augmentată. De asemenea, sunt definite cerințele și restricțiile de proiectare, analiza funcțională a sistemului, arhitectura hardware și software, scenariul de simulare și estimarea costurilor. Capitolul are rolul de a justifica deciziile tehnice înainte de implementare.

Capitolul 2, „Realizarea și implementarea sistemului”, descrie etapele practice prin care proiectul este transformat dintr-o arhitectură propusă într-un sistem funcțional. Aici sunt prezentate analiza poziției optime a brațului pe platformă, integrarea fizică a brațului, configurarea mediului software, implementarea task-ului pick and place, implementarea bridge-ului ROS2-Unity, dezvoltarea componentei AR și integrarea scenariului Nav2 cu MTC. Capitolul include și documentarea problemelor întâlnite și a soluțiilor aplicate.

Capitolul 3, „Testarea și validarea sistemului”, prezintă modul în care sistemul este verificat. Testarea include atât componente individuale, cât și scenariul integrat end-to-end. Sunt analizate teste funcționale, teste de performanță, teste de robustețe și teste de integrare. Printre metricile relevante se numără rata de succes a task-ului pick and place, timpul de execuție, precizia poziționării și latența bridge-ului Unity. Scopul capitolului este de a evalua dacă sistemul îndeplinește obiectivele definite și de a identifica limitările rămase.

Concluziile finale sintetizează contribuțiile lucrării, rezultatele obținute și direcțiile de dezvoltare ulterioară. Printre direcțiile viitoare se numără implementarea completă a colectării demonstrațiilor prin AR, extinderea task-urilor de manipulare, îmbunătățirea robusteții și compararea performanței cu alte metode de control sau demonstrație.

Bibliografia include sursele utilizate pentru fundamentarea teoretică și tehnică a lucrării. Sursele sunt citate în text prin numere în paranteze pătrate, conform cerințelor de redactare. Documentația grafică va include diagrame, scheme, capturi și fotografii realizate în timpul proiectului, cu menționarea explicită a sursei pentru fiecare material.

Prin această structură, lucrarea urmărește să prezinte nu doar rezultatul final, ci și raționamentul tehnic din spatele fiecărei decizii. Sistemul propus combină tehnologii existente într-o arhitectură proprie, orientată spre manipulare autonomă, vizualizare intuitivă și posibilitatea extinderii către interacțiune prin realitate augmentată.

## Bibliografie

[1] Robotnik. (2025). Robotic trends in 2025: Innovations transforming industries. https://robotnik.eu/robotic-trends-in-2025-innovations-transforming-industries/

[2] Suzuki, R., Karim, A., Xia, T., Hedayati, H., & Marquardt, N. (2022). Augmented Reality and Robotics: A Survey and Taxonomy for AR-enhanced Human-Robot Interaction and Robotic Interfaces. https://doi.org/10.1145/3491102.3517719

[3] Mocanu, I., & Nițu, G.-C. (2026). Human-Robot Interaction: Real-Time Control of Robotic Systems via ROS2 and Unity. https://doi.org/10.1007/978-3-032-12481-4_5

[4] Yitmen, I., & Almusaed, A. (2024). Synopsis of Industry 5.0 Paradigm for Human-Robot Collaboration. https://doi.org/10.5772/intechopen.1005583

[5] Woo, S., Kim, Y., & Kim, S. (2025). Converging Extended Reality and Robotics for Innovation in the Food Industry. AgriEngineering, 7, 322. https://doi.org/10.3390/agriengineering7100322

[6] Huang, S., Wang, B., Li, X., Zheng, P., Mourtzis, D., & Wang, L. (2022). Industry 5.0 and Society 5.0 - Comparison, complementation and co-evolution. Journal of Manufacturing Systems, 64, 424-428.

[7] Lyu, Z. (2023). Digital Twins in Industry 5.0. Research, 6. https://doi.org/10.34133/research.0071

[8] Ślusarczyk, B., Tvaronavičienė, M., Haque, A. U., & Oláh, J. (2020). Predictors of Industry 4.0 technologies affecting logistic enterprises' performance: International perspective from economic lens. Technological and Economic Development of Economy, 26(6), 1263-1283.

[9] Unity Technologies. (2024). Unity Robotics Hub. https://github.com/Unity-Technologies/Unity-Robotics-Hub

[10] Macenski, S., Foote, T., Gerkey, B., Lalancette, C., & Woodall, W. (2022). Robot Operating System 2: Design, architecture, and uses in the wild. Science Robotics, 7(66). https://doi.org/10.1126/scirobotics.abm6074

[11] Open Robotics. (2024). ROS 2 Jazzy Jalisco - Documentation. https://docs.ros.org/en/jazzy/

[12] Open Robotics. (2024). Nav2 - Navigation Stack for ROS 2. https://docs.nav2.org/

[13] MoveIt. (2024). MoveIt 2 - Documentation. https://moveit.picknik.ai/main/doc/how_to_guides/how_to_guides.html

[14] MoveIt. (2024). MoveIt Task Constructor - Documentation. https://moveit.picknik.ai/main/doc/how_to_guides/pick_and_place_with_moveit_task_constructor/pick_and_place_with_moveit_task_constructor.html

[15] Unity Technologies. (2024). ROS-TCP-Connector - GitHub Repository. https://github.com/Unity-Technologies/ROS-TCP-Connector

[16] Unity Technologies. (2024). Unity - Documentation. https://docs.unity3d.com/

[17] Meta. (2024). Meta Quest Developer Documentation. https://developer.meta.com/quest/

[18] Open Robotics. (2024). Gazebo - ROS 2 Integration Documentation. https://gazebosim.org/docs

[19] ROBOTIS. (2025). OMX - Introduction and Specifications. https://ai.robotis.com/omx/introduction_omx.html

[20] ROBOTIS. (2025). OMX-F - Assembly Guide. https://ai.robotis.com/omx/assembly_guide_omx.html

[21] ROBOTIS. (2025). OMX-F - Operation Guide ROS 2. https://ai.robotis.com/omx/operation_omx.html

[22] ROBOTIS. (2025). OMX-F - Simulation with Gazebo. https://ai.robotis.com/omx/gazebo_omx.html

[23] ROBOTIS. (2023). Dynamixel Actuators - Technical Documentation. https://emanual.robotis.com/docs/en/dxl/

[24] Abaza, B. F. (2025). AI-Driven Dynamic Covariance for ROS 2 Mobile Robot Localization. Sensors, 25, 3026. https://doi.org/10.3390/s25103026

[25] Abaza, B. F., Staicu, A.-A., & Doicin, C. V. (2026). Lightweight Semantic-Aware Route Planning on Edge Hardware for Indoor Mobile Robots: Monocular Camera-2D LiDAR Fusion with Penalty-Weighted Nav2 Route Server Replanning. Sensors, 26(7), 2232. https://doi.org/10.3390/s26072232

[26] Russell, S., & Norvig, P. (2020). Artificial Intelligence: A Modern Approach (4th ed.). Pearson.

[27] Siciliano, B., Sciavicco, L., Villani, L., & Oriolo, G. (2009). Robotics: Modelling, Planning and Control. Springer.

[28] Thrun, S., Burgard, W., & Fox, D. (2005). Probabilistic Robotics. MIT Press.
