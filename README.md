# LorHels Presta

es una aplicación web financiera integral, diseñada para administrar carteras de préstamos, automatizar cobranzas y brindar transparencia a los clientes. Funciona completamente en la nube (con Firebase) y se actualiza en tiempo real.

Aquí tienes el desglose de los módulos y características que ya están 100% operativos:

---

### 1. Sistema de Seguridad y Roles (Niveles de Acceso)
* **Administrador (Dueño):** Tiene control total. Puede ver todas las estadísticas, editar/eliminar registros en caso de error, aprobar pagos y cobrar directamente saltándose las validaciones.
* **Cobrador (Trabajador de campo):** Su vista está restringida. Solo ve los clientes de su ruta asignada y los préstamos activos que debe cobrar. No ve las ganancias totales de la empresa ni puede modificar datos sensibles.
* **Cliente (Portal de Autoservicio):** Puede iniciar sesión con su propio correo y contraseña temporal para ver su estado de cuenta, su balance pendiente y el historial de las cuotas que ya ha pagado.

---

### 2. Motor Financiero y Operativo
* **Calculadora Mágica:** Al registrar un préstamo, el sistema calcula automáticamente los intereses, divide el capital en cuotas exactas y genera un calendario de fechas de pago según la frecuencia (diario, semanal, quincenal, mensual).
* **Regla Anti-Sobreendeudamiento:** El sistema bloquea automáticamente la creación de un préstamo nuevo si detecta que el cliente ya tiene uno activo o pendiente.
* **Mora Automática Programable:** Permite configurar un porcentaje de recargo y días de gracia. El sistema rastrea las fechas de pago a diario y, si un cliente se atrasa, le suma la mora automáticamente a su cuota.
* **Amortización Inteligente:** Si un cliente paga de más, el sistema tacha la cuota actual y el dinero "sobrante" viaja automáticamente a descontar o eliminar la última cuota del préstamo.

---

### 3. Gestión de Cobros y Comunicación
* **Caja Fuerte Virtual:** Los cobradores registran los pagos en la calle, pero el dinero no se descuenta del balance del cliente hasta que el Administrador presiona "Aprobar" (asegurando que el dinero realmente llegó a la base).
* **Tickets Térmicos:** Generación de recibos digitales listos para impresoras térmicas portátiles o para guardar en PDF. Incluso los clientes pueden imprimir sus propios comprobantes de "PAGADO" desde su portal.
* **Integración con WhatsApp:** Con un solo clic, el sistema genera un mensaje formal y abre WhatsApp para enviarle al cliente su recibo digital, detallando el monto pagado, si hubo mora y su balance actualizado.

---

### 4. Dashboards y Analítica
* **Métricas en Tiempo Real:** El administrador tiene tres tarjetas principales que suman automáticamente el *Capital Total Prestado*, el *Total Cobrado (Ganancias)* y la cantidad de *Clientes Activos*.
* **Buscador Instantáneo:** Una barra de búsqueda que permite filtrar la lista de clientes por nombre o número de cédula sin recargar la página.

---