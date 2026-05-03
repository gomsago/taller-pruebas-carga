# Taller de Pruebas de Carga y Rendimiento

##  Objetivo
Evaluar el comportamiento del sistema bajo diferentes niveles de carga utilizando k6.

---

##  Herramienta utilizada
- k6 (pruebas de carga sobre API HTTP)

---

##  Escenarios ejecutados

| Escenario | Descripción |
|----------|------------|
| Baseline | Carga base con usuarios moderados |
| Carga    | Incremento progresivo de usuarios |
| Estrés   | Sobrecarga del sistema |

---

##  Ejecución

```bash
set SCENARIO=baseline
k6 run perf/scripts/register_person_k6.js -o json=perf/results/baseline.json

set SCENARIO=load
k6 run perf/scripts/register_person_k6.js -o json=perf/results/load.json

set SCENARIO=stress
k6 run perf/scripts/register_person_k6.js -o json=perf/results/stress.json
