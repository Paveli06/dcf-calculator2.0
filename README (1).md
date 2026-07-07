# DCF Kalkulačka

Pokročilá DCF (Discounted Cash Flow) kalkulačka pro odhad vnitřní hodnoty akcie.
Jeden statický HTML soubor — žádný build krok, žádné závislosti na serveru.

## Co umí

- **Dvoufázový DCF model** — explicitní projekce (5/7/10 let) + terminální hodnota (Gordonův růstový model)
- **Lineárně konvergující předpoklady** — růst tržeb a EBIT marže se plynule mění od hodnoty pro 1. rok k cílové/terminální hodnotě
- **3 scénáře** — Pesimistický / Základní / Optimistický, každý s vlastní sadou předpokladů, editovatelné nezávisle
- **Citlivostní analýza** — tabulka vnitřní hodnoty na akcii podle kombinací WACC × terminální růst, barevně odlišená vůči aktuální tržní ceně
- **Grafy** — projekce FCF a jeho současné hodnoty, vodopád ocenění (EV → čistý dluh → equity), srovnání scénářů
- **Vše se přepočítává živě** při psaní do vstupů

## Nasazení na GitHub Pages

1. Vytvoř nový repozitář na GitHubu (např. `dcf-calculator`).
2. Nahraj do něj soubor `index.html` (musí být v kořeni repozitáře, nebo ve složce `/docs` — podle nastavení níže).

   ```bash
   git init
   git add index.html
   git commit -m "DCF kalkulačka"
   git branch -M main
   git remote add origin https://github.com/TVŮJ_ÚČET/dcf-calculator.git
   git push -u origin main
   ```

3. V repozitáři jdi do **Settings → Pages**.
4. U "Build and deployment" vyber **Source: Deploy from a branch**.
5. Vyber branch `main` a složku `/ (root)`.
6. Ulož. Po chvíli bude appka dostupná na:
   `https://TVŮJ_ÚČET.github.io/dcf-calculator/`

Žádné další kroky nejsou potřeba — appka je čistý HTML/CSS/JS, žádné npm balíčky ani build proces.

## Poznámky k modelu

- Vstupy jsou v absolutních částkách (ne v tisících/milionech) — zadej plnou částku, např. `1000000000` pro 1 miliardu.
- Pole "Aktuální cena akcie" je nepovinné — pokud ho necháš prázdné nebo na 0, appka jen nebude počítat rozdíl vůči trhu.
- Terminální hodnota se počítá jen pokud WACC > terminální růst (jinak vzorec diverguje — to je matematická vlastnost Gordonova modelu, ne chyba appky).

## Licence / použití

Tento nástroj je čistě edukační a orientační pomůcka, není investičním doporučením.
