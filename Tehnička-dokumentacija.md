# Tehnička dokumentacija
Na ovoj stranici je dostupna tehnička dokumentacija projekta SportsEventPlanner.

# 1. Uvod
Tehnička dokumentacija predstavlja detaljnu specifikaciju korisničkih zahtjeva napisanu prema standardu IEEE Std 830-1998. U uvodu ćemo navesti svrhu i djelokrug projekta te će biti reference koje su korištene. Slijedi opis proizvoda, specifični zahtjevi te detaljan opis dizajna sustava.
## Svrha
Svrha ovog dokumenta je pružiti naručitelju i programerima detaljne informacije o izradi krajnjeg proizvoda. Dokumentacija je vrlo bitna za daljnji razvoj, a uključuje opis aplikacije za vođenje sportskih događaja, specifikaciju korisničkih zahtjeva te tehničku specifikaciju. Također sadrži opise slučajeva korištenja te obilježja i ograničenja aplikacije.
## Djelokrug
Aplikacije se izdaje pod imenom "SportsPlannerApp". Namijenjena je organizatorima događaja i voditeljima timova. Gotov proizvod imati će: 
1. Desktop aplikaciju namijenjenu organizatorima događaja i voditeljima timova  kojom će se kreirati, prijavljivati te voditi evidencija o događajima. 
1. Bazu podataka kojoj se pristupa iz aplikacije
## Reference
Referenca korištena za izradu ovog dokumenta: 
1. IEEE Computer Society, IEEE Recommended Practice for Software Requirements Specifications. Dostupno na Moodle sustavu – kolegij Programsko inženjerstvo
## U poglavljima koja slijede opisano je sljedeće:

1. Opći opis 
1. Funkcionalnosti aplikacije - sumirani opis funkcionalnosti koje aplikacija pruža
1. Karakteristike korisnika - korisnici i njihova prava korištenja
1. Specifični zahtjevi - detaljan opis zahtjeva
1. Opis dizajna sustava -dijagrami i pojedine funkcionalnosti te njihovi dijagrami

# 2. Opći opis

## Funkcionalnosti aplikacije
1. Prijava u sustav - Prilikom pokretanja aplikacije otvara se forma za prijavu u aplikaciju. Popunjavanjem korisničkog imena i lozinke te klikom na gumb "Prijavi se" korisnik se prijavljuje u aplikaciju te mu se otvara glavna forma aplikacije.
1. Registracija u sustav
1. CRUD događaja - Organizator događaja otvara kontrolu Događaji. On klikom na gumb "Unos" može kreirati, "Promijeni" može promijeniti te "Izbriši" obrisati sportski događaj. Klikom na gumb "Spremi" podatci se šalju i zapisuju u bazu. 
1. Prijava u događaj 
1. Kreiranje natjecateljskog stabla - Organizator događaja otvara kontrolu Natjecateljsko stablo. On može kreirati natjecateljsko stablo za odabrani događaj. Organizator odabire događaj, nakon toga klikom na gumb "Kreiraj" kreira utakmice za događaj u koji su prijavljeni timovi. Utakmice se zatim spremaju u bazu u tablicu utakmice.
1. Pregled i unos rezultata - Ulaskom u kontrolu Natjecateljsko stablo, organizator ima mogućnost unosa rezultata te ažuriranje i brisanje istih.
1. Pregled timova i natjecatelja - Bilo koji korisnik otvara kontrolu Pregled timova i natjecanja. Korisnik odabire događaj te mu se za odabrani događaj prikazuju timovi i natjecatelji.
1. Ispis statistike
1. Tražilica - u gornjem desnom kutu aplikacije, na kontroli Događaji, postoji text box koji omogućuje unos riječi te pritiskom tipke Enter pronalazi se ključna riječ (naziv tima, sporta, natjecatelja ili događaja) i ispisuju se informacije iste.



## Karakteristike korisnika
Aplikaciju mogu koristiti:
1. Administrator - osoba odgovorna za uređivanje popisa sportova i za davanje pristupa, uz to što može sve što može i organizator događaja
1. Organizator događaja - osoba odgovorna za kreiranje događaja, kreiranje natjecateljskog stabla, upisivanje rezultata, uz to može i sve što može i natjecatelj
1. Voditelj tima - osoba koja prijavljuje tim kod grupnih natjecanja te prijavljuje natjecatelje. Može vidjeti rezultate, natjecateljsko stablo te ostale timove i natjecatelje. 
## Ograničenja
Ograničenja aplikacije vezana su uz dostupnost servera i baze podataka. Server stalno mora biti aktivan te za bazu podataka je stalno potrebna internetska veza.
## Pretpostavke
SportsPlannerApp je desktop aplikacija za Windows sustave na x86 arhitekturi.
 
