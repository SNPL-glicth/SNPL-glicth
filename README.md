# 👋 Nicolás

**ML Engineer · Sistemas industriales · Arquitectura de software**

Construyo sistemas de ML para producción industrial que funcionan en
el mundo real — no solo en notebooks. Me obsesiono con que el código
sea limpio, SOLID y que cada decisión de diseño tenga una razón física
detrás.

Trabajo en el stack completo: desde arquitectura de pipelines cognitivos
hasta el detalle de por qué un `k=3.0` en un Hampel filter destruye las
predicciones de una llenadora pero no de un pasteurizador.

---

## 🔧 En qué trabajo

- **Pipelines de predicción IoT** para líneas industriales (embotelladoras, sensores DLC)
- **Mixture of Experts (MoE)** con gating contextual por tipo de equipo —
  porque una nevera y un horno no son lo mismo y el modelo tampoco debería tratarlos igual
- **Arquitecturas cognitivas** con múltiples engines especializados
  (Kalman, Taylor, Statistical, Baseline) y fusión bayesiana adaptativa
- **Mantenimiento predictivo** con detección de drift por sensor individual,
  eventos industriales (CIP, arranques, cambios de producto) y perfilado por equipo

---

## 🧠 Cómo pienso el código

- El dominio físico primero — si no entiendo qué hace el equipo,
  no puedo modelarlo bien
- SOLID no como dogma sino como herramienta para que el sistema
  sobreviva cambios reales
- Backward compatibility siempre — nada de romper contratos existentes
- Tests como criterio de verdad — si no hay 40/40 verde, no está listo

---

## 🛠️ Stack

Python · ML pipelines · IoT industrial · Arquitectura hexagonal
Mixture of Experts · Bayesian inference · SOLID · Redis · SQLAlchemy
XGBoost · Kalman filters · Series temporales


---

## 📌 Proyectos destacados

### 🏭 Sistema ML IoT — Embotelladoras industriales
Pipeline cognitivo de predicción con MoE equipment-aware para sensores
industriales (pasteurizadores, llenadoras, CIP, transportadores, silos).

**Lo interesante:**
- Gating contextual por `(equipment_class, regime)` — Taylor domina
  pasteurizadores, Statistical domina llenadoras, nunca al revés
- Detección de eventos industriales (STARTUP, CIP_CYCLE, PRODUCT_CHANGEOVER)
  para suprimir falsas alarmas durante transitorios normales
- Aprendizaje bayesiano per-sensor con fallback a pesos globales
  — el pasteurizador_01 y el pasteurizador_02 aprenden de forma independiente
- Hampel filter adaptativo por equipo — `k=2.5` para pasteurizador,
  `k=4.0` para llenadora, `k=5.0` durante ciclos CIP activos
