### Issues to create for skills-integrate-mcp-with-copilot

1) Title: Añadir persistencia con SQLAlchemy y migraciones

Description:
Añadir soporte de base de datos (SQLite por defecto, opción Postgres), implementar modelos `Activity` y `Participant` con SQLAlchemy, integrar Alembic para migraciones, migrar datos de ejemplo desde el diccionario en memoria. Incluir tests básicos y actualizar endpoints para usar persistencia.

Labels: enhancement, backend

---

2) Title: Implementar autenticación y roles (estudiante/admin)

Description:
Añadir registro/login (JWT o `fastapi-users`), proteger endpoints administrativos, permitir roles `student` y `admin`, proveer endpoint para gestionar cuentas y reset de contraseña. Documentar flujo de uso.

Labels: enhancement, auth

---

3) Title: Panel administrativo para crear/editar actividades

Description:
Añadir UI mínima (`/admin`) para crear/editar/eliminar actividades (título, descripción, horario, `max_participants`), ver lista de participantes y exportar CSV. Proteger con rol `admin`.

Labels: enhancement, frontend

---

4) Title: Validación de cupo y gestión de lista de espera

Description:
En el backend, validar `max_participants` al inscribir; si está lleno, añadir a `waitlist`. Añadir endpoints para ver/promover lista de espera y notificar por email cuando haya vacante. Tests incluidos.

Labels: enhancement, backend

---

5) Title: Generar QR por inscripción y endpoint de check-in

Description:
Generar un código QR único al confirmar inscripción; añadir endpoint para escanear/check-in que marque asistencia. Usar librería `qrcode` y servir imágenes/URLs seguras.

Labels: feature, backend

---

6) Title: Notificaciones por email y exportación a calendario

Description:
Enviar emails de confirmación y recordatorios (configurable, dev: SMTP console), y permitir exportar evento a ICS y enlace de Google Calendar. Añadir configuración env vars y documentación.

Labels: enhancement, infra

---

7) Title: Integrar pagos para eventos de pago (opcional)

Description:
Añadir flujo opcional de pago para actividades (Stripe preferido), crear endpoint para iniciar pago, manejar webhooks y marcar inscripciones como `paid`. Documentar requisitos y modo sandbox.

Labels: feature, payments, optional