# 3. Specifični zahtjevi
## Zahtjevi performansi
Kada je dostupan server, baza podataka i stalna internetska veza, aplikacija radi kao što bi trebala. Jedini problemi koji bi se mogli javiti je kada korisnik ima nestabilnu internetsku vezu.
## Logički zahtjevi nad bazom podataka
ERA model je prikazan u "Opisu dizajna sustava".
## Ograničenja dizajna
Dizajn aplikacije SportsEventPlanner je vrlo jednostavan za korištenje. Postoji glaavna forma na kojoj su dodane user kontrole na lijevoj strani glavne forne. Ovisno o tome što korisnik želi otvoriti, klikom na određeni gumb u kontroli otvara se novi Tab.
## Obilježja aplikacije
1. Pouzdanost - Svi članovi tima koji su kreirali aplikaciju, nakon izrade, detaljno ju testiraju te provjeravaju. Korisnik može otkriti nove pogreške koje prilikom testiranja nisu uočene i treba ih javiti da bi se one otklonile.
1. Dostupnost - Aplikacija je dostupna ako postoji internetska veza i ako su server te baza podataka dostupni. Aplikacije također nije dostupna za vrijeme redovnog održavanja, ali to je dogovoreno sa korisnikom. 
1. Sigurnost -  Neovlašteno korištenje aplikacije ne postoji, zbog toga što je to rješeno već kod prijave. Svaka uloga ima drugačija prava te time nema neovlaštenog korištenja. 
1. Održavanje - Ne postoji velika potreba za održavanjem aplikacije. Ispravak eventualnih greški i problema će korisnik dobiti u obliku nove verzije aplikacije. Ukoliko korisnik zatraži, mogu se dodati novi sportovi. Novo dodavanje  funcionalnosti se može napraviti prema dogovoru sa korisnikom.
1. Pokretnost - Aplikacija je samo dostupna na svim Windows operacijskim sustavima. Aplikacija mora biti instalirana na računalo korisnika. 

