# Hotel Sunset Paradise - Sistema de Gestión de Reservas

Sistema web para la gestión integral de reservas hoteleras desarrollado con ASP.NET Core MVC.

## Descripción del Proyecto

El sistema Hotel Sunset Paradise permite al personal administrativo gestionar de manera eficiente:
- Habitaciones del hotel (registro, tipos, precios, disponibilidad)
- Clientes (registro con datos personales)
- Reservas (asignación de habitaciones, cálculo de costos, validación de fechas)

## Características Principales

- **Autenticación básica** con sesiones de usuario
- **Gestión completa de habitaciones** (CRUD)
- **Registro y administración de clientes**
- **Sistema de reservas** con validación automática
- **Dashboard informativo** con estadísticas en tiempo real
- **Diseño responsive** adaptable a dispositivos móviles
- **Validaciones robustas** tanto en servidor como en cliente

## Tecnologías Utilizadas

- **Backend:** ASP.NET Core MVC (.NET 6+)
- **Frontend:** HTML5, Bootstrap 5, JavaScript, jQuery
- **Estilos:** Bootstrap 5, Font Awesome
- **Validaciones:** Data Annotations, jQuery Validation
- **Estado:** Sessions para manejo de autenticación

## Requisitos del Sistema

- .NET 6.0 SDK o superior
- Visual Studio 2022 (recomendado) o Visual Studio Code
- Navegador web moderno (Chrome, Firefox, Edge)

## Instalación y Configuración

### 1. Clonar el repositorio
```bash
git clone [URL-del-repositorio]
cd HotelSunsetParadise
```

### 2. Restaurar dependencias
```bash
dotnet restore
```

### 3. Ejecutar la aplicación
```bash
dotnet run
```

O desde Visual Studio:
- Abrir el archivo `HotelSunsetParadise.sln`
- Presionar `F5` o hacer clic en "Start Debugging"

### 4. Acceder al sistema
- Abrir navegador en: `http://localhost:5000`
- Usar credenciales de prueba:
  - **Usuario:** admin
  - **Contraseña:** 123

## Estructura del Proyecto

```
HotelSunsetParadise/
├── Controllers/           # Controladores MVC
│   ├── BaseController.cs
│   ├── AccountController.cs
│   ├── HomeController.cs
│   ├── HabitacionesController.cs
│   ├── ClientesController.cs
│   └── ReservasController.cs
├── Models/               # Modelos de datos
│   └── HotelModels.cs
├── Services/             # Servicios de negocio
│   └── DataService.cs
├── Views/                # Vistas Razor
│   ├── Shared/
│   ├── Account/
│   ├── Home/
│   ├── Habitaciones/
│   ├── Clientes/
│   └── Reservas/
└── Program.cs           # Configuración de la aplicación
```

## Funcionalidades

### 1. Autenticación
- Login con credenciales hardcodeadas (admin/123)
- Manejo de sesiones para mantener estado de usuario
- Protección de rutas (redirección automática a login)
- Logout con limpieza de sesión

### 2. Gestión de Habitaciones
- **Agregar habitaciones:** Formulario con validaciones
  - Número único de habitación
  - Tipos: Individual, Doble, Suite, Presidencial
  - Precio por noche
  - Estado: Disponible, Ocupada, Mantenimiento
- **Listar habitaciones:** Vista completa con estado visual
- **Ver disponibles:** Filtro de habitaciones libres para reservas

### 3. Gestión de Clientes
- **Registrar clientes:** Formulario con validaciones
  - Nombre completo (requerido, máximo 100 caracteres)
  - DUI único (formato validado)
  - Número de teléfono
- **Listar clientes:** Vista tabular de todos los registrados

### 4. Sistema de Reservas
- **Crear reservas:** Formulario completo con dropdowns dinámicos
  - Selección de cliente existente
  - Selección de habitación disponible
  - Fechas de entrada y salida con validaciones
  - Cálculo automático del total (precio × noches)
- **Validaciones implementadas:**
  - Fecha de entrada no puede ser pasada
  - Fecha de salida debe ser posterior a entrada
  - No solapamiento de fechas para misma habitación
- **Listar reservas:** Vista de todas las reservas activas

### 5. Dashboard Principal
- Estadísticas en tiempo real:
  - Total de habitaciones registradas
  - Habitaciones disponibles
  - Clientes registrados
  - Reservas activas
- Accesos rápidos a funcionalidades principales

## Datos Predeterminados

El sistema incluye habitaciones predefinidas:
- **101, 102:** Individual ($45.00/noche)
- **201, 202:** Doble ($75.00/noche)
- **301, 302:** Suite ($120.00/noche)
- **401:** Presidencial ($200.00/noche)

## Validaciones Implementadas

### Server-Side (Data Annotations)
- Campos requeridos
- Rangos de valores
- Longitud de strings
- Tipos de datos específicos

### Client-Side (JavaScript)
- Validación de fechas en tiempo real
- Prevención de fechas pasadas
- Sincronización de fechas de entrada/salida

### Business Logic
- DUI único por cliente
- Número único de habitación
- Disponibilidad de habitaciones
- No solapamiento de reservas

## Patrones de Diseño

- **MVC (Model-View-Controller):** Separación clara de responsabilidades
- **Repository Pattern:** DataService como abstracción de datos
- **Dependency Injection:** Servicios de ASP.NET Core

## Seguridad

- Protección de rutas con validación de sesiones
- Validación de entrada en servidor y cliente
- Cookies de sesión HttpOnly
- Sanitización automática de datos por Razor

## Troubleshooting

### Problema: No se abre el navegador automáticamente
**Solución:** Verificar `launchSettings.json` tenga `"launchBrowser": true`

### Problema: Puerto ocupado
**Solución:** Cambiar puerto en `launchSettings.json` o ejecutar `dotnet run --urls="http://localhost:5001"`

### Problema: Errores de compilación
**Solución:** 
1. Clean Solution (Build → Clean Solution)
2. Rebuild Solution (Build → Rebuild Solution)
3. Verificar que todos los using statements estén presentes

## Equipo de Desarrollo

- **[Alejandra Cristal Calderon Escobar CE231635]** - Desarrollo Full Stack
- **[Gladis Del Carmen Rivas Miranda RM191684]** - Desarrollo Full Stack

  **ENLACE DEL VIDEO**
  https://drive.google.com/file/d/1FmB3SUQ0YjMcrVJ-B-5iesg8LjM8TyPL/view?usp=drivesdk


## Licencia

Este proyecto fue desarrollado como parte del desafío práctico #2 de la materia "Desarrollo de aplicaciones con software propietario" de la Universidad Don Bosco.

---

**Universidad Don Bosco**  
Facultad de Ingeniería - Escuela de Computación  
Septiembre 2025
