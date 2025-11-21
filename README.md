# 📅 Sistema de Reservas - Agenda de Citas Inteligente

![HTML5](https://img.shields.io/badge/-HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/-CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/-JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)

## 📖 Descripción

Sistema completo de reservas de citas con calendario interactivo, selección de horarios y confirmación por WhatsApp. Ideal para barberías, salones de belleza, spas, consultorios, talleres mecánicos y cualquier negocio que requiera agendar citas.

## ✨ Características Principales

- 📅 **Calendario Visual Interactivo** - Navega por meses y selecciona fechas fácilmente
- 🕐 **Gestión de Horarios** - Muestra horarios disponibles y ocupados
- 💈 **Múltiples Servicios** - Diferentes servicios con duración y precio
- ✅ **Validación Automática** - No permite reservar fechas pasadas ni domingos
- 📱 **Envío por WhatsApp** - Confirmación instantánea con todos los detalles
- 📊 **Resumen Completo** - Visualiza todo antes de confirmar
- 🎨 **Diseño Moderno** - Interfaz intuitiva y atractiva
- 📱 **100% Responsive** - Funciona perfecto en todos los dispositivos

## 🎯 Ideal Para

- ✅ Barberías y peluquerías
- ✅ Salones de belleza y spa
- ✅ Consultorios médicos y dentales
- ✅ Talleres mecánicos
- ✅ Servicios profesionales
- ✅ Cualquier negocio con sistema de citas

## 🚀 Demo en Vivo

🌐 **[Probar Sistema de Reservas](https://apgtest.github.io/sistema-reservas/)**



## 💻 Instalación

### Clonar el Repositorio

```bash
git clone https://github.com/apgtest/sistema-reservas.git
cd sistema-reservas
```

### Usar el Proyecto

Abre `index.html` en tu navegador o usa Live Server en VS Code.

## 🛠️ Personalización

### 1. Cambiar Número de WhatsApp

Busca y reemplaza `593999999999`:

```javascript
const urlWhatsApp = `https://wa.me/TU_NUMERO?text=${encodeURIComponent(mensaje)}`;
```

### 2. Personalizar Servicios

Modifica el array `servicios`:

```javascript
const servicios = [
    { 
        id: 1, 
        nombre: 'Tu Servicio', 
        duracion: '30 min', 
        precio: 15.00, 
        icon: '✂️' 
    },
    // Agrega más servicios aquí
];
```

**Campos:**
- `id`: Número único del servicio
- `nombre`: Nombre descriptivo
- `duracion`: Tiempo que toma (ej: "30 min", "1 hora")
- `precio`: Precio del servicio
- `icon`: Emoji representativo

### 3. Configurar Horarios Disponibles

Ajusta el array `horariosDisponibles`:

```javascript
const horariosDisponibles = [
    '09:00', '09:30', '10:00', '10:30', // Mañana
    '14:00', '14:30', '15:00', '15:30'  // Tarde
];
```

### 4. Cambiar Días No Laborables

Por defecto, los domingos están deshabilitados. Para cambiar:

```javascript
// En la función generarCalendario()
const esDomingo = fecha.getDay() === 0; // 0 = Domingo
// Cambia a otro día si necesitas:
// 1 = Lunes, 2 = Martes, etc.
```

### 5. Personalizar Colores

Modifica las variables CSS:

```css
:root {
    --primary: #667eea;     /* Color principal */
    --secondary: #764ba2;   /* Color secundario */
    --success: #25D366;     /* WhatsApp */
    --warning: #f59e0b;     /* Día actual */
}
```

### 6. Cambiar Nombre del Negocio

Edita el header:

```html
<h1>📅 Tu Negocio</h1>
<p>Agenda tu cita fácilmente</p>
```

## 📋 Flujo del Usuario

### 1. Seleccionar Servicio
- Usuario ve tarjetas con servicios disponibles
- Cada tarjeta muestra: nombre, duración y precio
- Click para seleccionar un servicio

### 2. Elegir Fecha
- Calendario visual muestra mes actual
- Puede navegar con flechas ← →
- Días pasados aparecen deshabilitados
- Domingos (u otros días no laborables) marcados como no disponibles
- Día actual resaltado en color especial
- Click en fecha disponible para seleccionar

### 3. Seleccionar Horario
- Se muestran todos los horarios disponibles
- Horarios ocupados aparecen tachados
- Click en horario disponible para seleccionar

### 4. Ingresar Datos
- Formulario con nombre y teléfono (requeridos)
- Campo de comentarios opcional
- Resumen completo de la reserva
- Botón para confirmar y enviar por WhatsApp

## 🎨 Estructura del Mensaje WhatsApp

```
📅 NUEVA RESERVA

👤 Cliente: María López
📱 Teléfono: 0991234567

💈 Servicio: Corte + Barba
📅 Fecha: Lunes, 25 de noviembre de 2025
🕐 Hora: 15:00
⏱️ Duración: 45 min
💰 Precio: $12.00

💬 Comentarios: Prefiero corte bajo
```

## 💡 Funcionalidades Avanzadas

### Simulación de Horarios Ocupados

El sistema simula aleatoriamente algunos horarios ocupados:

```javascript
// En la función mostrarHorarios()
const ocupados = horariosDisponibles.filter(() => Math.random() > 0.7);
```

**Para integrar con sistema real:**
1. Conecta a una base de datos
2. Consulta reservas existentes para la fecha
3. Marca esos horarios como ocupados

### Validación de Fechas

El sistema automáticamente:
- ✅ Deshabilita fechas pasadas
- ✅ Marca domingos como no disponibles
- ✅ Resalta el día actual
- ✅ Previene selección de fechas inválidas

### Navegación del Calendario

- **Mes anterior:** Click en ←
- **Mes siguiente:** Click en →
- **Año automático:** Se actualiza al cambiar de diciembre a enero

## 📱 Responsive Design

El sistema se adapta perfectamente a:

- 📱 **Móviles** (< 768px)
  - Servicios en 1 columna
  - Horarios en 3 columnas
  - Botones verticales

- 📲 **Tablets** (768px - 1024px)
  - Layout optimizado para pantalla mediana

- 💻 **Desktop** (> 1024px)
  - Vista completa con espaciado amplio

## 🎓 Conceptos Implementados

- ✅ **Manipulación de Fechas** - JavaScript Date API
- ✅ **Generación Dinámica de DOM** - Calendario y horarios
- ✅ **Estado de la Aplicación** - Objeto `reserva`
- ✅ **Validaciones** - Fechas, horarios y formularios
- ✅ **UX Optimizada** - Scroll automático, feedback visual
- ✅ **Diseño Modular** - Funciones reutilizables
- ✅ **Grid Layout CSS** - Calendario responsive

## 💼 Casos de Uso Reales

### Para Barbería en Loja:

```javascript
const servicios = [
    { id: 1, nombre: 'Corte Simple', duracion: '20 min', precio: 5.00, icon: '✂️' },
    { id: 2, nombre: 'Corte + Barba', duracion: '35 min', precio: 8.00, icon: '💈' },
    { id: 3, nombre: 'Tinte', duracion: '45 min', precio: 15.00, icon: '🎨' },
    { id: 4, nombre: 'Depilación Facial', duracion: '15 min', precio: 3.00, icon: '🪒' }
];
```

### Para Consultorio Médico:

```javascript
const servicios = [
    { id: 1, nombre: 'Consulta General', duracion: '30 min', precio: 25.00, icon: '🩺' },
    { id: 2, nombre: 'Consulta Especializada', duracion: '45 min', precio: 40.00, icon: '👨‍⚕️' },
    { id: 3, nombre: 'Control de Rutina', duracion: '20 min', precio: 15.00, icon: '📋' }
];
```

### Para Salón de Belleza:

```javascript
const servicios = [
    { id: 1, nombre: 'Corte Dama', duracion: '30 min', precio: 10.00, icon: '✂️' },
    { id: 2, nombre: 'Tinte Completo', duracion: '120 min', precio: 45.00, icon: '🎨' },
    { id: 3, nombre: 'Peinado', duracion: '45 min', precio: 15.00, icon: '💇‍♀️' },
    { id: 4, nombre: 'Manicure', duracion: '40 min', precio: 8.00, icon: '💅' },
    { id: 5, nombre: 'Depilación', duracion: '30 min', precio: 12.00, icon: '✨' }
];
```

### Para Taller Mecánico:

```javascript
const servicios = [
    { id: 1, nombre: 'Cambio de Aceite', duracion: '30 min', precio: 25.00, icon: '🛢️' },
    { id: 2, nombre: 'Revisión General', duracion: '60 min', precio: 35.00, icon: '🔧' },
    { id: 3, nombre: 'Alineación y Balanceo', duracion: '45 min', precio: 30.00, icon: '⚙️' },
    { id: 4, nombre: 'Cambio de Llantas', duracion: '20 min', precio: 15.00, icon: '🚗' }
];
```

## 🔮 Mejoras Futuras

- [ ] Integración con base de datos real
- [ ] Sistema de confirmación de citas por email
- [ ] Recordatorios automáticos
- [ ] Panel de administración
- [ ] Cancelación de citas
- [ ] Reprogramación de citas
- [ ] Lista de espera automática
- [ ] Múltiples profesionales
- [ ] Estadísticas de reservas
- [ ] Integración con Google Calendar

## ⚡ Ventajas del Sistema

### Para el Negocio:
- ✅ Reduce llamadas telefónicas
- ✅ Organiza mejor el día
- ✅ Menos citas olvidadas
- ✅ Profesionaliza el servicio
- ✅ Ahorra tiempo del personal
- ✅ Evita dobles reservas

### Para el Cliente:
- ✅ Reserva 24/7 desde cualquier lugar
- ✅ Ve horarios disponibles en tiempo real
- ✅ Elige el horario que más le convenga
- ✅ Confirmación instantánea
- ✅ Proceso rápido (menos de 2 minutos)

## 🐛 Solución de Problemas

### El calendario no se muestra
- Verifica que JavaScript esté habilitado
- Revisa la consola del navegador para errores

### Los horarios no aparecen
- Asegúrate de haber seleccionado un servicio primero
- Verifica que hayas seleccionado una fecha válida

### No se puede seleccionar una fecha
- Las fechas pasadas no son seleccionables
- Los domingos están deshabilitados por defecto
- Asegúrate de haber seleccionado un servicio

### El mensaje de WhatsApp no se envía
- Verifica el número de WhatsApp configurado
- Asegúrate de tener WhatsApp instalado o WhatsApp Web activo

## 🔧 Personalización Avanzada

### Habilitar Múltiples Días No Laborables

```javascript
// En generarCalendario()
const diaSemana = fecha.getDay();
const esNoLaborable = diaSemana === 0 || diaSemana === 6; // Domingo y Sábado
```

### Cambiar Horarios por Día de Semana

```javascript
function obtenerHorarios(fecha) {
    const dia = fecha.getDay();
    
    if (dia >= 1 && dia <= 5) { // Lunes a Viernes
        return ['09:00', '09:30', '10:00', '10:30', '11:00', '14:00', '14:30', '15:00'];
    } else if (dia === 6) { // Sábado
        return ['09:00', '09:30', '10:00', '10:30', '11:00'];
    }
    
    return []; // Domingo cerrado
}
```

### Agregar Duración Variable por Servicio

Ya está implementado - cada servicio tiene su campo `duracion`.

## 📄 Licencia

Proyecto bajo Licencia MIT - libre para usar y modificar.



<div align="center">

### ⭐ Si este proyecto te ayuda, dale una estrella ⭐



</div>

---

*Última actualización: Noviembre 2025*
