# SheetLedger – Benutzerhandbuch & Hilfe

[ View in English 🇺🇸 ](help)

---

### ⚡ 1. App-Start & Verbindungsstabilität
* **Synchronisierung beim Start:** SheetLedger synchronisiert beim Starten der Anwendung Ihren lokalen Zustand mit Ihrem Cloud-Hauptbuch.
* **Google API-Quota-Limits:** Die Google Sheets-APIs unterliegen weltweit strengen Nutzungslimits pro Minute. Wenn Ihr lokales Hauptbuch ein hohes Volumen an Batch-Operationen aufweist, können Synchronisierungsanfragen in eine Warteschlange gestellt und leicht verzögert werden.
* **Verbindungsfehler:** Wenn eine Synchronisierung oder Google Drive-Autorisierung aufgrund vorübergehender Netzwerküberlastung oder API-Rate-Limiting fehlschlägt, **keine Panik**. Ihre lokalen Daten sind absolut sicher. Warten Sie einfach einen Moment und versuchen Sie es erneut.

### 💎 2. Abonnementstufen & Google Sheets-Kontingente
Um zu verhindern, dass ein einzelner Nutzer das gesamte API-Verkehrskontingent erschöpft, und um die Stabilität des Dienstes für alle zu gewährleisten, **ist die maximale Anzahl gleichzeitig verknüpfter Google Sheets basierend auf Ihrer Abonnementstufe (Kostenlos vs. Premium) beschränkt**. Bitte überprüfen Sie das In-App-**Abonnement-Menü**, um Ihre aktuellen Limits einzusehen.

### ✈️ 3. Echte Offline-Funktionalität (Local-First)
* **Keine Netzwerkabhängigkeit:** SheetLedger ist als reine Local-First-Anwendung konzipiert. Sie können Ihre Finanzdaten überall einsehen, hinzufügen oder bearbeiten – selbst im Flugzeug oder ohne jegliche Verbindung.
* **Automatische Wiederaufnahme:** Sobald Ihr Gerät wieder eine Netzwerkverbindung herstellt, nimmt unsere interne State Machine den Betrieb im Hintergrund automatisch wieder auf und lädt Ihre zwischengespeicherten Änderungen sicher in die Cloud hoch.

### ⚠️ 4. Wichtig: Bearbeiten Sie das Google Sheets-Dokument nicht manuell
* **Kryptografische & strukturelle Integrität:** Das verknüpfte Google Sheets-Dokument fungiert als verschlüsselter Speicher-Backend. SheetLedger erzwingt strenge kryptografische Validierungen und relationale Schema-Prüfungen.
* **Risiko von Datenkorruption:** **Fügen Sie niemals manuell Zeilen, Zellen oder Spalten direkt in der Web- oder Mobiloberfläche von Google Sheets hinzu, löschen oder ändern Sie diese nicht.** Manuelle Eingriffe verletzen den Hash zur Überprüfung der Datenkonsistenz. Dies führt dazu, dass die App das Hauptbuch als beschädigt eingestuft, um Ihre Finanzsicherheit zu schützen. Alle Operationen müssen über die SheetLedger-App ausgeführt werden.

### 👥 5. Synchronisierung zwischen mehreren Geräten
Sie können sich mit Ihrem persönlichen Google-Konto auf mehreren Geräten (z. B. Ihrem Android-Smartphone und -Tablet) gleichzeitig sicher anmelden. Die Local-First-Architektur sorgt dafür, dass alle Geräte über die Cloud sicher auf dem selben Hauptbuchstand zusammengeführt werden.

### 🤝 6. Sichere Zusammenarbeit für mehrere Benutzer (Gemeinsame Hauptbücher)
SheetLedger unterstützt nativ die verteilte Buchhaltung für mehrere Benutzer mit Zugriffskontrolle auf Branchenniveau:
1. **So teilen Sie Daten:** Verwenden Sie einfach die offizielle Google Drive/Sheets-Oberfläche, um Ihr Tabellendokument über deren Google-Konto mit Ihren Partnern, Familienmitgliedern oder Geschäftspartnern zu teilen.
2. **Verknüpfung der App:** Lassen Sie diese Personen SheetLedger auf ihren Geräten öffnen und mit genau demselben freigegebenen Google Sheet verknüpfen.
3. **Identitätsbasierte Sicherheit:** Um unbefugte Manipulationen zu verhindern, **sind alle Transaktionsprotokolle an die eindeutige Google-Konto-ID des Erstellers gebunden**. Obwohl mehrere Benutzer innerhalb desselben freigegebenen Hauptbuchs zusammenarbeiten und Daten einsehen können, überprüft unsere State Machine streng die Identitäten: Einträge, die von einer Google-ID erstellt wurden, können von einer anderen ID nicht geändert oder gefälscht werden. Dies garantiert absolute Manipulationssicherheit.

---
© 2026 gophini. Entwickelt für ultimative Finanzsouveränität.  
Benötigen Sie technische Unterstützung? Kontaktieren Sie uns unter: **gophini.support@gmail.com**
