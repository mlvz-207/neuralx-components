# Guía de Contribución - NeuralX Components

## Cómo Agregar una Nueva Cuenta

### 1. Ubicación del Archivo

Edita: `components/panel-multicuenta.html`

### 2. Buscar la Sección de Datos

Busca el comentario:
```javascript
/* ============= EDITAR AQUÍ ============= */
```

### 3. Agregar Nueva Entrada

Dentro del array `secciones`, agrega un nuevo objeto:

```javascript
{
  id: "identificador-unico",           // ID único (sin espacios, minúsculas)
  titulo: "Nombre Completo o Razón Social",
  aviso: "Sin transferencias registradas.",
  saldos: {
    total: 0.00,                      // Saldo total
    breve: 0.00,                      // Disponible pronto
    transito: 0.00,                   // En tránsito
    disponibleTransferencias: 0.00,   // Disponible para transferir
    vitalicio: 0.00                   // Total acumulado histórico
  },
  perfil: {
    idCuenta: "NUMERO_DE_CUENTA",    // Cuenta bancaria o ID
    conectado: "DD MMM YYYY",         // Fecha de conexión
    pais: "País",                     // País de la cuenta
    correo: "email@dominio.com",      // Correo de contacto
    sitio: "www.sitio.com",           // Sitio web
    descripcionCargo: "NOMBRE CORTO", // Descripción breve (mayúsculas)
    estado: "Activo"                  // Estado: Activo/Inactivo
  }
}
```

### 4. Ejemplo Real

**Distribuidora de Medicamentos Lauret SA de CV:**

```javascript
{
  id: "lauret",
  titulo: "Distribuidora de Medicamentos Lauret SA de CV",
  aviso: "Sin transferencias registradas.",
  saldos: {
    total: 0.00,
    breve: 0.00,
    transito: 0.00,
    disponibleTransferencias: 0.00,
    vitalicio: 0.00
  },
  perfil: {
    idCuenta: "05832000151860070 (RGIOMXMTXXX)",
    conectado: "28-29 may 2025",
    pais: "México",
    correo: "pagos@lauret.com.mx",
    sitio: "www.lauret.com.mx",
    descripcionCargo: "DISTRIBUIDORA LAURET",
    estado: "Activo"
  }
}
```

### 5. Validar los Datos

Antes de guardar, verifica:
- [ ] El `id` es único y no existe en otras cuentas
- [ ] Todos los campos están completos
- [ ] Los saldos son números (usa `.00` para decimales)
- [ ] El correo tiene formato válido
- [ ] El sitio web está correctamente formateado
- [ ] No olvidaste la coma `,` al final del objeto (si no es el último)

### 6. Probar en el Navegador

Abre `components/panel-multicuenta.html` en un navegador y verifica:
- [ ] Aparece una nueva pestaña con el nombre de la cuenta
- [ ] Los datos se muestran correctamente
- [ ] No hay errores en la consola del navegador
- [ ] La navegación entre pestañas funciona

### 7. Commit y Push

```bash
git add components/panel-multicuenta.html
git commit -m "Agregar perfil: [Nombre de la Cuenta]"
git push
```

## Actualizar Saldos

Para actualizar los saldos de una cuenta existente:

1. Busca la cuenta por su `id`
2. Modifica los valores en el objeto `saldos`
3. Guarda y prueba en el navegador

**Ejemplo:**
```javascript
saldos: {
  total: 125000.00,                    // Nuevo total
  breve: 5000.00,                      // Próximo a recibir
  transito: 2000.00,                   // En proceso
  disponibleTransferencias: 118000.00, // Disponible ahora
  vitalicio: 250000.00                 // Histórico total
}
```

## Personalizar Estilos

### Cambiar Colores

Edita `assets/nx.css` y modifica las variables:

```css
:root {
  --nx-bg: #0b1220;      /* Fondo principal */
  --nx-accent: #1a2b45;  /* Fondo de tarjetas */
  --nx-purple: #7b5cff;  /* Acento púrpura */
  --nx-cyan: #00d3ff;    /* Acento cian */
}
```

### Cambiar el Logo

Reemplaza el archivo `assets/logo neuralx solo.png` con tu nuevo logo.

## Estructura de Archivos

```
neuralx-components/
├── assets/
│   ├── logo neuralx solo.png    # Logo (PNG transparente recomendado)
│   └── nx.css                   # Estilos globales
├── components/
│   └── panel-multicuenta.html   # Componente principal (EDITAR AQUÍ)
├── .gitignore                   # Archivos ignorados por Git
├── README.md                    # Documentación principal
└── CONTRIBUTING.md              # Esta guía
```

## Convenciones

### IDs de Cuenta
- Usar minúsculas
- Sin espacios (usar guiones `-` si es necesario)
- Descriptivo y único
- Ejemplos: `jose`, `edson`, `lauret`, `empresa-xyz`

### Formato de Fechas
- Usar formato: `DD MMM YYYY`
- Ejemplos: `28 may 2025`, `20 oct 2025`, `01 ene 2026`

### Descripción en Extracto
- MAYÚSCULAS
- Breve y descriptivo
- Máximo 20 caracteres
- Ejemplos: `NEURALX.COM`, `DISTRIBUIDORA LAURET`, `SWISS PAY`

### Estados Válidos
- `Activo`: Cuenta operativa
- `Inactivo`: Cuenta suspendida
- `Pendiente`: Cuenta en proceso de activación

## Solución de Problemas

### La pestaña no aparece
- Verifica que el `id` sea único
- Asegúrate de que la sintaxis JavaScript sea correcta
- Revisa que no falten comas

### Errores de formato
- Abre la consola del navegador (F12)
- Busca errores de sintaxis
- Verifica que todos los strings estén entre comillas

### Los saldos no se muestran correctamente
- Asegúrate de usar números, no strings
- Usa formato decimal: `1000.00` no `1000`
- No uses comas para miles: `1000000.00` no `1,000,000.00`

## Contacto

Para dudas o problemas, contacta al equipo de desarrollo de **NeuralX Global**.

---

**Última actualización**: 10 nov 2025