# 4. Opis dizajna sustava
## Use-Case Dijagram
Za aplikaciju smo kreirali jedan use case dijagram. Na dijagramu možemo vidjeti tri učesnika, a to su organizator turnira,voditelj tima te admin. Sva ta tri učesnika su korisnici aplikacije te se prijavljuju u aplikaciju. Voditelj tima nakon prijave može prijaviti tim te prijaviti natjecatelje u dodani tim. Može pregledati timove i natjecatelje u događajima. Može pregledati natjecateljsko stablo svih događaja te utakmice koje su u traženim stablima. Može pregledati statistike za odabrani događaj te ujedno može i generirati pdf sa tim statistikama. Organizator događaja može pregledati događaje, kreirati nove te ujedno i ažurirati i obrisati događaje koje je kreirao. Može pregledati natjecateljska stabla za sve događaje te može kreirati natjecateljsko stablo za događaj koji je on kreirao. Može unijeti rezultate za utakmice generirane natjecateljskim stablo, može ih ažurirati te obrisati. Može pregledati timove i natjecatelje u događajima. Admin može pregledati sportove koji su u ponudi za događaje u našoj aplikaciji, može ih dodati, ažurirati te obrisati. Važno je napomenuti da osim CRUD nad sportovima, admin može i sve što mogu i ostali korisnici. 
![use case dijagram](https://github.com/foivz/r20--aoletic-tmusic-dabramov1/blob/master/Dijagrami/UCD%20(4).png) 
## Dijagram klasa
Dijagram klasa prikazuje klase koje koristi aplikacija Sports Event Planner. Naša aplikacija sadrži devet funkcionalnosti.
Većina klasa je povezana slabom agregacijom, osim kontrola koje su vezane na glavnu formu. Funkcionalnost za događaje ima klasu kontrole, klasu objekta povućenu iz baze podataka, repozitorij te formu za unos događaja. Funkcionalnost za prijavu i registraciju u sustav imaju svoje forme te validaciju. Vrste sportova povućene su iz baze podataka u klasu "sport", postoji repozitorij za njih te kontrola za sport. Funkcionalnost za prijavu timova i natjecatelja u događaj ima kontrolu za prijavu te forme za unos timova i natjecatelja koje imaju svoje objekte povućene iz baze te repozitorije. Postoji klasa za pregled timova i natjecanja. Funkcionalnost za kreiranje i pregled natjecateljskog stabla ima kontrolu za to, objekt u kojem su utakmice kreirane tom funkcionalnošću te repozitorij i formu za unos rezultata.
![Dijagram klasa](https://github.com/foivz/r20--aoletic-tmusic-dabramov1/blob/master/Dijagrami/DKsve.png)
## ERA model
Baza podataka implementirana je u MySql-u te je pohranjena na serveru kolegija Programsko inženjerstvo. Model baze podataka sastoji se od 9 tablica. Tablica "Korisnik" sadrži informacije o bilo kojem korisniku naše aplikacije. Tablica "Korisnik" vuče podatke o tome koju ulogu određeni korisnik ima. U našoj aplikaciji to su administrator, organizator događaja te voditelj tima. Tablica "Dogadaji" sadrži podatke o sportskim događajima koje su organizatori događaja kreirali. Događaj mora biti određene vrste sporta koje je administrator zadao u tablici "Sportovi". U tablici "Timovi" su podatci o timovima koje su voditelji timova prijavili za određeno natjecanje. U tablici "Natjecatelji" nalaze se svi natjecatelji s ID-jem njihovog tima. Tablica NatjecateljiTimovi prikazuje povezanost timova i natjecatelja. TablicaTimoviUDogadaju prikazuje povezanost između događaja te timova koji su u njima. U tablici "Utakmice" nalaze se sve utakmice generirane natjecateljskim stablom. Ovdje su ujedno dva atributa koja nisu obavezna kod kreiranja utakmica, a kasnije se popunjavaju kod upisa rezultata. Voditelj tima može unijeti više timova, dok jedan tim može biti kreiran od samo jednog korisnika. Isto tako vrijedi i za tablicu "Natjecatelji", "Dogadaji", "Sportovi" te "Utakmice". Tim može imati više natjecatelja, dok jedan natjecatelj može pripadati samo jednom timu.
![](https://github.com/foivz/r20--aoletic-tmusic-dabramov1/blob/master/Dijagrami/ERA.png)
## Funkcionalnost - Prijava u sustav
Nakon što korisnik pokrene aplikaciju, prva što mora učiniti je prijaviti se u nju. Zbog toga nakon otvaranja aplikacije odmah izlazi forma za prijavu. U formi za prijavu, korisnik mora unijeti svoje korisničke podatke (korisničko ime, lozinka) te nakon toga mora kliknuti na gumb "Prijavi se". Nakon što korisnik ispuni cijelu formu za prijavu, aplikacija šalje podatke koje je korisnik upisao. Ukoliko je unos bio ispravan, tada aplikacija komunicira s bazom podataka te traži od nje postoji li registrirani korisnik s upisanim korisničkim podacima. Ukoliko korisnik ne postoji, tada aplikacija ispisuje pogrešku za neuspješnu prijavu te ponovo resetira polja za unos podataka. Ukoliko u bazi podataka postoji korisnik s upisanim podacima, tada se provjerava koju ulogu ima taj korisnik (Admin, organizator, voditelj tima) te se forma za prijavu gasi, a otvara se glavna forma koja je prilagođena za tog korisnika.
### Dijagram aktivnosti - Prijava u sustav
![Dijagram aktivnosti Prijava](https://github.com/foivz/r20--aoletic-tmusic-dabramov1/blob/master/Dijagrami/DAprijava.png)
### Dijagram slijeda - Prijava u sustav
![prijava dijagram slijeda](https://github.com/foivz/r20--aoletic-tmusic-dabramov1/blob/master/Dijagrami/DijagramSlijedaPrijava.png)
### Dijagram klasa - Prijava u sustav
![prijava klasa prijava](https://github.com/foivz/r20--aoletic-tmusic-dabramov1/blob/master/Dijagrami/DK_prijava.png)
### ERA model - Prijava u sustav
![era prijava](https://github.com/foivz/r20--aoletic-tmusic-dabramov1/blob/master/Dijagrami/ERA_prijava.png)
## Funkcionalnost - Registracija u sustav
### Dijagram aktivnosti - Registracija u sustav
## Funkcionalnost - CRUD događaja
Organizator događaja pritisne na gumb "događaji"u izborniku. Otvara se kontrola događaja. Učitavaju se svi događaji iz baze koje je prijavljeni organizator događaja te se prikazuju događaji koje je prije kreirao (ukoliko ih ima) u datagridDogadaji. Organizator događaja potom odabire željenu radnju. Ukoliko organizator događaja želi ažurirati već postojeći događaj koji je kreirao, označava događaj u datagridu te klikom na gumb "ažuriraj" se otvara forma za unos popunjena sa označenim redom u datagridu. Organizator zatim može mijenjati naziv,datume,brojeve timova te brojeve članova u timu. Klikom na gumb "spremi" ažurira već postojeći događaj u tablici. Ukoliko organizator događaja želi unijeti događaj, klikom na gumb "unos" se isto tako otvara kontrola za unos. Unosi naziv događaja, unosi datum početka te datum završetka događaja, unosi minimalni te maksimalni broj timova te nakon toga unosi broj članova u timu. Kada organizator upiše sve podatke može spremiti novi događaj u tablicu klikom na gumb "spremi".
### Dijagram aktivnosti - CRUD događaja
![](https://github.com/foivz/r20--aoletic-tmusic-dabramov1/blob/master/Dijagrami/ADDogadaji.jpg)
### Dijagram klasa- CRUD događaja
![](https://github.com/foivz/r20--aoletic-tmusic-dabramov1/blob/master/Dijagrami/CDDogadaji.vpd.png)
### ERA dijagram - CRUD događaja
![](https://github.com/foivz/r20--aoletic-tmusic-dabramov1/blob/master/Dijagrami/ERA_dogadaji.png)
## Funkcionalnost - Prijava u događaj
Na dijagramu možemo vidjeti da za prijavu u natjecanje osoba mora biti registrirana u aplikaciju i tek onda može otvoriti obrazac za prijavu na natjecanje. Korisnik prvo odabire željeno natjecanje u koje se želi prijaviti, nakon toga otvara se obrazac u kojem se ispunjavaju određene informacije koje organizator zahtjeva da se popune. Korisnik može ažurirati i obrisati prijavu i naknadno. Organizator ima mogućnost poništavanja prijave. Prijava kada je ispunjena sprema se u bazu podataka i popunjava tablicu gdje se spremaju prijave.
### Dijagram aktivnosti - Prijava u događaj
![](https://github.com/foivz/r20--aoletic-tmusic-dabramov1/blob/master/Dijagrami/DijagramAktivnostiPrijava2.png)
## Funkcionalnost - Kreiranje natjecateljskog stabla
Organizator događaja pritisne na gumb "natjecateljsko stablo". Otvara se kontrola natjecateljsko stablo. Aplikacija provjera otvara li kontrolu voditelj timaili organizator. Ukoliko kontrolu otvara organizator, on ima dvije mogućnosti.
Može kreirati stablo pritiskom na gumb "kreiranje" te može pregledati stablo za neki događaj. Voditelj tima može samo pregledati stablo za neki događaj. Organizator označuje događaj za koji želi kreirati stablo u ComboBoxu. Pritiskom na gumb "kreiranje" dohvaćuje se željeni događaj iz baze, dohvaćuju se timovi iz baze za traženi događaj te se kreira stablo natjecanja s nazivima timova. Utakmice kreirane natjecateljskim stablom zapisuju se u tablicu utakmice. Kreirane utakmice prikazuju se u dataGridu utakmice. Ukoliko već natjecateljsko stablo postoji, provjerava se jesu li upisani rezultati za utakmice, ako jesu, na temelju pobjednika u tim utakmicama se generira sljedeće natjecateljsko stablo. Ukoliko organizator ili voditelj tima žele vidjeti neko stablo, odabiru događaj u comboboxu te se automatski utakmice iz baze zadane natjecateljskim stablom za željeni događaj prikazuju u dataGriduUtakmice. 
### Dijagram aktivnosti - Kreiranje natjecateljskog stabla
![](https://github.com/foivz/r20--aoletic-tmusic-dabramov1/blob/master/Dijagrami/ADNatjecateljskoStablo.vpd.png)
### Dijagram klasa- Kreiranje natjecateljskog stabla
![](https://github.com/foivz/r20--aoletic-tmusic-dabramov1/blob/master/Dijagrami/CDStablo.vpd.png)
### ERA dijagram - Kreiranje natjecateljskog stabla
![](https://github.com/foivz/r20--aoletic-tmusic-dabramov1/blob/master/Dijagrami/ERA_stablo.png)
## Funkcionalnost - Prijava u događaj
## Funkcionalnost - Unos rezultata
Nakon što korisnik u glavnoj formi aplikacije odabere gumb "Natjecateljsko stablo", korisniku se otvara kontrola u kojoj ima mogućnost unosa rezultata za pojedine utakmice. Prvo korisnik mora odabrati događaj te utakmicu koja pripada tom događaju. Nakon toga aplikacija uzima podatke o utakmici iz baze podataka te se utakmica učitava u dataGrid za utakmice. Nakon toga korisnik ima mogućnost odabira aktivnosti za pojedinu utakmicu. Ukoliko korisnik klikne na gumb "Dodaj utakmicu", tada se otvara forma za unos rezultata. Ulaskom u formu, korisnik treba unijeti broj poena za prvi tim te broj poena za drugi tim i klikom na gumb "Spremi" provjerava se ispravnost podataka, te ako su podaci ispravni podaci se unose u bazu podataka te se novi rezultat učitava u dataGrid za utakmice. Ukoliko se korisnik odlučio za ažuriranje rezultata, tada se otvara kontrola za ažuriranje podataka te korisnik mora unijeti nove poene za tim 1 te nove poene za tim 2 i kliknuti na gumb "Spremi". Nakon toga provjerava se ispravnost unesenih podataka te ako podaci nisu ispravno upisani, ispisuje se pogreška za unos, a ukoliko su podaci ispravno uneseni rezultati se ažuriraju u bazi podataka te se novi rezultat ispisuje u dataGridu za rezultat utakmice. Zadnja mogućnost koju korisnik ima je brisanje utakmice klikom na gumb "Izbriši utakmicu". Nakon klika na gumb, aplikacija briše iz baze podataka odabranu utakmicu te se osvježava popis utakmica i učitava u dataGrid.
### Dijagram aktivnosti - Unos  rezultata
![Dijagram aktivnosti Rezultati](https://github.com/foivz/r20--aoletic-tmusic-dabramov1/blob/master/Dijagrami/DArezultati.png)
### Dijagram klasa - Unos  rezultata
![Dijagram klasai Rezultati](https://github.com/foivz/r20--aoletic-tmusic-dabramov1/blob/master/Dijagrami/DK_rezultati.png)
### ERA model - Unos  rezultata
![ERA model Rezultati](https://github.com/foivz/r20--aoletic-tmusic-dabramov1/blob/master/Dijagrami/ERA_rezultati.png)
## Funkcionalnost - Pregled timova i natjecatelja
Korisnik pritisne na gumb "pregled timova i natjecanja" u izborniku. Otvara se kontrola pregled timova i natjecanja. Prikazuje se ComboBox u kojem su događaji. Odabirom događaja dohvaćuju se svi timovi iz baze koji su u tom događaju te se učitavaju u dataGrid Timovi. Korisnik duplim klikom na red u dataGriduTimovi može vidjeti sve natjecatelje koji su u tom timu u dataGriduNatjecatelji. 
### Dijagram aktivnosti - Pregled timova i natjecatelja
![](https://github.com/foivz/r20--aoletic-tmusic-dabramov1/blob/master/Dijagrami/ADPregled.jpg)
### Dijagram klasa- Pregled timova i natjecatelja
![](https://github.com/foivz/r20--aoletic-tmusic-dabramov1/blob/master/Dijagrami/CDPregled.vpd.png)
### ERA dijagram - Pregled timova i natjecatelja
![](https://github.com/foivz/r20--aoletic-tmusic-dabramov1/blob/master/Dijagrami/ERA_pregled.png)

## Funkcionalnost - Ispis statistike
Kod statistike potrebno je odabrati točno određeno natjecanje za koje želimo pregledati statistiku. Imamo dvije mogućnosti gledanja statistike. prvi način pojedinačno po igračima i drugi način pojedinačno po timovima. U tom prikazu se prikazuje statistika svakog člana određenog tima koji u tom trenutku pregledavamo.
### Dijagram aktivnosti - Ispis statistike
![](https://github.com/foivz/r20--aoletic-tmusic-dabramov1/blob/master/Dijagrami/DijagramAktivnostiStatistika2.png)
## Funkcionalnost - Tražilica
Prilikom otvaranja bilo koje kontrole koja sadrži neki od DataGrid-ova za prikaz podataka pojavljuje se i TextBox polje gdje korisnik može kliknuti i upisati željenu riječ. Kada korisnik unosi slova u TextBox, tada se podaci u Datagridu filtriraju po riječi. Ako tražena riječ ne postoji u datagridu, tada datagrid postaje prazan, ali ako riječ ipak postoji u datagridu, tada se prikazuju sve riječi koje u sebi sadrže riječi ili slova koja su upisana u TextBox
### Dijagram aktivnosti - Tražilica
![Dijagram aktivnosti Tražilica](https://github.com/foivz/r20--aoletic-tmusic-dabramov1/blob/master/Dijagrami/DAtrazilica.png)
### Dijagram klasa - Tražilica
![Dijagram klasa Tražilica](https://github.com/foivz/r20--aoletic-tmusic-dabramov1/blob/master/Dijagrami/DK_trazilica.vpd.png)
### ERA model - Tražilica
![ERA model Tražilica](https://github.com/foivz/r20--aoletic-tmusic-dabramov1/blob/master/Dijagrami/ERA_trazilica.png)
