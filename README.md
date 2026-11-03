# NEXERGY SME – Energy-to-Production Intelligence Prototype

**Find the Waste. Predict the Failure. Optimise the Factory.**

NEXERGY SME is a retrofit-first industrial intelligence platform for Indian manufacturing SMEs. It connects energy, equipment health, production, cost and carbon into one actionable layer.

**Important: all data in this prototype is simulated. No real plant data is used.**

### What this prototype does
- Simulates 7 days of hourly compressor data: power, vibration, runtime and production.
- Injects a degradation fault at hour 72 (about +12% energy, +18% vibration).
- Computes production-normalised Specific Energy Consumption (SEC, kWh per unit) against a baseline built from the first 72 hours.
- Detects anomalies with a rolling z-score on SEC (alert threshold 3.0).
- Estimates monthly energy-cost loss, CO2 impact and an equipment health score.
- Produces a recommendation: inspect compressor leakage and loading efficiency.
- Verifies the result: Verified saving = Baseline SEC minus Post-action SEC.

### How to run
Open `nexergy_prototype.html` in any modern browser. No installation needed. Use the tariff and grid-factor inputs, then click "Apply recommended action" to simulate the repair.

### Assumptions
- Tariff: Rs 8 per kWh (adjustable).
- Grid emission factor: 0.710 tCO2/MWh (CEA CO2 Baseline Database v21.0, FY 2024-25).
- All savings shown are simulated and must be validated through site-specific baseline measurement.

### Architecture (designed for pilot)
Factory sensors, then edge gateway (Modbus, OPC-UA, MQTT), then cloud analytics, then action engine, then measurement and verification. Only the analytics and dashboard layer is built in this prototype.

### Roadmap
0–30 days baseline and connect; 30–90 days detect and diagnose; 3–6 months optimise and verify; 6–24 months scale.

### Team
Tesla N – Shantanu Tripathy

### Technologies
Built: HTML, CSS, JavaScript, SVG charts, seeded time-series simulator, statistical anomaly detection. Planned: ESP32 or Raspberry Pi edge gateway, Python (pandas, scikit-learn), time-series database, cloud hosting.
