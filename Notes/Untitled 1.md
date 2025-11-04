iiiii```
--- Inicializando Dominio ---
Dominio: [0, 6.28] x [0, 6.28]
Malla total: 64 x 64 = 4096 puntos
Malla interior (sin fronteras): 64 x 62 = 3968 incógnitas
Pasos: dx = 0.0982, dz = 0.0982
------------------------------
Campo de temperatura generado:
  - Rango: [300.00, 1201.43] K
  - Rango en °C: [26.85, 928.28]
  - Media: 442.35 K (169.20 °C)
  - Desv. estándar: 157.98 K
  - Verificación periodicidad (max |T[:,0] - T[:,-1]|): 0.000000e+00 K
  - T promedio en z=0: 614.33 K (341.18 °C)
  - T promedio en z=Zmax: 300.00 K (26.85 °C)
  - T promedio en columna central: 629.48 K (356.33 °C)
--- Calculando campo de densidad desde temperatura ---
Constantes termodinámicas:
  - Presión de referencia: 101325.00 Pa
  - Constante del gas (aire): 287.05 J/(kg·K)
  - Densidad de referencia (T=300K): 1.1766 kg/m³
Campo de densidad calculado:
  - Rango: [0.2938, 1.1766] kg/m³
  - Media: 0.8720 kg/m³
  - Desv. estándar: 0.2227 kg/m³
  - Razón ρ_max/ρ_min: 4.00
  - Verificación periodicidad (max |ρ[:,0] - ρ[:,-1]|): 0.000000e+00 kg/m³
  - ρ promedio en z=0: 0.7378 kg/m³
  - ρ promedio en z=Zmax: 1.1766 kg/m³
  - ρ promedio en columna central: 0.6361 kg/m³
  - Verificación (ρ centro vs esperado): 0.6361 vs 0.5608
Análisis de flotabilidad:
  - ∂ρ/∂z promedio: 0.073070 kg/m⁴
  - ∂ρ/∂z en columna central: 0.148460 kg/m⁴
  - ⚠️ Columna central: estable (poco realista para un incendio)
Consistencia termodinámica:
  - Correlación entre T y 1/ρ: 1.000000
  - ✓ Relación T vs ρ es correcta (correlación casi perfecta)
------------------------------------------------------------
--- Calculando campo de presión desde densidad ---
Método seleccionado: hydrostatic
Parámetros de integración hidrostática:
  - Gravedad: 9.81 m/s²
  - Paso vertical: 0.0982 m
  - Integración completada desde z=Zmax hacia z=0
  - ✓ Forzado p=0 en z=0 (restando offset)
Campo de presión (hidrostático):
  - Rango: [-64.40, 0.00] Pa
  - Media: -24.09 Pa
  - Desv. estándar: 16.30 Pa
  - Frontera z=0: max|p| = 0.000000e+00 Pa
  - Frontera z=Zmax: max|p| = 6.439742e+01 Pa
  - Verificación periodicidad (max |p[:,0] - p[:,-1]|): 0.000000e+00 Pa
Verificación del gradiente vertical:
  - ∂p/∂z medio calculado: -8.55 Pa/m
  - ∂p/∂z medio esperado (-ρg): -8.55 Pa/m
  - Error relativo: 0.01%
Estructura vertical de presión:
  - p medio en z=0: 0.00 Pa
  - p medio en z=Zmax: -52.83 Pa
  - p medio en columna central: -15.69 Pa
============================================================
VERIFICACIÓN DE CONSISTENCIA DEL SISTEMA T-ρ-p
============================================================
1. Ecuación hidrostática (∂p/∂z = -ρg):
   - Error absoluto máximo: 4.47e-01 Pa/m
   - Error absoluto medio: 7.02e-03 Pa/m
   - Error relativo medio: 0.06%
   - ✓ EXCELENTE: Equilibrio hidrostático bien satisfecho

2. Condiciones de borde:
   - En z=0: max|p| = 0.00e+00 Pa
   - En z=Zmax: max|p| = 6.44e+01 Pa
   - ⚠️ Condiciones de borde no exactamente cero

3. Periodicidad en x:
   - Presión: max|p[:,0] - p[:,-1]| = 0.00e+00 Pa
   - Densidad: max|ρ[:,0] - ρ[:,-1]| = 0.00e+00 kg/m³
   - ✓ Periodicidad satisfecha

4. Consistencia de flotabilidad:
   - Correlación ∂p/∂x vs ∂ρ/∂x: -0.6230
   - ⚠️ Correlación débil (puede ser esperado en flujos complejos)

5. Análisis de estabilidad (Número de Richardson):
   - Frecuencia Brunt-Väisälä (N²) en columna central:
     · Rango: [-1.04e+01, 3.20e+00] s⁻²
     · Fracción inestable (N²<0): 100.0%
   - ✓ Columna central inestable (esperado para incendio)

============================================================
RESUMEN DE VERIFICACIÓN:
⚠️  ALGUNOS CHEQUEOS FALLARON
   Revisar advertencias arriba
============================================================
```