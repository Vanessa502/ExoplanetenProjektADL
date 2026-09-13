# Klassifikation von Exoplanetenkandidaten mittels Self-Supervised Learning

**Ein Vergleich von Training from Scratch und Masked-Reconstruction-Pretraining auf TESS-Lichtkurven**

> Master-Projekt zum Modul *Advanced Deep Learning* im Sommersemester 2026

## Projektstruktur

```text
├── data/
│   ├── raw/                          # Heruntergeladene Ausgangsdaten
│   ├── interim/                      # Zwischenergebnisse der Aufbereitung
│   └── processed/
│       └── spoc120_dataset/          # Modellfertige Views, Metadaten und Splits
├── Notebooks/
│   ├── 01_dataset_exploration.ipynb
│   ├── 02_lightcurve_exploartion.ipynb
│   ├── 03_dataset_generation.ipynb
│   ├── 04_supervised_baseline.ipynb
│   ├── 05_self_supervised_pretraining.ipynb
│   └── 06_final_evaluation.ipynb
├── results/
│   ├── supervised/                   # Supervised Baselines
│   ├── ssl/                          # Pretraining und Fine-Tuning
│   └── final_evaluation/             # Finale Testmetriken und Vergleiche
├── requirements.txt
└── README.md
```

## Erste Schritte

1. **Virtuelle Umgebung anlegen**

   ```bash
   python -m venv .venv
   ```

2. **Umgebung aktivieren**

   Windows PowerShell:

   ```powershell
   .\.venv\Scripts\Activate.ps1
   ```

   Windows Eingabeaufforderung:

   ```cmd
   .venv\Scripts\activate.bat
   ```

   macOS/Linux:

   ```bash
   source .venv/bin/activate
   ```

3. **Abhängigkeiten installieren**

   ```bash
   python -m pip install --upgrade pip
   pip install -r requirements.txt
   ```

4. **Jupyter starten** und den Kernel `.venv` auswählen

   ```bash
   jupyter lab
   ```

## Ausführung

Die Notebooks sind entsprechend ihrer Nummerierung auszuführen:

1. Exploration und Aufbereitung des TOI-Katalogs
2. Exploration und Vorverarbeitung der TESS-Lichtkurven
3. Generierung der Global Views und Local Views
4. Training der supervised Baseline
5. Self-Supervised Pretraining und Fine-Tuning
6. Finale Evaluation auf dem unangetasteten Test-Split

Die Notebooks 01 bis 03 benötigen eine Internetverbindung für den Zugriff auf
das NASA Exoplanet Archive beziehungsweise das MAST-Archiv. Mit dem bereits
erzeugten Datensatz unter `data/processed/spoc120_dataset/` kann direkt ab
Notebook 04 begonnen werden.

Die zusammengefassten Resultate befinden sich in
`results/final_evaluation/final_metrics_table.csv`.


## Hinweis zur Nutzung von KI

Bei der Entwicklung dieses Projektes wurde generative KI unterstützend
eingesetzt, insbesondere "GPT-5.6 Sol von OpenAI". Die Unterstützung umfasste
die Konzeption und Überarbeitung von Quellcode sowie die sprachliche und
strukturelle Ausarbeitung der Projektdokumentation bzw. des Papers.
Alle KI-generierten Vorschläge wurden geprüft und bei Bedarf angepasst. 
Methodik, Implementierung, Interpretation und dargestellte Ergebnisse wurden
eigenständig verantwortet.