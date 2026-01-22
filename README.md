# Calendario de Vacaciones (2025–2030)

Aplicación web estática para gestionar y estimar vacaciones disponibles mediante un calendario interactivo con soporte para:
- Annual Leave generado por **ratio de horas trabajadas**
- **Carryover**
- **Bank Holidays (Irlanda)** editables
- **Time Off In Lieu (TIL)** por trabajar un Bank Holiday
- **Día extra por cumpleaños**
- Exportación a **Google Calendar (.ics)**

## Producción (GitHub Pages)

➡️ **https://velascou.github.io/calendario_vacaciones/**

> Nota: Asegúrate de tener GitHub Pages habilitado en:
> Repo → **Settings** → **Pages** → Deploy from branch → `main` → `/root`

---

## Funcionalidades principales

### Calendario interactivo
- Marcar días como **vacaciones** (Annual Leave)
- Marcar días como **Bank Holiday** (pre-cargados para Irlanda)
- Marcar **trabajé este Bank Holiday** para generar **TIL**
- Marcar días como **deshabilitados** (no trabajados, no consumen vacaciones)

### Cálculo del saldo (modelo por horas)
La app calcula las vacaciones disponibles acumuladas hasta una fecha (**cutoff**) con esta lógica:


**Vacaciones disponibles (días)**:

- Las **horas diarias** se calculan automáticamente como:

### TIL por trabajar Bank Holiday
Regla incluida:
- Bank Holiday trabajado en día laborable → **+3 días**
- Bank Holiday trabajado en fin de semana → **+1.5 días**

> Puedes editar los Bank Holidays directamente en el calendario.

### Exportación a Google Calendar
Exporta:
- Vacaciones tomadas (Annual Leave) en formato `.ics`
- Bank Holidays como calendario `.ics`

En Google Calendar:
1. Settings
2. Import & export
3. Import
4. Selecciona el `.ics`

---

## Cómo usar la aplicación

1. Abre la web en producción o ejecuta localmente con doble click en `index.html`
2. Elige el **año (2025–2030)**
3. Define:
   - Fecha de cálculo (**cutoff**)
   - Inicio de contrato
   - Horas semanales (ej: 38)
   - Días/semana (ej: 5)
   - Ratio de acumulación (ej: 0.08)
   - Carryover si aplica
   - Cumpleaños (opcional)
4. Usa el **Modo de edición**:
   - Marcar vacaciones
   - Editar Bank Holiday
   - Trabajé el Bank Holiday (TIL)
   - Deshabilitar día

Los cambios se guardan automáticamente en tu navegador (**localStorage**).

---

## Desarrollo / Contribución

### Clonar
```bash
git clone https://github.com/Velascou/calendario_vacaciones.git
cd calendario_vacaciones
