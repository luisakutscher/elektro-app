# SPEC.md – Elektrobetrieb Brandt & Söhne

## Business Rules

- **BR1:** Bei Auftrag über 1.500 Euro wird ein schriftliches Angebot verfasst, was der Kunde unterschreiben muss. (Antwort 1 & 7)
- **BR2:** Jeder Auftrag bekommt seine eigene Rechnung, es gibt keine Sammelrechnungen. (Antwort 8)
- **BR3:** Der Preis für den Kunden wird errechnet durch geleisteten Stundenlohn der Mitarbeiter und 30% Zuschlag auf die Materialkosten (plus Anfahrtspauschale im Falle eines Notdiensteinsatzes). (Antwort 6)
- **BR4:** Die Mitarbeiter werden nach ihrer Qualifikation (Meister, Geselle, Lehrling) auf die Aufträge verteilt. (Antwort 5)
- **BR5:**

## Entitäten

- **Mitarbeiter**, Attribute: Name, Qualifikation (Meister, Geselle, Lehrling)
- **Kunde**, Attribute: Name, Auftrag
- **Einsatzort**, Attribute: Adresse, Auftrag
- **Auftrag**, Attribute: Auftrag_ID, Kunde, Datum, Status
- **Leistung**, Attribute: Art (Installation, Reparatur, Notdienst), Dauer, Preis
- **Material**, Attribute: Art (Kabel), Bestand
- **Rechnung**, Attribute: Rechnung_ID, Auftrag, Betrag, Status

## Beziehungen

- Auftrag – Mitarbeiter → n:m
- Auftrag – Material → n:m
- Kunde – Auftrag → 1:n
- Auftrag – Rechnung → 1:1
- Einsatzort – Auftrag → 1:n
- Fahrzeug – Mitarbeiter → n:m
- Mitarbeiter – Leistung → n:m

## Widersprüche

- **W1:** „mit dem Bus“ (Antwort 10) vs. vier Busse (Antwort 11) → Fuhrpark
- **W2**

## Prioritäten

1. Mitarbeiter Überblick → Zeiten und Orte
2. Material & Bestand
3. Fahrzeugnutzung

## Offene Fragen

- feste Terminzeiten außerhalb des notdienstes?
- W: Vier Busse für vier Meister? Oder vier Busse für drei Meister und ein Bus ist backup?
- W: Sie meinten ihre frau arbeitet im büro nebenan, ist das büro eine andere adresse, als werkstatt und lager? Oder ist alles unter einer adresse?
- kann es an einem einsatzort auch mehrere aufträge geben?
- kann ein auftrag mehrere leistungen beinhalten? → beziehung zwischen auftrag und leistung
- wonach werden materialien sortiert?
