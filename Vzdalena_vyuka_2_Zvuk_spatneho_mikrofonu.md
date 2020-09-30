Strukturovanější doplněk k videu https://youtu.be/r6_77ZlApPY

# Jak na vzdálenou výuku (část 2) - Jak vylepšit zvuk špatného mikrofonu

V tomto tutorialu budeme používat další z volně dostupných softwarů pro Windows, tentokrát zaměřených na procesování audia téměř v reálném čase. Jde o programy **VoiceMeeter Banana** a **Cantabile Lite** a o **VST pluginy**.

## Co který software vlastně dělá?

### VoiceMeeter Banana
Tento program zahrnuje jednak **virtuální zvukovou kartu**, jednak program pro její obluhování ve formě **mixpultu** umožňujícího kombinovat vstupy a výstupy ostatních zvukových karet.

### VST pluginy
VST (Virtual Studio Technology) je softwarové rozhraní pro komunikaci softwaru a pluginů upravujících digitální audio signál. V principu jde o simulaci původně analogového zařízení nahrávacích studií. Technologie byla vyvinuta firmou Steinberg a jde o otevřený standard, díky čemuž vznikají i nekomerční pluginy. Pro více informací se podívejte na příslušný článek [Wikipedie](https://cs.wikipedia.org/wiki/Virtual_Studio_Technology). V tomto případě používáme efekty, které specifickým způsobem procesují zvuk.

### Cantabile Lite
Cantabile Lite je tzv. VST Host, tedy program, ve kterém je možno používat VST pluginy (nebo nástroje, ale to je mimo záběr tohoto tutoriálu). Tyto plaginy je zde možné organizovat a ukládat si jejich nastavení.

## Odkazy ke stažení
- [Voicemeeter Banana](https://vb-audio.com/Voicemeeter/index.htm)
- [Cantabile Lite](https://www.cantabilesoftware.com/free-vst-host)
- VST pluginy (Pokud je to možné, stahujeme 64-bitové VST2 pluginy. Není možné kombinovat 32- a 64-bitové pluginy.)
  - [ReaPlugs](https://www.reaper.fm/reaplugs/)
  - [Dead Duck plugins](http://deadducksoftware.blogspot.com/)
  - [TDR VOS SlickEQ](https://www.tokyodawn.net/tdr-vos-slickeq/)
  - [TDR Kotelnikov](https://www.tokyodawn.net/tdr-kotelnikov/)
  - [TDR Nova](https://www.tokyodawn.net/tdr-nova/)
  - [Polyverse Wider](https://polyversemusic.com/products/wider/)
  - [LoudMax](https://www.kvraudio.com/product/loudmax-by-thomas-mundt)

## Instalace
Postupujeme podle doporučení instalačních balíčků. Jako první nainstalujeme VoiceMeeter, následně buď nainstalujeme nebo zkopírujeme VST pluginy do jedné libovolné složky, bežně *C:\Program Files\VST Plugins*, ale není to nutné. Jako poslední naistalujeme software Cantabile Lite při jehož instalaci je nutné nastavit jako Audio Driver **ASIO - VoiceMeeter Insert Virtual ASIO** a příslušnou cestu k VST pluginům. 

## Prostředí jednotlivých programů
### VoiceMeeter Banana
Pro fungování virtuální zvukové karty **musí být spuštěn** program VoiceMeeter nebo VoiceMeeter Banana. Obojí jsou dvě různě rozsáhlé varianty téhož. V rámci VoiceMeeteru je nutné nastavit několik věcí – vstupy, výstupy a jak mají být tyto vzájemně propojeny. Výsledek by měl vypadat podobně jako na obrázku níže.

![VoiceMeeter]()

Dále už pouze **posuvníky korigujeme hlasitost**. Program sám má vestavěný ekvalizér, kompresor a gate, ale ty nebudeme nyní potřebovat, protože využijeme stažené pluginy.

Vedle posuvníků jsou také tlačítka **A** a **B**. **A** značí hardwarový výstup, **B** softwarový. **Mikrofonní vstup pouštíme do A výstupu zásadně pouze pokud se jedná o sluchátka, nikdy pokud výstup směřuje do reproduktorů.** Nejde tak docela o zásadu, pouze o to, že puštění mikrofonního signálu zpět do reproduktorů může způsobit vazbu (pištění), které může poškodit nebo i zničit reproduktor. 

### Cantabile Lite
Uživatelské rozhraní tohoto programu zahrnuje jednak levou část zahrnující hlasitosti na vstupu výstupu a informace o zatížení systému, jednak dominantní čast zobrazující routing jednotlivých pluginů. Pro zdárné fungování potřebujeme vytvořit souvislý řetěz z levé strany (Main Microphone) na pravou (Main Speakers) jak je ukázáno na přiloženém obrázku.

![Cantabile Lite]()

Jednotlivé pluginy přidáváme kliknutím na plus v poli nebo pravým tlačítkem a následným výběrem ze seznamu. Propojení pak probíhá tažením z výstupu jednoho do vstupu druhého pluginu.

Pro ukázku jsem sestavil dva [soubory](https://uloz.to/file/FwN7TwznPO8O/cantabile-rar), které jsem využil při natáčení videa.

## Prostředí VST pluginů
### ReaEQ
Čtyřpásmový **ekvalizér** s možností nastavení typu, centrální frekvence, zisku a šířky pásma. V našem případě použitý jako **High Pass Filter**, který odřezává ze signálu nežádoucí basové frekvence. Nastavení příliš vysoké frekvence zároveň způsobuje nežádoucí deformaci hlasového projevu.

### ReaFir
**Odstraňovač šumu** umožňující fungovat v několika módech. Z nich se jako nejlépe použitelný jeví mód **Subtract** odečítající předem nahraný vzorek šumu pozadí/mikrofonu. To se provede pomocí zaškrtnutí a odzaškrtnutí políčka **Automatically build noise profile**. To vytvoří profil šumu následně odečítaný od vstupu.

### TDR VOS SlickEQ
Jednoduchý třípásmový **ekvalizér**. Je možné zvolit z několika "národních" možností tvaru ekvalizovaného pásma. Tímto pluginem je možné docílit lepší přirozenosti hlasu. Je potřeba si u tohoto pluginu dát pozor na extrémy. Dobrá ekvalizace je decentní: Používáme spíše širší pásma (bandwith) a nižší absolutní hodnoty zisku (gain).

### TDR Nova
Až 4 pásmový ekvalizér s možností **pásmového kompresoru**. To je efekt potlačující hlasitostní extrémy v signálu pomocí definovaného **poměru** (Ratio) ztlumování signálu hlasitějšího než je nastavený **práh** (Treshold). Kromě klasických parametrů ekvalizéru zde tedy můžeme spustit kompresor tlačítkem **Treshold**, díky čemuž můžeme následně nastavit práh a poměr komprese. Tímto způsobem je možné efektivně potlačit sykavky nebo retnice.

### TDR Kotelnikov
Jde o **kompresor**, který je použit na celý signál. Používá se pro snížení vlivu změn polohy řečníka vůči mikrofonu, jinak řečeno pro stabilizování výstupní hlasitosti. Ani s tímto efektem by se to nemělo přehánět, protože dynamika přednesu je samozřejmě důležitá ve vztahu k udržení pozornosti posluchačů.

### DD Expander
**Expander** funguje na podobném (a zároveň opačném) principu jako kompresor - snižuje hlasitost pod daným prahem. Je jím tedy možné účinně potlačit potiché ruchy pozadí (klikání apod.) přičemž je méně ofenzivní vůči signálu než tzv. **noise gate**, který zvuk pod určitým prahem vůbec nepouští dál, což může působit v případě řeči nepřirozeně.

### Wider
Tento efekt vytváři **iluzi stereo zvuku**, tedy jisté prostorovosti.

### LoudMax
Na konec řetězce je možné zařadit tento **limiter**, který signál drží pod určitým prahem tak, aby nedošlo k jeho přebuzení.

## Propojení s ostatním softwarem (OBS, MS Teams apod.)
Pro propojení s jakýmkoli softwarem je pouze nutné nastavit jako mikrofonní vstup **VoiceMeeter Output (VB-Audio VoiceMeeter VAIO)**