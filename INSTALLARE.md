# Verificare TVA 1.0.3

Made by SAVI-NIMS

Aplicație pentru Windows x64 și Mac Apple Silicon. Verifică înregistrarea TVA și inactivitatea fiscală ANAF pentru companii românești, maximum 100 de rânduri per foaie.

## Instalare

**Windows:** extrageți complet ZIP-ul. Păstrați `VerificareTVA.exe` împreună cu `_internal`. Rulați `Test instalare.cmd`, apoi deschideți aplicația. Nu este necesară instalarea Python sau Excel pentru import și export. Pachetul este portabil, destinat Windows 10/11 x64.

**Mac:** deschideți DMG-ul și trageți `VerificareTVA.app` în Applications. Pachetul este pentru Apple Silicon, macOS 13 sau ulterior. Nu include versiune Intel.

Windows nu are certificat comercial de semnare. Mac are semnătură ad-hoc, fără notarizare Apple. La o blocare SmartScreen/Gatekeeper sau prin politica organizației, verificați proveniența și consultați IT. Nu dezactivați global protecțiile sistemului. Testarea configurației și rețelei organizației rămâne necesară.

## Tabelul Excel

Folosiți `Model_Import_Companii.xlsx`, inclus în pachet și disponibil separat pe pagina de descărcare. Conține o singură foaie, `Companii`, cu exact două coloane:

| Denumire societate | CUI |
|---|---|
| Completați denumirea legală a societății | Completați CUI-ul, cu sau fără RO |

Datele se introduc de la rândul 2. Șablonul are 100 de rânduri libere și CUI formatat ca text. Nu introduceți formule în coloana CUI. Salvați o copie `.xlsx`. Rândurile complet goale se ignoră. Dacă încărcați șablonul înainte de completare, aplicația anunță că nu există rânduri de clienți. Formatul anterior cu `Client` și `CUI cumparator` rămâne acceptat.

## Utilizare

1. Apăsați **Deschide Excel…** și selectați copia completată.
2. Apăsați **Verifică la ANAF**. Se folosește data curentă în București.
3. Citiți rezultatele și **COMENTARII**, apoi **Salvează raportul…**.

Verde înseamnă TVA înregistrat, fără inactivitate fiscală, cu date complete și denumire concordantă. Roșu indică CUI absent/neacceptat, inactivitate fiscală sau anulare TVA confirmată. Galben indică date/denumire de verificat ori lipsa înregistrării TVA fără anulare confirmată. Gri înseamnă verificare nereușită, incompletă sau neconcordantă.

O celulă CUI goală, `-`, text neacceptat sau formulă produce roșu și nota **CUI nu este prezent**. Diferențele de denumire sunt explicate în **COMENTARII**, cu numele din Excel și cel returnat de ANAF. La o eroare de conexiune, aplicația nu păstrează un rezultat verde din verificarea precedentă.

Originalul Excel nu este modificat. Exportul creează un subdosar nou cu `Raport_TVA.xlsx` și `Dovezi_ANAF.json`. Fișierele includ datele clienților și trebuie păstrate într-un dosar cu acces adecvat.

## Conexiunea ANAF

Aplicația trimite numai CUI și data prin HTTPS POST la `https://webservicesp.anaf.ro/api/PlatitorTvaRest/v9/tva`. Nu încarcă Excelul într-un serviciu propriu și nu include telemetrie. Pentru proxy și certificate, utilizați configurația aprobată de IT. Verificarea TLS rămâne activă.

Rezultatul privește numai TVA și inactivitatea fiscală. Nu verifică ONRC sau VIES și nu stabilește tratamentul TVA al unei tranzacții.

## Actualizare

Închideți aplicația, descărcați noul pachet de la linkul permanent și instalați-l într-un dosar separat sau înlocuiți aplicația Mac. Nu amestecați executabilul cu fișierele runtime ale altei versiuni. Rapoartele salvate separat rămân disponibile. Aplicația nu se actualizează automat.

Ultima versiune: https://github.com/victor-savinims-legal/anaf-vat-checker-downloads/releases/latest

Licențele bibliotecilor incluse sunt în `THIRD_PARTY_NOTICES.md` și în dosarul `licenses` din runtime.
