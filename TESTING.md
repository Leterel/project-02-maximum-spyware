# Tests und Reproduzierbarkeit — Maximum Spyware

## Voraussetzungen
JDK 21; Android SDK Platform/Build Tools 36; PowerShell 7.

## Befehle
```text
node --test tests/*.test.mjs
```

Start/Build: In frischer isolierter Arbeitskopie: ./build-native.ps1 -SdkPath $env:ANDROID_SDK_ROOT -JavaHome $env:JAVA_HOME. Nur Emulator.

## Tatsächlicher Befund vom 02.11.2026
3797 Produktionsprüfungen und 18 Consent-Gate-Prüfungen bestanden; frischer Offline-APK-Build samt Signatur/Ausrichtung bestanden. Node: 1 bestanden, 2 Signiertests ausgelassen.

Bei fehlenden Paketen/Hardware/Betriebssystemen ist das Ergebnis „nicht ausgeführt“, kein Pass. Plattformnachweise aus älteren Detailberichten gelten nur für die dort genannten Versionen. Android-Automatisierung ausschließlich mit expliziter emulator-Seriennummer und bestätigtem ro.kernel.qemu=1. Physische Geräte, persönliche Medien und Produktionskonten sind keine Testfixtures.

## Vor Merge
`git diff --check` ausführen; relevante Funktionstests wiederholen, wenn Codeänderungen ihren Befund entwerten. Speicherdaten/alte Versionen erhalten. Fehlende externe Abnahmen in HANDOFF.md benennen.
