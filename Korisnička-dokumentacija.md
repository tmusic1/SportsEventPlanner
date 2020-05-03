# Korisnička dokumentacija
# Sports Event Planner
## 1. Prijava
Prilikom otvaranja aplikacije prvo se otvara Log In forma. Unutar nje potrebno je ispuniti korisničke podatke (korisničko ime i lozinka) te se mora kliknuti na gumb "Prijavi se" kako bi se korisnik prijavio u aplikaciju svojim korisničkim računom. Ukoliko korisnik ne posjeduje korisnički račun, tada treba kliknuti na "Nemaš korisnički račun? Registriraj se" te se nakon toga otvara nova forma u kojoj se vrši registracija. Ukoliko korisnik upiše krive podatke, forma za prijavu se resetira te on ima mogućnost ponovnog unosa svojih korisničkih podataka.

## 2. Registracija
Nakon što se korisnik odluči da se želi registrirati za korištenje ove aplikacije te otvori formu za registraciju, on treba ispuniti formu svojim podacima. Podaci koji se traže od Vas kako bi se mogli registrirati su Vaše ime, prezime, željeno korisničko ime, E-mail, te lozinka. Također, lozinku je potrebno ponovo upisati kako biste potvrdili prvotno upisanu lozinku. Nakon što ste ispunili sve korisničke podatke potrebno je kliknuti na gumb "Registriraj se", kako bi se registracija izvršila. Nakon toga korisnički račun je uspješno izrađen te se možete prijaviti u aplikaciju.

## 3. Glavna forma aplikacije

Nakon što ste se uspješno prijavili u aplikaciju, otvara se glavna forma. Na lijevoj strani forme nalazi se navigacijski izbornik koji se sastoji od 6 gumbova koji otvaraju različite kontrole. Gumbi koji se nalaze na navigacijskom izborniku su:
1. Događaji
1. Sportovi
1. Natjecateljsko stablo
1. Prijava u natjecanje
1. Pregled timova i natjecanja
1. Statistika

U donjem lijevom kutu nalazi se gumb "Odjavi se" koji Vas odjavljuje iz aplikacije nakon što kliknete na njeg. Ako želite ponovo koristiti aplikaciju, nakon odjave morate se ponovo prijaviti.

### 3.1 Događaji

Ukoliko ste na glavnoj formi kliknuli na gumb "Događaji", otvara Vam se kontrola "Događaji". Unutar kontrole moguće je dodavati nove događaje, ažurirati već dodane događaje te obrisati događaje. Ispod gumbova nalazi se popis svih događaja.  Ukoliko želite dodati novi događaj potrebno je kliknuti na gumb "Dodaj događaj". Nakon što ste kliknuli na taj gumb, otvara Vam se nova forma koju je potrebno ispuniti. U formu je potrebno upisati ime događaja, datum početka, datum završetka, minimalni broj timova, maksimalni broj timova, broj članova u timu te iz padajućeg izbornika odabrati vrstu sporta za taj događaj. Ukoliko ste upisali sve podatke, potrebno je kliknuti na gumb "Spremi" te se uneseni događaj sprema u aplikaciju. 

Nakon što odaberete neki događaj i kliknete na gumb "Ažuriraj događaj" otvara se ista forma kao i za dodavanje događaja. Također je potrebno upisati sve informacije vezane za događaj koje će se kasnije zamijeniti sa informacijama koje su unesene prije. Klikom na gumb "Spremi", spremiti ćete navedene promjene. 

Ukoliko želite obrisati jedan od događaja, potrebno je odabrati događaj te kliknuti na gumb "Obriši događaj"

### 3.2 Sportovi

Ako ste na glavnoj formi odabrali gumb "Sportovi" , otvara Vam se nova kontrola koja sadrži popis svih sportova za koje je moguće kreirati događaje. Sportovi su unaprijed određeni te samo admin može dodati i mijenjati popis događaja

### 3.3 Natjecateljsko stablo

Prilikom klika na gumb "Natjecateljsko stablo" u glavnoj formi, otvara se kontrola Natjecateljsko stablo. Ovdje možete izraditi ždrijeb za unseseni događaj. Događaj se odabire tako da iz padajućeg izbornika odaberete naziv događaja te kliknete na gumb "Kreiranje najtecateljskog stabla". Nakon toga kreira se ždrijeb. Ukoliko ždrijeb za navedeni događaj već postoji, klikom na gumb "Pregled natjecateljskog stabla" možete pogledati kako izgleda ždrijeb za odabrani događaj. Ispod ždrijeba moguće je dodavati, promijeniti te izbrisati rezultate utakmice.

 Odabirom utakmice iz ždrijeba te klikom na gumb "Dodaj rezultat" otvara se forma za unos rezultata. U otvorenoj formi potrebno je upisati broj poena za tim 1 te broj poena za tim 2 te klikom na gumb "Spremi" rezultat se unosi u aplikaciju.

 Ukoliko želite ažurirati već uneseni rezultat potrebno je kliknuti na gumb "Promijeni rezultat" te se otvara ista forma u kojoj ponovo unosite željeni rezultat. 

Rezultat je moguće obrisati tako što morate odabrati utakmicu te kliknuti na gumb "Izbriši rezultat".

### 3.4 Prijava u natjecanje

Ukoliko se želite prijaviti u natjecanje, na glavnoj formi je potrebno kliknuti na gumb "Prijava u natjecanje". Tada Vam se otvara kontrola za prijavu u natjecanje gdje morate iz padajućeg izbornika odabrati željeni događaj. Ukoliko se radi o timskom sportu tada je omogućen gumb "Dodaj tim" te klikom na njega otvara se nova forma za unos timova. U formi je potrebno napisati ime tima, broj igrača te kontakt broj. Pošto se radi o timskom sportu, u ovoj formi je potrebno kliknuti i na gumb "Dodaj natjecatelja" kako biste dodali i natjecatelje koji se nalaze u tom timu. Klikom na gumb "Spremi", prijava se izvršava.

Ukoliko ste odabrali događaj u kojem se igra pojedinačni sport tada je gumb "Dodaj tim" blokiran te je moguće kliknuti samo na gumb "Dodaj natjecatelja". Klikom na taj gumb otvara se forma u kojoj korisnik mora napisati ime, prezime, OIB, E-mail, datum rođenja te kontakt telefon. Klikom na gumb "Spremi" korisnik se prijavljuje u natjecanje.

### 3.5 Pregled timova i natjecatelja

Ukoliko želite vidjeti prijavljene timove i natjecatelje, na glavnoj formi potrebno je kliknuti na gumb "Pregled timova i natjecatelja". Nakon toga otvara se kontrola gdje možete vidjeti sve prijavljene timove i natjecatelje nakon što iz padajućeg izbornika izaberete željeni događaj. Na lijevoj strani prikazani su timovi, a na desnoj strani natjecatelji.

### 3.6 Statistika

Ukoliko  imate kakvo pitanje slobodno nam se javite putem E-maila
1. aoletic@foi.hr
1. tmusic@foi.hr
1. dabramovic@foi.hr