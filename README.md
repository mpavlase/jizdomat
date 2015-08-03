Jízdomat CLI
=====
Note: just scroll down for english version

Přehled
------
`jizdomat` je šikovná utilita do příkazové řádky, se kterou můžete snadno zjistit volná místa na portálu http://jizdomat.cz (a od něj odvozených) mezi zadanými městy a je napsán pro python2.

Použití
------
1. Zkopírujte soubor `jizdomat.conf.sample` do `jizdomat.conf` and nezapomeňte změnit `api_key` na váš
2. A můžeme vyrazit :-) Například se potřebujeme dostat z Ostravy do Brna, ale až za 3 dny. Dotaz pak bude vypadat takto:
`./jizdomat -f ostrava -t brno -d 3`. Dostaneme zhruba takovýto výstup (jména řidičů jsou vymyšlená):
```
07/26 (+4, Sun) 19:00, 150 Kc, 2 free, Adam Klobouček (Ostrava ➤ Brno)
07/27 (+5, Mon) 08:00, 0 Kc, 2 free, Blanka Mistrová (Opava ➤ Portorož)
07/27 (+5, Mon) 09:00, 250 Kc, 2 free, Čeněk Vočadlý (Havířov ➤ Pasohlávky)
07/28 (+6, Tue) 15:00, 150 Kc, 3 free, David Drtikol (Havířov ➤ Znojmo)
08/02 (+11, Sun) 15:00, 330 Kc, 3 free, Eva Volejníková (Karviná ➤ Praha)
```
Dejte tomu, že je dneska 22.7.2015. Nejbližší volná jízda je za 4 dny a bude řídit Adam Klobouček. API Jízdomatu vyhledává i v částech trasy, kterými zadaná města prochází (mezi Havířovem a Znojmem je po cestě Ostrava i Brno).

Dostupné přepínače
-------

| Přepínač | Popis |
| ---- | ---- |
|*-h, --help* | zobrazí nápovědu ke všem parametrům |
|*-f city_from, --from city_from* | Město odkud chcete cestovat (default: ostrava) |
|*-t city_to, --to city_to* | Cíl cesty (default: brno) |
|*-d days, --days days* | Nejdříve za kolik dní dopředu hledat jízdy? (default: 0) | 
|*-l limit, --limit limit* | Maximum výsledků (default: 10) |
|*-r, --reverse* | Obrátí směr hledání 'city_from' a 'city_to' (default: False) |
|*-a, --all* | Zobrazí úplně všechny jízdy, tj. včetně již obsazených. (default: False) |
|*--long-location* | Zobrazovat plné (dlouhé) popisky míst odjezdu a příjezdu (default: False) |

Všechny přepínače jsou také popsány v `jizdomat -h`.

TODO
-----
* dopsat testy
* zkusit si z toho udělat balíček pro pip
***

Overview
----
`jizdomat` is handy tool for command line usage for doing queries agains http://jizdomat.cz (and derivates) written for python2. You will see nicely structured list of spare seats between given cities.

Quick start
-----
1. Copy `jizdomat.conf.sample` to `jizdomat.conf` and change `api_key` to yours
2. Let's take some journey! :-) For example, you need to travel from Ostrava to Brno by next 3 days. So you can do that by this way:
`./jizdomat -f ostrava -t brno -d 3`. You will get output similar to this one (names are fictious):
```
07/26 (+4, Sun) 19:00, 150 Kc, 2 free, Adam Klobouček (Ostrava ➤ Brno)
07/27 (+5, Mon) 08:00, 0 Kc, 2 free, Blanka Mistrová (Opava ➤ Portorož)
07/27 (+5, Mon) 09:00, 250 Kc, 2 free, Čeněk Vočadlý (Havířov ➤ Pasohlávky)
07/28 (+6, Tue) 15:00, 150 Kc, 3 free, David Drtikol (Havířov ➤ Znojmo)
08/02 (+11, Sun) 15:00, 330 Kc, 3 free, Eva Volejníková (Karviná ➤ Praha)
```
Let's say, today is 2015-07-22, so now we see that closest journey will take place after at least 4 days, Adam Klobouček is name of driver. The API provide also matching sub-parts of journeys. That's why there are other than yours cities.

| Param | Description |
| ---- | ---- |
|*-h, --help* | show this help message and exit |
|*-f city_from, --from city_from* | City from you want to travel (default: ostrava) |
|*-t city_to, --to city_to* | Your destination (default: brno) |
|*-d days, --days days* | How many days in relative to current date you want to travel? (default: 0) | 
|*-l limit, --limit limit* | Maximum of results (default: 10) |
|*-r, --reverse* | Swap city_from and city_to values (default: False) |
|*-a, --all* | Show all journeys, so also those are full. By default it shows just available (default: False) |
|*--long-location* | Show full location description. By default it is shortened to just name of city, without more specific location (default: False) |

All available switches are described in help `jizdomat -h`

