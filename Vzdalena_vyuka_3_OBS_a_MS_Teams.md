Strukturovanější doplněk k videu 

# Jak na vzdálenou výuku (část 3) - Propojení OBS a MS Teams

Po úvodu do OBS a poznámkách týkajících se zvuku se dostáváme k důležité kapitole: Jak využít OBS při výuce v reálném čase?

Samozřejmě, v minulém tutorialu jsme cíleně nastavovali audio tak, aby ho bylo možné použít v různých aplikacích, ale co když nás vnější okolnosti lákají nebo nutí k použití funkcionality OBS v podobě separace zdrojů nebo přepínání scén? 

V takovém případě máme dvě základní možnosti:

1.   Streamování videa
2.   Nastavení virtuální webkamery

Oběma variantám se budeme podrobněji věnovat v následujících kapitolách, pokaždé ve spojení s MS Teams, a to ne kvůli jakékoli jedičnosti této aplikace, ale pouze kvůli její rozšířenosti v rámci výuky. Tento návod by měl být samozřejmě z větší části aplikovatený i na ostatní software.

## Streamování videa z OBS do MS Stream

Uvažujeme-li, že máme nastavené OBS pro nahrávání videa a audia podle minulých návodů, zbývá nám poměrně málo kroků.

### Postup vytvoření streamu
Pro vytvoření živé události je nutné jít do **kalendáře** aplikace MS Teams a tam zvolit **Nová schůzka** a **Živá událost**.

![Vytvoření živé události](obr/3_1_udalost.png)

Jako první v nastavení události je nutné nastavit její **jméno a čas konání**.

![Zadání jména události a času jejího konání](obr/3_2_jmeno_a_cas.png)

Poté nastavíme, kdo bude mít k videu **přístup**. Video nenastavujeme veřejné.

![Udělení přístupu](obr/3_3_pristup.png)

Scrollujeme níže a zvolíme možnost produkce na **Externí aplikace nebo zařízení**.

![Nastavení produkce](obr/3_4_externi.png)

V dalším kroku získáme **odkaz pro účastníky**.

![Odkaz pro účastníky](obr/3_5_odkaz.png)

Nasledně scrollujeme níže a otevřeme odkaz na webové rozhraní služby **MS Stream**.

![Odkaz do MS Stream](obr/3_6_stream.png)

Zde vyvoláme nastavení **Aktualizovat podrobnosti o videu**.

![Vyvolání nastavení streamu](obr/3_7_navigace.png)

Poté zkopírujeme adresu **URL ingestace serveru** a spustíme **nastavování streamu**.

![Kopírování adresy a spuštění nastavování](obr/3_8_nastaveni.png)

Jdeme do **nastavení OBS**, kde na kartě **Vysílání** zvolíme službu Vlastní..., vložíme zkopírované URL a zadáme libovolný (povinný) Vysílací klíč.

![Nastavení vysílání v OBS](obr/3_9_vysilani_obs.png)

Zkontrolujeme stav streamu v prohlížeči a pokud je stream připraven na připojení, můžeme v OBS spustit vysílání.

![Stav pro spuštění streamu](obr/3_10_pripraveno.png)

![Začít vysílat](obr/3_11_zacit_vysilat.png)

Dále už je potřeba pouze událost spustit.

![Zahájit](obr/3_12_zahajit_udalost.png)

A ukončit.

![Ukončit](obr/3_13_ukoncit.png)

### Výhody a nevýhody

Hlavní výhodou tohoto přístupu by měla být hlavně stabilita audio i video kvality, naproti tomu hlavní nevýhodou je poměrně velká latence vysílání. Z toho můžeme hlavní využití tohoto přístupu shrnout na webináře, přednášky a výklady, při kterých není vyžadována okamžitá interakce s posluchačem.

## Vytvoření virtuální webkamery pro videohovory

Alternativou k výše zmíněnému je instalace rozšíření OBS pod názvem [OBS Virtualcam](https://obsproject.com/forum/resources/obs-virtualcam.949/) pro Windows, v případě využívání Macu [obdobný plugin](https://github.com/johnboiles/obs-mac-virtualcam), nebo v případě Linuxu rozšíření [OBS V4L2sink](https://github.com/CatxFish/obs-v4l2sink).

Všechna tato rozšíření umožňují vytvoření virtuální webkamery zobrazující živý náhled v OBS. Tu je dále možné použít v téměř libovolném videohovoru.

My se budeme dále věnovat pouze variantě pro Windows.

### Instalace a nastavení

Z [repozitáře](https://github.com/Fenrirthviti/obs-virtual-cam/releases) nejdříve stáhneme instalační balíček pro windows.

![](obr/3_14_download_vc.png)

Nainstalujeme rozšíření a spustíme OBS.

V OBS rozklikneme v horní liště **Nástroje** a **VirtualCam**.

![](obr/3_15_settings_nav.png)

Spustíme virtuální kameru tlačítkem **Start**.

![](obr/3_16_start.png)

Otevřeme nastavení MS Teams.

![](obr/3_17_settings_teams.png)

V tomto okamžiku by se měla kamera objevit v **nastavení MS Teams**, případně může být nutné Teams **restartovat**, aby došlo k obnovení seznamu dostupných zařízení.

![](obr/3_18_obs_cam_set.png)

Následně už je pouze nutné zjistit metodou pokus omyl, zda je obraz **zdrcadlený či nikoliv** z pohledu účastníka schůzky. (Tento fakt se může lišit od náhledu v nastavení aplikace). 

Pokud je zrcadlení opačné, lze ho změnit v rozšíření VirtualCam (položka **Horizontal Flip**). To může způsobovat jeho pád. V takovém případě je nutné zrcadlit scénu nebo obraz v nastavení videokonference (což není umožněno v MS Teams).

Po konci videohovoru nám nezbývá nic než zastavit virtuální kameru.

![](obr/3_19_stop.png)

### Výhody a nevýhody
Hlavní výhodou tohoto přístupu je nízká latence vysílání zvuku i videa, což může být nezbytné při seminářích a cvičeních, kde se vyžaduje interance s posluchači. Naproti tomu kvalita obrazu může lehce pokulhávat.

Je třeba zmínit, že samotné MS Teams nabízí značnou podporu výuky, takže je dobré doporučit prvně důkladné prozkoumání těchto možností a poté je doplnit třeba jen o vylepšení zvuku.

