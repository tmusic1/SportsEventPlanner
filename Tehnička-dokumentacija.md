# Tehnička dokumentacija
Na ovoj stranici je dostupna tehnička dokumentacija projekta SportsEventPlanner.

# 1. Uvod
Tehnička dokumentacija predstavlja detaljnu specifikaciju korisničkih zahtjeva napisanu prema standardu IEEE Std 830-1998. U uvodu ćemo navesti svrhu i djelokrug projekta te će biti reference koje su korištene. Slijedi opis proizvoda, specifični zahtjevi te detaljan opis dizajna sustava.
## Svrha
Svrha ovog dokumenta je pružiti naručitelju i programerima detaljne informacije o izradi krajnjeg proizvoda. Dokumentacija je vrlo bitna za daljnji razvoj, a uključuje opis aplikacije za vođenje sportskih događaja, specifikaciju korisničkih zahtjeva te tehničku specifikaciju. Također sadrži opise slučajeva korištenja te obilježja i ograničenja aplikacije.
## Djelokrug
Aplikacije se izdaje pod imenom "SportsPlannerApp". Namijenjena je organizatorima događaja, voditeljima timova te natjecateljima. Gotov proizvod imati će: 
1. Desktop aplikaciju namijenjenu organizatorima događaja, voditeljima timova te natjecateljima kojom će se kreirati, prijavljivati te voditi evidencija o događajima. 
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
1. Prijava u sustav
1. Registracija u sustav
1. CRUD događaja - Organizator događaja otvara Tab Događaji. On klikom na gumb "Unos" može kreirati, "Promijeni" može promijeniti te "Izbriši" obrisati sportski događaj. Klikom na gumb "Spremi" podatci se šalju i zapisuju u bazu. 
1. Prijava u događaj 
1. Kreiranje natjecateljskog stabla - Organizator događaja otvara Tab Natjecateljsko stablo. On može kreirati natjecateljsko stablo za odabrani događaj. Organizator odabire događaj, nakon toga klikom na gumb "Kreiraj" kreira utakmice za događaj u koji su prijavljeni timovi. Utakmice se zatim spremaju u bazu u tablicu utakmice.
1. Pregled rezultata
1. Pregled timova i natjecatelja - Bilo koji korisnik otvara Tab Pregled timova i natjecanja. Korisnik odabire događaj te mu se za odabrani događaj prikazuju timovi i natjecatelji.
1. Ispis statistike
1. Tražilica



