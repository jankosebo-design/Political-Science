# Political Science

Materiály a interaktívne hry k predmetu Political Science (Bc., Aplikovaná ekonómia).

| Modul | Hra | Adresa po zapnutí GitHub Pages |
|---|---|---|
| 3 · Hlasovacie systémy a mocenská hra | Ústava za 75 minút | https://jankosebo-design.github.io/political-science/modul-03/ustava75/ |

Úvodná stránka: https://jankosebo-design.github.io/political-science/

## Ako hra funguje (technicky)

- Je to **jeden HTML súbor** bez inštalácie a bez vlastného servera.
- **Hostiteľ = počítač vyučujúceho na projektore.** Všetky výsledky sa ukladajú v jeho prehliadači (localStorage) a dajú sa na konci exportovať do CSV.
- **Hráči = mobily študentov.** Pripájajú sa cez QR kód; spojenie ide priamo prehliadač–prehliadač (WebRTC, knižnica PeerJS 1.5.4 je vložená v súbore). Na nadviazanie spojenia sa používa bezplatný verejný server PeerJS (`0.peerjs.com`) a jeho TURN servery.
- Študenti sa **nemusia registrovať** ani nič inštalovať. Stačí moderný prehliadač (Chrome, Safari, Firefox).
- GitHub Pages poskytuje **https**, ktoré WebRTC na mobiloch vyžaduje.

## Jednorazové nastavenie: zapnutie GitHub Pages (asi 2 minúty)

1. Zlúčte (merge) pull request s hrou do vetvy `main`.
2. Na GitHube otvorte repozitár → **Settings** → v ľavom menu **Pages**.
3. V časti **Build and deployment** nastavte:
   - **Source:** `Deploy from a branch`
   - **Branch:** `main`, priečinok `/ (root)` → **Save**.
4. Počkajte 1–3 minúty. Hore na stránke Pages sa objaví *„Your site is live at …“*.
5. Otvorte https://jankosebo-design.github.io/political-science/ a overte, že sa zobrazí úvodná stránka.

> Repozitár musí zostať **verejný** (bezplatné GitHub Pages pre súkromné repozitáre nie sú dostupné). Hra neobsahuje osobné údaje; mená študentov existujú len v prehliadači vyučujúceho.

## Generálka pred hodinou (5 minút, odporúčané)

1. Na notebooku otvorte adresu hry → zobrazí sa obrazovka hostiteľa s **kódom hry** a **QR kódom**.
2. Skontrolujte stav vpravo hore: **„spojenie: pripojené“**.
3. Mobilom (ideálne na **školskej Wi-Fi** aj na **mobilných dátach**) naskenujte QR, zadajte meno a vyberte stranu. Na projektore musí pribudnúť hráč.
4. Ak sa mobil nepripojí na školskej Wi-Fi, ale na dátach áno, školská sieť blokuje WebRTC. Riešenie: študenti hrajú na mobilných dátach (prenos je minimálny, desiatky kB).

## Priebeh na hodine

1. **Pred hodinou:** na počítači v učebni otvorte adresu hry a prepnite na projektor (celá obrazovka F11).
2. **Pripojenie (5 min):** študenti naskenujú QR kód z projektora (alebo prepíšu odkaz `…?room=KÓD`), zadajú meno ako v Moodle a vyberú stranu (5 strán × 8 hráčov). Prvý v strane je kapitán.
3. **Hra:** vyučujúci posúva fázy tlačidlami **Ďalej ▶ / ◀ Späť** (Štart → 1 Analýza → Odhalenie → 2 Ústava → Výsledok → 3 Moc a info → Odhalenie → 4 Komisia → Realita → Výstup → Body). Podrobne v [pravidlách a metodike (PDF)](modul-03/ustava75/pravidla_a_metodika.pdf).
4. **Koniec:** vo fáze *Body* exportujte výsledky do **CSV** a nahrajte do Moodle.

### Čo keď…

- **Zatvorím omylom prehliadač na projektore?** Otvorte znova tú istú adresu: hra ponúkne *„Pokračovať v rozohratej hre?“* → OK. Stav je uložený v prehliadači.
- **Študentovi spadne mobil / zatvorí stránku?** Nech znova otvorí ten istý odkaz alebo QR; vráti sa pod tým istým menom a stranou.
- **Chcem začať novú hru?** Pri otázke *„Pokračovať…?“* zvoľte **Zrušiť**, alebo vo fáze Body tlačidlo **Nová hra**.
- **Test bez internetu na jednom počítači:** pridajte k adrese `?t=local` (hostiteľ aj hráči v kartách toho istého prehliadača).
- **Dôležité:** hru hostiteľa spúšťajte len na **jednom** počítači; študenti adresu hostiteľa neotvárajú (QR vedie na hráčsku verziu).

## Aktualizácia hry

Novú verziu stačí nahrať ako `modul-03/ustava75/index.html` (na GitHube: otvoriť súbor → ikona ceruzky alebo *Add file → Upload files*). Zmena je online do 1–3 minút.

## Obmedzenia, o ktorých treba vedieť

- Verejný server PeerJS je bezplatná služba bez záruky dostupnosti. Pri 40 hráčoch bežne stačí; preto odporúčame generálku pred hodinou.
- Ak by bol verejný server nedostupný, záložné riešenie je vlastný PeerJS server (univerzitné IT); hra má na to parametre `?peerhost=…&peerport=…`, pri https by však potrebovala malú úpravu (zabezpečené spojenie).
