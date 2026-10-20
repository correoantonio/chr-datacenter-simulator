# CHR + Data Centers | Simulador energético

Aplicación estática divulgativa en español con parámetros hipotéticos, sin instalaciones reales identificables.

**Simulador público:** https://correoantonio.github.io/chr-datacenter-simulator/

## Funcionamiento
Abrir index.html o la URL pública. Modificar potencia IT, PUE, potencia máxima de turbinación y energía útil CHR. Los resultados se actualizan inmediatamente. Incluye escenarios pequeño, mediano e hiperescala, reinicio y exportación CSV UTF-8 con separador punto y coma. No requiere cuentas, backend, bases de datos ni dependencias externas.

## Metodología
- Demanda D = potencia IT × PUE (MW).
- Aporte S = mínimo entre potencia máxima CHR y D (MW).
- Cobertura instantánea = 100 × S / D (%).
- Autonomía de descarga = energía útil / S (h). Si la cobertura es parcial, mide la duración del aporte CHR, no la autonomía de todo el centro.
- Duración a máxima potencia = energía útil / potencia máxima CHR (h).
- Demanda en t horas = D × t (MWh).
- Aporte acumulado CHR = mínimo entre energía útil y S × t (MWh).

Periodos: 1, 4, 8, 12, 24 y 48 horas. Reiniciar recupera 100 MW IT, PUE 1,20, 200 MW CHR y 1.200 MWh útiles. Ejemplo hiperescala: 800 MW IT y PUE 1,20 demandan 960 MW; 400 MW CHR cubren el 41,67 % durante 10 horas con 4.000 MWh útiles.

El almacenamiento parte lleno y opera con potencia constante, sin recarga. La energía de entrada ya es útil a la salida: no se descuentan otra vez pérdidas de ciclo. No se modelan hidráulica, UPS, contingencias, mantenimiento, restricciones de red, precios ni trazabilidad renovable. La barra representa potencia instantánea, no energía garantizada.

Este simulador tiene carácter divulgativo y utiliza hipótesis simplificadas. Los resultados no acreditan la viabilidad técnica o económica de una instalación, la disponibilidad real de energía, la capacidad de acceso y conexión, la reducción efectiva de restricciones eléctricas ni la garantía de suministro de un centro de datos.

## Investigación científica y referencias
Metadatos contrastados con Crossref el 20 de octubre de 2026. El simulador no reproduce los modelos de estos estudios.

1. Li et al. (2026). Equilibrium-based electricity-computation collaborative scheduling for data centers integrated with seawater pumped storage hydropower. Energy, 345, 140267. https://doi.org/10.1016/j.energy.2026.140267 — bombeo reversible marino.
2. Wang et al. (2025). Electricity-computility integration of data centers and pumped storage driven by cold energy storage in China. Energy Reports, 14. https://doi.org/10.1016/j.egyr.2025.11.048 — bombeo reversible y almacenamiento de frío.
3. Su et al. (2025). Optimal scheduling of a cascade hydro-thermal-wind power system integrating data centers and considering the spatiotemporal asynchronous transfer of energy resources. Applied Energy, 377, 124360. https://doi.org/10.1016/j.apenergy.2024.124360 — coordinación hidroeléctrica general, no estudio específico de CHR.

## Publicación y licencia
GitHub Pages desde main, carpeta raíz. Código bajo licencia MIT, con autorización del titular del HTML original. Los artículos enlazados conservan sus propios derechos.
