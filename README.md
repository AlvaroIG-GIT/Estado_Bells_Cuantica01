# Práctica 1: Entorno de Simulación Cuántica y Estados de Bell con PyQuil

Implementación de circuitos cuánticos para la generación y simulación de los cuatro estados de Bell (estados entrelazados cuánticos máximos) utilizando **pyQuil**, el compilador cuántico **quilc** y el simulador **QVM** de Rigetti Forest SDK.

## Descripción

La práctica consiste en configurar el entorno de ejecución cuántica local y modelar los cuatro estados de Bell sobre un procesador virtual (`9q-square-qvm`):

- **`estado_bell_1.py`**: Estado $|\Phi^+\rangle = \frac{|00\rangle + |11\rangle}{\sqrt{2}}$ (Hadamard en $q_0$ + CNOT).
- **`estado_bell_2.py`**: Estado $|\Phi^-\rangle = \frac{|00\rangle - |11\rangle}{\sqrt{2}}$.
- **`estado_bell_3.py`**: Estado $|\Psi^+\rangle = \frac{|01\rangle + |10\rangle}{\sqrt{2}}$.
- **`estado_bell_4.py`**: Estado $|\Psi^-\rangle = \frac{|01\rangle - |10\rangle}{\sqrt{2}}$.

Cada circuito declara un registro de memoria clásica (`ro` de 2 bits), aplica la secuencia de puertas correspondientes ($H$, $CNOT$, $X$, $Z$) y realiza 100 lecturas (*shots*) para verificar la correlación cuántica de los resultados.

## Tecnologías

- **Lenguaje:** Python 3
- **Librería cuántica:** pyQuil
- **Compilador y Simulador:** `quilc` y `QVM` (Rigetti Forest SDK)

## Requisitos y Configuración Previa

El simulador requiere que los servidores locales del compilador y la máquina virtual cuántica estén en ejecución.

1. **Lanzar el compilador `quilc`** (en una terminal independiente):
   ```bash
   quilc -P -S