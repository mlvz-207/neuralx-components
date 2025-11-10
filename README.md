# NeuralX Components

Sistema de componentes web para la gestión de cuentas conectadas de **NeuralX Global**.

## Descripción

Este repositorio contiene componentes web reutilizables para visualizar y gestionar múltiples cuentas conectadas, incluyendo:
- Saldos y transacciones
- Información de perfiles
- Transferencias de dinero
- Reportes en PDF

## Estructura del Proyecto

```
neuralx-components/
├── assets/
│   ├── logo neuralx solo.png    # Logo de NeuralX
│   └── nx.css                   # Estilos globales del tema
├── components/
│   └── panel-multicuenta.html   # Componente principal de gestión de cuentas
└── README.md                    # Este archivo
```

## Componentes

### Panel Multi-cuenta (`panel-multicuenta.html`)

Componente principal que muestra información de múltiples cuentas en un sistema de pestañas.

**Características:**
- Sistema de pestañas para navegar entre cuentas
- Visualización de saldos (total, disponible, en tránsito)
- Perfil de cuenta con información detallada
- Barra de progreso de saldos
- Tema oscuro con gradientes personalizados

## Cuentas Configuradas

Actualmente el sistema gestiona las siguientes cuentas:

1. **Jose Dicarlo Ochoa**
   - ID: `acct_1SLCii1VTtI441E`
   - Conectado: 23 oct 2025
   - Sitio: www.neurax.com

2. **Edson Marcelino Romero**
   - ID: `acct_1SKC1H8QJiMAB0uV`
   - Conectado: 20 oct 2025
   - Sitio: www.sandbox.com

3. **Luis Guillermo Carreón**
   - ID: `acct_1SKBKy1eN6biy0sn`
   - Conectado: 20 oct 2025
   - Sitio: www.gmdjf.com

4. **Distribuidora de Medicamentos Lauret SA de CV**
   - Cuenta: 05832000151860070 (RGIOMXMTXXX)
   - Conectado: 28-29 may 2025
   - Sitio: www.lauret.com.mx
   - Correo: pagos@lauret.com.mx

## Cómo Usar

1. **Abrir el componente:**
   ```bash
   # Abrir en navegador
   open components/panel-multicuenta.html
   ```

2. **Agregar una nueva cuenta:**
   - Edita el archivo `components/panel-multicuenta.html`
   - Busca la sección `/* ============= EDITAR AQUÍ ============= */`
   - Agrega un nuevo objeto en el array `secciones`:

   ```javascript
   {
     id: "identificador-unico",
     titulo: "Nombre de la Cuenta",
     aviso: "Sin transferencias registradas.",
     saldos: {
       total: 0.00,
       breve: 0.00,
       transito: 0.00,
       disponibleTransferencias: 0.00,
       vitalicio: 0.00
     },
     perfil: {
       idCuenta: "ID_DE_CUENTA",
       conectado: "DD MMM YYYY",
       pais: "País",
       correo: "correo@ejemplo.com",
       sitio: "www.sitio.com",
       descripcionCargo: "DESCRIPCION",
       estado: "Activo"
     }
   }
   ```

3. **Personalizar estilos:**
   - Edita `assets/nx.css` para modificar colores, fuentes y efectos
   - Variables CSS disponibles:
     - `--nx-bg`: Color de fondo
     - `--nx-accent`: Color de acento
     - `--nx-purple`: Color púrpura
     - `--nx-cyan`: Color cian

## Tecnologías

- **HTML5**: Estructura del componente
- **CSS3**: Estilos con variables y gradientes
- **JavaScript (Vanilla)**: Lógica de interacción
- **Intl API**: Formateo de moneda (MXN)

## Formato de Datos

Los datos se almacenan en un objeto JavaScript dentro del HTML:

```javascript
const NX = {
  logo: "../assets/logo neuralx solo.png",
  secciones: [
    // Array de objetos de cuenta
  ]
};
```

## Características del Diseño

- **Tema oscuro**: Fondo `#0b1220` con gradientes
- **Colores de acento**: Púrpura `#7b5cff` y Cian `#00d3ff`
- **Tipografía**: Sans-serif moderna
- **Bordes**: Estilo punteado (`dashed`)
- **Efectos**: Sombras, desenfoque y transiciones suaves

## Desarrollo

Para modificar los componentes:

1. **Editar datos**: Modifica el objeto `NX` en `panel-multicuenta.html`
2. **Editar estilos**: Modifica `assets/nx.css`
3. **Probar cambios**: Abre el archivo HTML en un navegador
4. **Commit**: Guarda tus cambios con git

```bash
git add .
git commit -m "Descripción de los cambios"
git push
```

## Notas

- El formateo de moneda está configurado para **MXN (Peso Mexicano)**
- Los botones de "Simular" y "Descargar" están deshabilitados (pendiente de implementación)
- Las transferencias no están implementadas actualmente

## Licencia

Proyecto interno de **NeuralX Global**.

---

**Última actualización**: 10 nov 2025