## Karakteristike korisnika
Aplikaciju mogu koristiti:
1. Administrator - osoba odgovorna za uređivanje popisa sportova i za davanje pristupa, uz to što može sve što može i organizator događaja
1. Organizator događaja - osoba odgovorna za kreiranje događaja, kreiranje natjecateljskog stabla, upisivanje rezultata, uz to može i sve što može i natjecatelj
1. Natjecatelj - osoba koja prijavljuje tim kod grupnih natjecanja te prijavljuje sebe kod pojedinačnih natjecanja. Može vidjeti rezultate, natjecateljsko stablo te ostale timove i natjecatelje. 
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
## Dijagram klasa
## ERA model
## Funkcionalnost - Prijava u sustav
Nakon što korisnik pokrene aplikaciju, prva što mora učiniti je prijaviti se u nju. Zbog toga nakon otvaranja aplikacije odmah izlazi forma za prijavu. U formi za prijavu, korisnik mora unijeti svoje korisničke podatke (korisničko ime, lozinka) te nakon toga mora kliknuti na gumb "Prijavi se". Nakon što korisnik ispuni cijelu formu za prijavu, provjerava se ispravnost unesenih podataka (RegEx). Ukoliko podaci nisu ispravni, aplikacija izbacuje poruku o neispravnosti unosa, te resetira sve prijašnje podatke koje je korisnik upisao. Ukoliko je unos bio ispravan, tada aplikacija komunicira s bazom podataka te traži od nje postoji li registrirani korisnik s upisanim korisničkim podacima. Ukoliko korisnik ne postoji, tada aplikacija ponovo ispisuje pogrešku za neuspješnu prijavu te ponovo resetira polja za unos podataka. Ukoliko u bazi podataka postoji korisnik s upisanim podacima, tada se provjerava koju ulogu ima taj korisnik (Admin, organizator, natjecatelj) te se forma za prijavu gasi, a otvara se glavna forma koja je prilagođena za tog korisnika.
### Dijagram aktivnosti - Prijava u sustav
![Dijagram aktivnosti Prijava](https://github.com/foivz/r20--aoletic-tmusic-dabramov1/blob/master/Dijagrami/DijagramAktivnostiPrijava.png)
## Funkcionalnost - Registracija u sustav
### Dijagram aktivnosti - Registracija u sustav
## Funkcionalnost - CRUD događaja
Organizator događaja pritisne na gumb "događaji"u izborniku. Otvara se kontrola događaja. Učitavaju se svi događaji iz baze koje je prijavljeni organizator događaja te se prikazuju događaji koje je prije kreirao (ukoliko ih ima) u datagridDogadaji. Organizator događaja potom odabire željenu radnju. Ukoliko organizator želi ažurirati neki događaj, označuje željeni događaj, taj događaj se dohvaćuje iz baze. Klikom na gumb "ažuriraj" se inicijalizira kontrola za unos te upisuje naziv događaja, unosi datum početka te datum završetka događaja, unosi minimalni te maksimalni broj timova te nakon toga unosi broj članova u timu. Kada organizator upiše sve podatke može ažurirati prije označeni događaj u tablici klikom na gumb "spremi" ili odustati klikom na gumb "odustani". Ukoliko organizator događaja želi unijeti događaj, klikom na gumb "unos" se isto tako otvara kontrola za unos. Unosi naziv događaja, unosi datum početka te datum završetka događaja, unosi minimalni te maksimalni broj timova te nakon toga unosi broj članova u timu. Kada organizator upiše sve podatke može spremiti novi događaj u tablicu klikom na gumb "spremi" ili odustati klikom na gumb "odustani".
### Dijagram aktivnosti - CRUD događaja
![](https://github.com/foivz/r20--aoletic-tmusic-dabramov1/blob/master/Dijagrami/DijagramAktivnostiDogadajiFinal.vpd.jpg)
## Funkcionalnost - Prijava u događaj
### Dijagram aktivnosti - Prijava u događaj
## Funkcionalnost - Kreiranje natjecateljskog stabla
Organizator događaja pritisne na gumb "natjecateljsko stablo". Otvara se kontrola natjecateljsko stablo. Aplikacija provjera otvara li kontrolu natjecatelj ili organizator. Ukoliko kontrolu otvara organizator, on ima dvije mogućnosti.
Može kreirati stablo pritiskom na gumb "kreiranje" te može pregledati stablo za neki događaj. Natjecatelj može samo pregledati stablo za neki događaj. Organizator označuje događaj za koji želi kreirati stablo u ComboBoxu. Pritiskom na gumb "kreiranje" dohvaćuje se željeni događaj iz baze, dohvaćuju se timovi iz baze za traženi događaj te se kreira stablo natjecanja s nazivima timova. Utakmice kreirane natjecateljskim stablom zapisuju se u tablicu utakmice. Kreirane utakmice prikazuju se u dataGridu utakmice. Ukoliko organizator ili natjecatelj žele vidjeti neko stablo, odabiru događaj te pritiskom na gumb "pregled" dohvaćuje se željeni događaj iz baze, dohvaćuju se utakmice iz baze te se utakmice zadane natjecateljskim stablom za željeni događaj prikazuju u dataGriduUtakmice. 
### Dijagram aktivnosti - Kreiranje natjecateljskog stabla
![](https://github.com/foivz/r20--aoletic-tmusic-dabramov1/blob/master/Dijagrami/DijagramAktivnostiNatjecateljskoStabloFinal.jpg)
## Funkcionalnost - Pregled rezultata
Nakon što korisnik u glavnoj formi aplikacije odabere gumb "Natjecateljsko stablo", korisniku se otvara kontrola u kojoj ima mogućnost unosa rezultata za pojedine utakmice. Prvo korisnik mora odabrati događaj te utakmicu koja pripada tom događaju. Nakon toga aplikacija uzima podatke o utakmici iz baze podataka te se utakmica učitava u dataGrid za utakmice. Nakon toga korisnik ima mogućnost odabira aktivnosti za pojedinu utakmicu. Ukoliko korisnik klikne na gumb "Dodaj utakmicu", tada se otvara kontrola za unos rezultata. Ulaskom u kontrolu, korisnik treba unijeti broj poena za domaćina te broj poena za gosta i klikom na gumb "Spremi" provjerava se ispravnost podataka, te ako su podaci ispravni podaci se unose u bazu podataka te se nova utakmica učitava u dataGrid za utakmice. Ukoliko se korisnik odlučio za ažuriranje rezultata, tada se otvara kontrola za ažuriranje podataka te korisnik mora unijeti nove poene domaćina te nove poene gosta i kliknuti na gumb "Spremi". Nakon toga provjerava se ispravnost unesenih podataka te ako podaci nisu ispravno upisani, ispisuje se pogreška za unos, a ukoliko su podaci ispravno uneseni rezultati se ažuriraju u bazi podataka te se novi rezultat ispisuje u dataGridu za rezultat utakmice. Zadnja mogućnost koju korisnik ima je brisanje utakmice klikom na gumb "Izbriši utakmicu". Nakon klika na gumb, aplikacija briše iz baze podataka odabranu utakmicu te se osvježava popis utakmica i učitava u dataGrid.
### Dijagram aktivnosti - Pregled rezultata
![Dijagram aktivnosti Rezultati](https://github.com/foivz/r20--aoletic-tmusic-dabramov1/blob/master/Dijagrami/DijagramAktivnostiRezultati.png)
## Funkcionalnost - Pregled timova i natjecatelja
Korisnik pritisne na gumb "pregled timova i natjecanja" u izborniku. Otvara se kontrola pregled timova i natjecanja. Prikazuje se ComboBox u kojem su događaji. Odabirom događaja. Dohvaćuju se svi timovi iz baze koji su u tom događaju te se učitavaju u dataGrid Timovi. Korisnik duplim klikom na red u dataGridu može vidjeti sve natjecatelje koji su u tom timu.  
### Dijagram aktivnosti - Pregled timova i natjecatelja
![](https://github.com/foivz/r20--aoletic-tmusic-dabramov1/blob/master/Dijagrami/DijagramAktivnostiPregledTimovaNatjecatelja.vpd.jpg)
## Funkcionalnost - Ispis statistike
### Dijagram aktivnosti - Ispis statistike
## Funkcionalnost - Tražilica
U gornjem lijevom kutu aplikacije nalazi se tražilica koja omogućuje korisniku pregled ključnih riječi u aplikaciji (za nazive timova, događaja, natjecatelja i sportova). Klikom na tražilicu korisnik unosi riječ te pritišće tipku "Enter". Nakon toga aplikacija komunicira s bazom podataka te provjerava nalazi li se unesena riječ u nekoj od navedenih tablica. Ukoliko riječ nije pronađena, ispisuje se poruka o neuspješnom pokušaju pretraživanja riječi. Ako je riječ pronađena u bazi podataka otvara se nova kontrola za prikaz podataka te se u nju učitavaju svi podaci koji pripadaju uz tu riječ
### Dijagram aktivnosti - Tražilica
![Dijagram aktivnosti Tražilica](https://github.com/foivz/r20--aoletic-tmusic-dabramov1/blob/master/Dijagrami/DijagramAktivnostiTrazilica.png)


