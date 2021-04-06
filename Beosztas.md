<span class="small">*// ez az oldal
[innen](https://blackbelt.atlassian.net/wiki/spaces/BAVIMP/pages/547815539)
lett tükrözve //*</span>

<div>

</div>

<div id="main-content" class="wiki-content"
inline-comments-target="true">

A felhasználó beosztását reprezentáló osztály.

A Beosztás egy példánya a felhasználót beosztja egy szerepkörében egy
szervezeti egységbe egy adott napon:

-   A beosztás mindig a felhasználó egy létező szerepköréhez
    kapcsolódik:

    <div class="preformatted panel conf-macro output-block"
    style="border-width: 1px;" hasbody="true" macro-name="noformat"
    macro-id="5369c7cd-f4d1-4180-85b7-5ec854159abe">

    <div class="preformattedContent panelContent">

        Context Felhasznalo
        inv: self.beosztasok → forAll( b:Beosztas | self.szerepkorok->includes(b.szerepkor) )

    </div>

    </div>

-   Ha egy felhasználó elveszíti valamely szerepkörét, akkor törölnünk
    kell a kapcsolódó beosztásokat is. Lásd
    [Felhasznalo.szerepkorDetachCustom()](/PIM/felhasznalo-(csomag)/Felhasznalo.md)
    művelet.

-   Egy felhasználó egy szerepkörében több szervezeti egységhez is be
    lehet osztva. (pl. általában raktáros a zálogfiók1-ben, de pluszban
    beosztották "besegíteni" a zálogfiók2-be is.)

# Attribútumok

-   **felhasznalo** - melyik felhasználó
-   **szerepkor** - milyen szerepkörében
-   **szervezet** - melyik szervezetbe van beosztva
-   **napja** - melyik napra: opcionális. Ha nincs megadva, akkor az
    állandó beosztást jelent.
-   **aktiv\_e** - a felhasználó ki- / bekapcsolhatja a beosztását,
    ezzel mintegy szerepkört választ magának

### Jogosultságok:

Lásd a vonatkozó képernyőket. Összefoglalva:

-   user is **&lt;UserAdmin&gt;** - a felhasználó beoszthat bármely
    felhasználót bármilyen szervezeti egységhez, illetve kezelheti vagy
    törölheti bármelyik beosztást a rendszerben.
-   user is **&lt;org/StaffAdmin&gt;**  - a felhasználó beoszthat
    *bármely felhasználót* az <u>org</u> szervezeti egységhez, illetve
    kezelheti vagy törölheti az <u>org</u> szervezeti egységbe történt
    beosztásokat.

Másként:

A szervezeti hierarchia, illetve a felhasználók szervezeti besorolása
független attól, hogy  ki milyen beosztásokat kezelhet. A
&lt;UserAdmin&gt; joggal bármilyen beosztást kezelni lehet, míg a
&lt;org/StaffAdmin&gt; joggal bármilyen org-ba történő beosztást kezelni
lehet. Az &lt;org/staffAdmin&gt; jogot megkaphatja az org vezetője
(fiókvezető), de a modell szerint akárki más is, pl. egy régióvezető,
vagy a munka szervezésért felelős más személy a zálogfiókban.

Megjegyzés: Az **&lt;org/staffAdmin&gt;** jogosultság a felhasználó
org-ba történt beosztásból származik... Lásd [Jogosultságok
kezelése](/Jogosultsagok-kezelese.md) oldal.

</div>
