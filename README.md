<div align="center">

# ✈️ Flight Management System

**Flight/airport/passenger data-analysis system built in C** — project for *Laboratórios de Informática III* @ University of Minho (2025/2026) [Grade: 19/20]

![C](https://img.shields.io/badge/-C-A8B9CC?style=for-the-badge&logo=c&logoColor=black)
![Makefile](https://img.shields.io/badge/-Makefile-427819?style=for-the-badge&logo=gnu&logoColor=white)
![Doxygen](https://img.shields.io/badge/-Doxygen-2C4AA8?style=for-the-badge&logo=doxygen&logoColor=white)
![Valgrind](https://img.shields.io/badge/-Valgrind-orange?style=for-the-badge)

</div>

---

## 📖 About

**Flight Management System** is a C application developed for *Laboratórios de Informática III* at the University of Minho. The project loads and analyzes a dataset of **flights**, **airports**, **aircraft**, **passengers**, and **reservations** (CSV files), storing them in memory using custom data structures, and answers a set of predefined **queries** over that data.

The project emphasizes **modularity** and **encapsulation**, separating interface (`.h`) from implementation (`.c`), with careful memory management (validated via `valgrind`) and Doxygen-style documentation.

---

## 🧩 Data Model

| Entity | Source | Key fields |
|---|---|---|
| Flights | `flights.csv` | id, departure/arrival times, status, origin/destination, aircraft, airline |
| Airports | `airports.csv` | IATA/ICAO code, name, city, country, coordinates, type |
| Aircraft | `aircrafts.csv` | tail number, manufacturer, model, year, capacity, range |
| Passengers | `passengers.csv` | document number, name, dob, nationality, contact info |
| Reservations | `reservations.csv` | reservation id, flight(s), passenger, seat, price, extras |

---

## 🔎 Queries

| # | Query |
|---|---|
| Q1 | Airport summary (arrivals/departures count) by airport code |
| Q2 | Top N aircraft with most flights (optional manufacturer filter) |
| Q3 | Airport with most departures between two dates |
| Q4 | Passenger with most weeks in the top-10 spenders over a period |
| Q5 | Top N airlines by average delay per flight |
| Q6 | Most common destination airport for passengers of a given nationality |

Each query supports two output formats — `;`-separated (default) or `=`-separated (`<N>S` variant).

---

## 🚀 Executables

The `Makefile` builds three executables:

| Executable | Purpose |
|---|---|
| `programa-principal` | Batch mode — runs a list of queries from a command file against a dataset, writing results to `resultados/` |
| `programa-interativo` | Interactive terminal menu for running queries manually |
| `programa-testes` | Validates query output against expected results, and reports timing + memory usage |

### Build

```bash
make
```

### Run — main mode

```bash
./programa-principal <dataset_dir>/ <commands_file>
```

### Run — interactive mode

```bash
./programa-interativo
```

### Run — test mode

```bash
./programa-testes <dataset_dir>/ <commands_file> <expected_results_dir>/
```

---

## ✅ Data Validation

CSV entries are validated both **syntactically** (dates, emails, coordinates, IDs, enums, etc.) and **logically** (e.g., flight `origin` ≠ `destination`, referenced aircraft/passenger must exist). Invalid rows are excluded from query results and logged to `resultados/<entity>_errors.csv`.

---

## 🗂️ Project Structure

```
Flight-Management-System/
├── include/                 # Header files (.h) — Doxygen-documented interfaces
├── src/                     # Implementation files (.c)
├── resultados/              # Query outputs + validation error logs
├── resultados-esperados/    # Expected outputs for programa-testes
├── Makefile                 # Builds programa-principal, -interativo, -testes
├── Doxyfile                 # Doxygen configuration
├── relatorio-fase1.pdf      # Phase 1 report
└── relatorio-fase2.pdf      # Phase 2 report
```

---

## 🛠️ Tech Stack

- **Language:** C
- **Build tool:** Make
- **Documentation:** Doxygen
- **Memory analysis:** Valgrind
- **Debugging:** GDB

---

<div align="center">

🔗 [github.com/miguelprcorreia/Flight-Management-System](https://github.com/miguelprcorreia/Flight-Management-System)

</div>
