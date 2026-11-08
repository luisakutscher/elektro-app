# SPEC.md – Elektrobetrieb Brandt & Söhne

Quelle: Meeting 1 und 2 mit Thomas Brandt (jeweils 12 und 8 Nachrichten)

## Business Rules

- **BR1:** Bei Auftrag über 1.500 Euro wird ein schriftlicher Vertrag verfasst, den der Kunde unterschreiben muss. (Antwort 1 & 7)
- **BR2:** Jeder Auftrag bekommt seine eigene Rechnung, es gibt keine Sammelrechnungen. (Antwort 8)
- **BR3:** Der Preis für den Kunden wird errechnet durch geleisteten Stundenlohn der Mitarbeiter und 30% Zuschlag auf die Materialkosten (Notdiensteinsatz: plus Anfahrtspauschale 80 EUR und Stundenlohn 1,5x höher). (Antwort 6 & 16)
- **BR4:** Die Mitarbeiter werden nach ihrer Qualifikation (Meister, Geselle, Lehrling) auf die Aufträge verteilt. Ein Lehrling darf nicht alleine zu einem Auftrag. (Antwort 5)
- **BR5:** Das Zahlungsziel nach Rechnungsausgabe beträgt 14 Tage. Nach drei Wochen werden bis zu zwei Erinnerungen verschickt → bleibt die Zahlung dennoch aus, wird ein Anwalt eingeschaltet. (Antwort 15)

## Entitäten

- **Mitarbeiter**, Attribute: Name, Qualifikation (Meister, Geselle, Lehrling), Stunden
- **Kunde**, Attribute: Name, Auftrag
- **Einsatzort**, Attribute: Adresse, Auftrag
- **Auftrag**, Attribute: Auftrag_ID, Kunde, Datum, Status (ausstehend, beendet) 
- **Leistung**, Attribute: Art (Installation, Reparatur, Notdienst), Dauer, Preis
- **Material**, Attribute: Art (NYM-Kabel, Sicherungen, Dosen, Lüsterklemmen), Bestand
- **Rechnung**, Attribute: Rechnung_ID, Auftrag, Betrag, Status (ausgestellt_am, fällig_am, bezahlt_am)
- **Wartungsvertrag**, Attribute: Kunde, Vertragsstatus (ausgestellt_am, gekündigt_am), Leistungsstatus (Stromcheck, Notlichtprüfung), Bezahlungsstatus (fällig_am, bezahlt_am)

## Beziehungen

- Auftrag – Mitarbeiter → n:m
- Auftrag – Material → n:m
- Kunde – Auftrag → 1:n
- Auftrag – Rechnung → 1:1
- Einsatzort – Auftrag → 1:n
- Fahrzeug – Mitarbeiter → n:m
- Mitarbeiter – Leistung → n:m
- Auftrag – Leistung → n:m
- Mitarbeiter - Werkzeug → n:m

## Widersprüche

- **W1:** „mit dem Bus“ (Antwort 10) vs. vier Busse (Antwort 11) → Fuhrpark/Fahrzeuge
- **W2:** „kein Vertrag, […] ein schriftliches Angebot“ (Antwort 7) vs. Vertrag (Antwort 17) → BR1

## Prioritäten

1. Mitarbeiter → Zeiten und Orte (v1)
2. Material (Bestand), Werkzeuge & Rechnungen (v1)
3. Tracking Wartungsverträge → Kunden, Einnahmen, Termine (v2)

## Anmerkungen
- 12 Mitarbeiter bestehend aus vier Meistern, fünf Gesellen, zwei Lehrlingen und Fr. Brandt
- Arbeitszeiten unter der Woche sind von 7 bis 16 Uhr
- wichtige Werkzeuge: Bohrhämmer, Multimeter, Steigleitern
- es gibt ein Telefon für den normalen Dienst und eins für Notdienstanrufe
- Wartungsvertrag: alle zwei Jahre Stromcheck & jährlich Notlichtprüfung
- Werkstatt, Lager & Büro alles an einem Standort
