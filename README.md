SQL PROJEKT
Projekt je rozdělený do dvou pomyslných částí, ta první delší připravuje jednotlivé tabulky a druhá část pak už jen tabulky spojí a vytvoří požadovaná panelová data. Rozhodl jsem se postupovat tímto způsobem ze dvou hlavních důvodů. 

Tím prvním je rychlost, na kterou jsem narazil hned na začátku projektu. Bez pročištění dat a výběru jen těch potřebných trvalo spojení tabulek několik desítek minut a často došlo i k nějaké chybě, bylo to velmi neefektivní. Jako jeden příklad uvádím např. tabulku economies, kde kromě jednotlivých zemí jsou uvedeny také regiony a geo-politické celky. Samotné čištění jsem udělal tak, že jsem si vytvořil pomocnou tabulku pouze se zeměmi z covid19_basic_differences a tu jsem pak použil na odstranění všech záznamů, které neobsahují tyto země.

Druhým hlavním důvodem rozdělení projektu do dvou částí byla lepší přehlednost projektu a snazší hledání a identifikace problémů. Jednotlivé SQL příkazy jsou rozděleny do menších dílčích celků a pomocných tabulek, které je pak snazší upravit nebo opravit.

U některých záznamů, např. z tabulky countries, nebylo jasné, z jakého roku data pocházejí. Všude, kde to bylo možné, jsem se snažil brát data, kde bylo možné dohledat, ke kterému roku se vztahují, a to jsem pak uvedl ve výsledné tabulce. V některých případech jsem si data spočítal sám, např. u hustoty zalidnění, abych věděl a mohl uvést, ze kterého roku data jsou. U giniho koeficientu byla data časové velmi neuspořádaná a poslední záznam byl někdy i několik desítek let starý. Vybral jsem vždy ten nejaktuálnější a vytvořil nový sloupec, kde je uvedeno, ze kterého roku jsou konkrétní data. 

Dalším častým problémem bylo rozdílné pojmenování zemí a jejich hlavních měst. Např. Praha v tabulce countries a Prague v tabulce weather, to stejné např. v tabulce covid19_basic_differences, kde máme Czechia a v tabulce countries Czech republic. Názvy jsem se snažil sjednotit.

Narazil jsem také na záznamy, kde bylo potřeba změnit nebo převést datový typ. Jako příklad uvádím °C v tabulce o počasí, kde jsem musel odstranit tento znak a převést datový typ na INT, abych s ním mohl dále pracovat. 

Je to můj první takhle velký SQL skript. Budu moc rád za připomínky a návrhy, jak ho udělat rychlejší a efektivnější. Zejména poslední část, kdy připojuji data o počasí. Přestože jsem se snažil o maximální optimalizaci, výsledná tabulka se generuje několik desítek minut.
