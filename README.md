# data-engineering-portfolio
# Data Engineering Portfolio – Batch Data Pipeline

## Projektbeschreibung
Dieses Projekt wurde im Rahmen des Moduls Data Engineering (DLMDWWDE02) entwickelt. Ziel ist die Konzeption und Implementierung einer batchbasierten Datenarchitektur zur Verarbeitung großer Datenmengen im Kontext einer Machine-Learning-Anwendung zur Analyse von Flugverspätungen.

Die Architektur ermöglicht die periodische Verarbeitung historischer Flugdaten, deren Transformation sowie die Bereitstellung aggregierter Kennzahlen für nachgelagerte Anwendungen.

---

## Architekturüberblick

Die Datenpipeline basiert auf einer Microservice-Architektur und ist in mehrere Schichten unterteilt:

- Ingestion Layer  
  Import von Rohdaten in einem batchbasierten Prozess  
- Raw Layer  
  Speicherung unveränderter Daten zur Sicherstellung der Nachvollziehbarkeit  
- Processing Layer  
  Datenbereinigung sowie Feature Engineering  
- Serving Layer  
  Bereitstellung aggregierter Daten für analytische Anwendungen  

---

## Verwendete Technologien

- Python zur Datenverarbeitung  
- Pandas zur Transformation und Aggregation der Daten  
- Docker und Docker Compose zur Containerisierung und Sicherstellung der Reproduzierbarkeit  
- GitHub zur Versionskontrolle und Projektverwaltung  

---

## Projektstruktur

data-engineering-project/  
├── ingestion/ 
│  
└── ingest.py  
├── processing/  
│   └── process.py  
├── data/  
│   ├── raw/  
│   ├── processed/  
│   └── serving/  
├── Dockerfile.ingestion  
├── Dockerfile.processing  
├── docker-compose.yml  
├── requirements.txt  
└── flights.csv  

---

## Architekturdiagramm

<img width="684" height="456" alt="image" src="https://github.com/user-attachments/assets/67d71d25-463c-445a-ae5d-c789b4ee48d9" />

---

## Datenpipeline

1. Ingestion Service  
   Rohdaten werden aus einer CSV-Datei geladen und im Raw Layer gespeichert.  

2. Processing Service  
   Die Rohdaten werden eingelesen, bereinigt und um zusätzliche Merkmale erweitert. Anschließend erfolgt eine Aggregation der Daten nach definierten Kriterien.  

3. Serving Layer  
   Die aggregierten Daten werden gespeichert und stehen für weiterführende Analysen oder Machine-Learning-Anwendungen zur Verfügung.  

---

## Ausführung des Projekts

Voraussetzungen:  
Docker und Docker Compose  

Start der Datenpipeline:  

docker-compose up --build  

---

## Ergebnisdaten

Nach erfolgreicher Ausführung werden folgende Dateien erzeugt:

- data/raw/raw_flights.csv  
- data/processed/processed_flights.csv  
- data/serving/aggregated_flights.csv  

Die aggregierten Daten enthalten unter anderem durchschnittliche Verspätungswerte pro Flughafen.

---

## Nicht-funktionale Anforderungen

Reliability  
- Deterministische Batch-Verarbeitung  
- Reproduzierbare Systemumgebung durch Containerisierung  

Scalability  
- Modulare Struktur durch Microservices  
- Erweiterbarkeit einzelner Komponenten  

Maintainability  
- Klare Trennung der Systemschichten  
- Strukturierte und nachvollziehbare Codebasis  

Data Security und Governance  
- Schichtenmodell zur Trennung von Rohdaten und verarbeiteten Daten  
- Grundlage für zukünftige Zugriffskontrollen und Datenmanagement  

---

## Reflexion

Die implementierte Architektur zeigt, dass batchbasierte Datenpipelines eine geeignete Lösung für die Verarbeitung großer historischer Datenmengen darstellen. Die Aufteilung in Microservices unterstützt die Wartbarkeit sowie die Erweiterbarkeit des Systems und ermöglicht eine klare Strukturierung der einzelnen Verarbeitungsschritte.

---

## Weiterentwicklungsmöglichkeiten

- Integration von Apache Spark für skalierbare Datenverarbeitung  
- Erweiterung um Streaming-Komponenten zur Echtzeitverarbeitung  
- Deployment in Cloud-Umgebungen  
- Integration zusätzlicher Datenquellen  

---

## Autorin

Lydia Schirmer  
IU Internationale Hochschule  
Matrikelnummer: 10190634  
