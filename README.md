# Verificare TVA

Made by SAVI-NIMS

Aplicație desktop pentru verificarea TVA și a inactivității fiscale la ANAF. Companii românești, până la 100 de rânduri per fișier Excel. Interfață în limba română.

## Descărcare

| Fișier | Link permanent către versiunea curentă |
|---|---|
| Windows 10/11 x64 | [Descarcă aplicația Windows](https://github.com/victor-savinims-legal/anaf-vat-checker-downloads/releases/latest/download/VerificareTVA-Windows-x64.zip) |
| Mac Apple Silicon | [Descarcă aplicația Mac](https://github.com/victor-savinims-legal/anaf-vat-checker-downloads/releases/latest/download/VerificareTVA-Mac-AppleSilicon.dmg) |
| Șablon Excel gol | [Descarcă șablonul](https://github.com/victor-savinims-legal/anaf-vat-checker-downloads/releases/latest/download/Model_Import_Companii.xlsx) |
| Pagina versiunii | [Ultima versiune și verificările pachetelor](https://github.com/victor-savinims-legal/anaf-vat-checker-downloads/releases/latest) |

Nu este necesar un cont GitHub pentru descărcare. Folosiți linkurile de mai sus. Arhivele „Source code” generate automat de GitHub conțin numai documentația acestui repository.

## Pornire

**Windows:** extrageți complet ZIP-ul, rulați `Test instalare.cmd`, apoi `VerificareTVA.exe`. Păstrați subdosarul `_internal` alături de executabil.

**Mac:** deschideți DMG-ul și copiați `VerificareTVA.app` în Applications. Este necesar un Mac cu procesor Apple Silicon și macOS 13 sau ulterior.

**Excel:** completați șablonul cu doar `Denumire societate` și `CUI`, de la rândul 2. Salvați o copie `.xlsx`, încărcați-o în aplicație și apăsați **Verifică la ANAF**. Sunt acceptate până la 100 de rânduri de societăți. Nu sunt necesare alte coloane.

Pachetele includ runtime-ul. Nu trebuie instalat Python. Microsoft Excel nu este necesar pentru import/export, dar puteți folosi Excel sau alt editor compatibil pentru completarea șablonului.

[Instrucțiuni de instalare și utilizare](INSTALLARE.md)

## Semnare și verificare

Windows nu are certificat comercial. Mac are semnătură ad-hoc, fără notarizare Apple. Verificați hash-urile din `SHA256SUMS.txt` și respectați politica IT pentru eventualele avertizări SmartScreen/Gatekeeper. Nu dezactivați global protecțiile sistemului.

Testele automate sunt executate pe Windows Server 2025 x64 și macOS 15 ARM64. Configurația și rețeaua utilizatorului trebuie validate separat. Dovezile pentru versiunea curentă sunt atașate pe pagina release-ului în `VALIDATION.json`.

## Date și actualizări

Excelul original rămâne nemodificat. Doar CUI-ul și data sunt trimise la ANAF. Rapoartele se salvează local la cererea utilizatorului și includ date despre clienți. Rezultatul nu stabilește tratamentul fiscal al tranzacției și nu verifică ONRC.

Linkurile de descărcare rămân identice când se publică o versiune nouă. Aplicația instalată nu se actualizează automat. Descărcați și instalați noul pachet pentru actualizare.

Acest repository public distribuie pachetele și documentația. Repository-ul sursei aplicației este separat și privat. Se păstrează o singură versiune publicată pentru descărcare.
