# Verificare TVA 1.0.4: instalare / installation

Made by **SAVI-NIMS**

[Română](#română) · [English](#english) · [Descărcări / Downloads](https://github.com/victor-savinims-legal/anaf-vat-checker-downloads/releases/latest)

Actualizat la 11 noiembrie 2026. / Updated 11 November 2026.

## Română

### Descărcare și cerințe

Descărcați numai de pe [pagina oficială a proiectului](https://github.com/victor-savinims-legal/anaf-vat-checker-downloads/releases/latest). Nu este necesar un cont GitHub.

| Sistem | Fișier | Cerințe |
|---|---|---|
| Windows | `VerificareTVA-Windows-x64.zip` | Windows 10/11 x64. Pachet portabil, cu runtime inclus. |
| Mac | `VerificareTVA-Mac-AppleSilicon.dmg` | Apple Silicon, macOS 13 sau ulterior. Fără suport Mac Intel. |
| Excel | `Model_Import_Companii.xlsx` | Șablon gol, inclus și în pachete. |

Nu trebuie instalate Python sau Excel pentru rularea aplicației. Pentru completarea șablonului, folosiți un editor compatibil `.xlsx`. Verificarea ANAF necesită internet.

**Windows nu are certificat comercial de semnare. Mac are semnătură ad-hoc, fără Developer ID și fără notarizare Apple.** Pot apărea avertizări la prima deschidere. Acest lucru nu reprezintă o garanție de securitate. Verificați proveniența pachetului și respectați politica IT a organizației.

### Windows: instalare și avertizări

1. Descărcați ZIP-ul. Opțional, comparați SHA256 cu fișierul din același release, conform comenzilor de la final.
2. În File Explorer, clic dreapta pe ZIP, apoi **Extract All / Extragere totală**. Alegeți un dosar în care aveți drept de scriere.
3. Deschideți dosarul extras. **Nu porniți aplicația direct din ZIP.** Păstrați `VerificareTVA.exe` și întregul dosar `_internal` împreună.
4. Rulați `Test instalare.cmd`. Acesta verifică instalarea locală. Dacă raportează o eroare, păstrați rezultatul pentru IT. Nu este o verificare antivirus și nu testează disponibilitatea ANAF.
5. Deschideți `VerificareTVA.exe`.

**Dacă apare „Windows protected your PC” pentru o aplicație nerecunoscută:**

- Confirmați că pachetul provine din repository-ul oficial. Poate apărea **Unknown publisher**, deoarece pachetul nu este semnat comercial.
- Dacă aveți încredere în sursă și politica dispozitivului permite, selectați **More info / Mai multe informații**, apoi **Run anyway / Rulați oricum**. [Microsoft: SmartScreen](https://learn.microsoft.com/en-us/windows/apps/package-and-deploy/smartscreen-reputation).
- Dacă butonul lipsește sau mesajul menționează **Smart App Control**, **blocked by your administrator** ori o restricție de organizație, opriți-vă și consultați IT. Smart App Control nu oferă o excepție pentru o singură aplicație. Această versiune nesemnată poate fi inutilizabilă pe acel dispozitiv. [Microsoft: Smart App Control](https://support.microsoft.com/en-us/windows/security/threat-malware-protection/smart-app-control-frequently-asked-questions).
- Dacă browserul blochează descărcarea, citiți motivul. O avertizare de reputație diferă de o detecție de malware. Consultați IT dacă nu puteți identifica tipul avertizării.

**O alertă de virus, malware sau carantină nu se tratează cu „Run anyway”.** Nu restaurați fișierul și nu adăugați excluderi antivirus pentru a forța rularea. Păstrați mesajul exact pentru verificare. Nu dezactivați Defender, SmartScreen sau Smart App Control.

### Mac: instalare și avertizări

1. Descărcați DMG-ul. În **About This Mac / Despre acest Mac**, verificați că procesorul este Apple Silicon.
2. Deschideți DMG-ul și trageți `VerificareTVA.app` în **Applications / Aplicații**.
3. Deschideți aplicația din Applications. La confirmarea standard pentru un fișier descărcat, selectați **Open / Deschide** numai dacă aveți încredere în sursă.
4. Dacă macOS blochează aplicația deoarece dezvoltatorul nu este verificat sau Apple nu o poate verifica pentru software rău intenționat, închideți alerta. După această încercare, deschideți **System Settings / Configurări sistem → Privacy & Security / Intimitate și securitate**.
5. În zona **Security / Securitate**, identificați mesajul pentru `VerificareTVA` și selectați **Open Anyway / Deschide oricum**, numai dacă ați verificat sursa și acceptați deschiderea. Unele versiuni macOS afișează întâi **Open**. Autentificați-vă dacă vi se solicită și confirmați **Open**.

Denumirile diferă în funcție de limba și versiunea macOS. Butonul poate apărea numai după o încercare recentă de deschidere. Dacă lipsește, încercați din nou aplicația și reveniți la setări. Pe un Mac administrat, consultați IT dacă opțiunea este blocată. [Apple: deschiderea aplicațiilor](https://support.apple.com/en-gb/102445), [Apple: excepția pentru o aplicație](https://support.apple.com/en-euro/guide/mac-help/mh40617/mac).

**Opriți-vă dacă mesajul spune „will damage your computer”, indică malware sau spune că aplicația este deteriorată.** Pentru un fișier deteriorat, descărcați din nou din sursa oficială și comparați SHA256. Dacă problema persistă, solicitați verificarea pachetului. Nu folosiți comenzi pentru eliminarea carantinei sau dezactivarea Gatekeeper.

### Căutare manuală după CUI sau denumire

Pe prima pagină sunt două câmpuri distincte. Este suficientă oricare dintre metode, fără fișier Excel. **Recomandăm CUI-ul** pentru identificare exactă.

- **CUI:** introduceți codul, cu sau fără RO, și apăsați **Verifică CUI**. Cererea merge direct la ANAF. Rezultatul afișează denumirea returnată de ANAF.
- **Denumire societate:** introduceți minimum două caractere și apăsați **Caută denumirea**. Denumirea este trimisă către serviciul extern **CUIScan**, pentru identificare. Alegeți explicit societatea după denumire, CUI, județ și localitate, apoi **Verifică firma aleasă la ANAF**. Chiar și o singură potrivire trebuie selectată.
- Dacă numele selectat diferă de denumirea ANAF, ambele apar în **COMENTARII**. Căutarea după denumire nu stabilește statutul TVA. Verificarea fiscală folosește exclusiv răspunsul direct ANAF.
- Puteți salva același raport Excel și dovezile JSON. Acestea înregistrează metoda de identificare și, după caz, denumirea căutată și societatea selectată.

CUIScan este o sursă terță de identificare. Rezultatele sale pot fi incomplete sau neactualizate. API-ul public documentează maximum 30 de rezultate și 100 de cereri/oră/IP, inclusiv calculatoarele care împart același IP. La indisponibilitate sau limitare, folosiți CUI-ul direct. Aplicația nu trimite către CUIScan fișierul Excel sau căutările făcute prin câmpul CUI. [API](https://cuiscan.ro/api-docs.html), [confidențialitate](https://cuiscan.ro/confidentialitate.html).

### Excel și utilizare

Șablonul are foaia **Companii** și exact două coloane. Păstrați aceste antete:

| Denumire societate | CUI |
|---|---|
| Denumirea legală a companiei | CUI, cu sau fără prefixul RO |

Completați de la rândul 2, maximum 100 de rânduri de companii per foaie. CUI este formatat ca text. Nu utilizați formule. Salvați o copie `.xlsx`. Rândurile complet goale sunt ignorate. Șablonul gol nu produce rezultate.

1. **Deschide Excel…**: selectați copia completată și foaia dorită.
2. **Verifică la ANAF**: verificarea folosește data curentă din București.
3. Citiți statusul și **COMENTARII**, apoi **Salvează raportul…**.

| Culoare | Semnificație |
|---|---|
| Verde | Înregistrare TVA, fără inactivitate fiscală, cu date complete și denumire concordantă dacă a fost furnizată. |
| Roșu | CUI absent/neacceptat, inactivitate fiscală sau anulare TVA confirmată. Citiți motivul. |
| Galben | Date/denumire de verificat ori lipsa înregistrării TVA fără anulare confirmată. |
| Gri | Răspuns ANAF indisponibil, incomplet, neconcordant sau CUI negăsit. Nu confirmă un status fiscal. |

O celulă CUI goală, `-`, text neacceptat sau formulă primește roșu și **CUI nu este prezent**. La diferențe de denumire, **COMENTARII** arată numele din Excel și informația returnată de ANAF.

Exportul creează un dosar nou cu `Raport_TVA.xlsx` și `Dovezi_ANAF.json`. Excelul original rămâne nemodificat. Aplicația trimite către ANAF doar CUI și data, prin HTTPS. Nu încarcă Excelul într-un serviciu propriu și nu include telemetrie. Rapoartele conțin date despre clienți: alegeți un dosar cu acces adecvat, inclusiv dacă este sincronizat în cloud.

Rezultatul acoperă numai TVA și inactivitatea fiscală, nu ONRC, VIES sau tratamentul TVA al unei tranzacții.

### Actualizare și verificare IT

Actualizarea este manuală: închideți aplicația, descărcați ultima versiune și extrageți Windows într-un dosar nou sau înlocuiți aplicația Mac din Applications. Nu combinați runtime-uri din versiuni diferite. Păstrați separat rapoartele.

Pentru IT:

- Comparați SHA256, verificați politica de execuție și scanați pachetul cu protecția organizației.
- Pe Windows, rulați `Test instalare.cmd` din dosarul extras și verificați pornirea interfeței pe configurația țintă.
- Testați importul fără date confidențiale: un CUI cunoscut, unul lipsă și o denumire diferită. Comparați rezultatul cu ANAF pentru aceeași dată.
- Verificați exportul ambelor fișiere și faptul că Excelul original rămâne nemodificat. Lipsa rețelei nu trebuie să producă un rezultat verde.
- Pentru proxy/certificate folosiți configurația aprobată de IT. Nu dezactivați verificarea TLS. Endpoint: `https://webservicesp.anaf.ro/api/PlatitorTvaRest/v9/tva`, HTTPS POST, port 443.
- Testele automate 1.0.4 au rulat pe Windows Server 2025 x64 și macOS 15 ARM64. Nu certifică fiecare configurație Windows 10/11 sau Mac. Dovezile sunt în `VALIDATION.json` din release.

## English

### Downloads and requirements

Download only from the [official project release page](https://github.com/victor-savinims-legal/anaf-vat-checker-downloads/releases/latest). No GitHub account is required.

| System | File | Requirements |
|---|---|---|
| Windows | `VerificareTVA-Windows-x64.zip` | Windows 10/11 x64. Portable package with runtime included. |
| Mac | `VerificareTVA-Mac-AppleSilicon.dmg` | Apple Silicon, macOS 13 or later. Intel Macs are not supported. |
| Excel | `Model_Import_Companii.xlsx` | Blank template, also included in both packages. |

Python and Excel are not required to run the app. Use a compatible `.xlsx` editor to fill in the template. ANAF checks require internet access.

**Windows has no commercial signing certificate. The Mac app has an ad-hoc signature, without Developer ID or Apple notarization.** First-run warnings are possible. This disclosure is not a security guarantee. Check the package source and follow your organization's IT policy.

### Windows: installation and warnings

1. Download the ZIP. Optionally compare its SHA256 with the file from the same release, using the commands below.
2. In File Explorer, right-click the ZIP and select **Extract All**. Choose a folder you can write to.
3. Open the extracted folder. **Do not run the app from inside the ZIP.** Keep `VerificareTVA.exe` and the complete `_internal` folder together.
4. Run `Test instalare.cmd`. It checks the local installation. If it reports an error, retain the output for IT. This is not an antivirus scan and does not test ANAF availability.
5. Open `VerificareTVA.exe`.

**If “Windows protected your PC” reports an unrecognized app:**

- Confirm the package came from the official repository. **Unknown publisher** is possible because there is no commercial signature.
- If you trust the source and your device policy permits, select **More info**, then **Run anyway**. [Microsoft: SmartScreen](https://learn.microsoft.com/en-us/windows/apps/package-and-deploy/smartscreen-reputation).
- If the button is absent or the message names **Smart App Control**, **blocked by your administrator**, or an organization restriction, stop and consult IT. Smart App Control has no per-app override. This unsigned release might not run on that device. [Microsoft: Smart App Control](https://support.microsoft.com/en-us/windows/security/threat-malware-protection/smart-app-control-frequently-asked-questions).
- If the browser blocks the download, read the reason. A reputation warning differs from a malware detection. Consult IT if you cannot identify the warning type.

**Do not treat a virus, malware or quarantine alert as a “Run anyway” case.** Do not restore the file or add antivirus exclusions to force it to run. Retain the exact message for review. Do not disable Defender, SmartScreen or Smart App Control.

### Mac: installation and warnings

1. Download the DMG. Check **About This Mac** to confirm an Apple Silicon processor.
2. Open the DMG and drag `VerificareTVA.app` into **Applications**.
3. Launch it from Applications. For the standard downloaded-file confirmation, select **Open** only if you trust the source.
4. If macOS blocks it because the developer is unverified or Apple cannot check it for malicious software, dismiss the alert. After that launch attempt, open **System Settings → Privacy & Security**.
5. Under **Security**, find the message for `VerificareTVA` and select **Open Anyway** only if you have verified the source and choose to authorize it. Some macOS versions show **Open** first. Authenticate if prompted, then confirm **Open**.

Labels vary by macOS version and language. The button may appear only after a recent launch attempt. If absent, try opening the app again and return to settings. On a managed Mac, contact IT if the option is blocked. [Apple: opening apps safely](https://support.apple.com/en-gb/102445), [Apple: an app-specific exception](https://support.apple.com/en-euro/guide/mac-help/mh40617/mac).

**Stop if the warning says “will damage your computer”, reports malware, or says the app is damaged.** For a damaged download, download again from the official source and compare SHA256. If it persists, request a package review. Do not run commands to remove quarantine or disable Gatekeeper.

### Manual search by CUI or company name

The home screen has two separate fields. Either method works without an Excel file. **CUI is recommended** for exact identification.

- **CUI:** enter the tax identifier, with or without RO, and select **Verifică CUI** (Check CUI). The request goes directly to ANAF. The result displays the company name returned by ANAF.
- **Denumire societate:** enter at least two characters and select **Caută denumirea** (Search name). The name is sent to the external **CUIScan** service for identification. Explicitly select the company using its name, CUI, county and locality, then **Verifică firma aleasă la ANAF** (Check selected company with ANAF). Even a single match requires selection.
- If the selected name differs from ANAF's name, **COMENTARII** shows both. Name discovery does not determine VAT status. Fiscal results come exclusively from the direct ANAF response.
- Save the same Excel report and JSON evidence. These record the identification method and, where applicable, the search term and selected company.

CUIScan is a third-party identity source. Its results may be incomplete or out of date. Its public API documents up to 30 results and 100 requests/hour/IP, shared by devices using the same public IP. If unavailable or limited, use CUI directly. The app does not send the workbook or CUI-field searches to CUIScan. [API](https://cuiscan.ro/api-docs.html), [privacy](https://cuiscan.ro/confidentialitate.html).

### Excel input and use

The template contains the **Companii** sheet and exactly two columns. Keep these Romanian headers:

| Denumire societate | CUI |
|---|---|
| Legal company name | Romanian tax identifier, with or without RO |

Start on row 2, with up to 100 company rows per sheet. CUI uses text format. Do not use formulas. Save an `.xlsx` copy. Completely empty rows are ignored. A blank template has no companies to check.

The app interface is in Romanian:

1. **Deschide Excel…** (Open Excel): choose the completed copy and sheet.
2. **Verifică la ANAF** (Check with ANAF): uses the current date in Bucharest.
3. Review the status and **COMENTARII** (comments), then **Salvează raportul…** (Save report).

| Colour | Meaning |
|---|---|
| Green | VAT registered, not fiscally inactive, with complete data and a matching name when supplied. |
| Red | Missing/unaccepted CUI, fiscal inactivity or confirmed VAT cancellation. Read the reason. |
| Yellow | Data/name needs review, or not VAT registered without confirmed cancellation. |
| Grey | ANAF response unavailable, incomplete, inconsistent, or CUI not found. No fiscal status is confirmed. |

A blank CUI, `-`, unaccepted text or formula is red with **CUI nu este prezent** (CUI is missing). For name differences, **COMENTARII** shows the Excel name and ANAF information.

Export creates a new folder with `Raport_TVA.xlsx` and `Dovezi_ANAF.json`. The original Excel stays unchanged. The app sends only CUI and the check date to ANAF over HTTPS. It does not upload the workbook to its own service or include telemetry. Reports contain client data: choose a folder with appropriate access, including cloud-synced folders.

Scope is VAT and fiscal inactivity only, excluding ONRC, VIES and transaction tax treatment.

### Updates and IT acceptance

Updates are manual: close the app, download the latest package, then extract Windows into a new folder or replace the Mac app in Applications. Do not mix runtime files from different versions. Keep reports separately.

For IT:

- Compare SHA256, review application-control policy and scan the package with the organization's protection tools.
- On Windows, run `Test instalare.cmd` from the extracted folder and check the interface launches on the target device.
- Test import without confidential data: a known CUI, a missing CUI and a different company name. Compare results against ANAF for the same date.
- Check both output files export and the original Excel remains unchanged. An unavailable network must not produce a green result.
- Use IT-approved proxy/certificate configuration. Keep TLS verification enabled. Endpoint: `https://webservicesp.anaf.ro/api/PlatitorTvaRest/v9/tva`, HTTPS POST, port 443.
- Version 1.0.4 automated tests ran on Windows Server 2025 x64 and macOS 15 ARM64. They do not certify every Windows 10/11 or Mac configuration. See the release's `VALIDATION.json`.

## SHA256: verificare opțională / optional verification

Descărcați `SHA256SUMS.txt` din **același release** ca pachetul și comparați întregul hash pentru exact acel fișier. O potrivire confirmă identitatea cu pachetul publicat, nu absența malware-ului. Dacă diferă, nu rulați pachetul.

Download `SHA256SUMS.txt` from the **same release** as the package and compare the complete hash for that exact file. A match confirms identity with the published file, not freedom from malware. If it differs, do not run the package.

Windows PowerShell, folosind calea reală / using your actual download path:

```powershell
Get-FileHash -Algorithm SHA256 -LiteralPath "$env:USERPROFILE\Downloads\VerificareTVA-Windows-x64.zip"
```

Mac Terminal, folosind calea reală / using your actual download path:

```sh
shasum -a 256 "$HOME/Downloads/VerificareTVA-Mac-AppleSilicon.dmg"
```

[SHA256SUMS.txt](https://github.com/victor-savinims-legal/anaf-vat-checker-downloads/releases/latest/download/SHA256SUMS.txt) · [VALIDATION.json](https://github.com/victor-savinims-legal/anaf-vat-checker-downloads/releases/latest/download/VALIDATION.json)

Licențele bibliotecilor sunt în `THIRD_PARTY_NOTICES.md` și `licenses` din runtime. / Library licenses are in `THIRD_PARTY_NOTICES.md` and the runtime's `licenses` folder.
