# Panify — Backend

> **"Horneamos Calidad, Entregamos Confianza."**

Backend de **Panify**, el sistema de gestión de pedidos, inventario y entregas de la panadería **Distribuciones Oro Pan**. Centraliza la lógica de negocio y el acceso a los datos de la plataforma web, reemplazando el registro manual de pedidos (llamadas y papel).

> 🚧 **Estado del proyecto:** en fase de diseño. El stack tecnológico y el estilo de la API están **por definir** (ver [Decisiones técnicas pendientes](#-decisiones-técnicas-pendientes)).

---

## 📌 Contexto

| | |
|---|---|
| **Cliente / caso de estudio** | Panadería "Distribuciones Oro Pan" |
| **Programa** | SENA — Análisis y Desarrollo de Software (ADSO) |
| **Ficha / Grupo** | 3315796 / Grupo 4 |
| **Alcance** | Sistema operativo de pedidos y stock. No cubre procesos contables ni financieros complejos. |

**Problema:** los pedidos se toman de forma manual, lo que causa pérdida de información, retrasos en producción, confusiones para el domiciliario y falta de comprobantes claros para el cliente.

---

## 🎯 Objetivo del backend

Proveer la lógica de negocio, las reglas de validación y la persistencia que necesita el frontend para gestionar pedidos, inventario, recibos y entregas.

---

## 📦 Módulos

| Módulo | Responsabilidad |
|---|---|
| **Gestión de Usuarios** | Registro, inicio de sesión, recuperación de contraseña y perfil con historial. Control de acceso por roles: Administrador, Cliente, Domiciliario y Panadero. |
| **Productos e Inventario** | CRUD del catálogo, stock mínimo, alertas de producto agotado y descuento automático del inventario al confirmar un pedido. |
| **Gestión de Pedidos** | Creación de pedidos validados contra el stock disponible y control horario (bloqueo de pedidos para el mismo día después de la hora límite). |
| **Gestión de Recibos** | Comprobante por cada pedido, con precios congelados al momento de la compra, y reportes operativos (diarios, semanales y mensuales). |
| **Entregas y Rutas** | Panel de prioridades ordenado por hora y urgencia, y lista de rutas simplificada para el panadero y el domiciliario. |

---

## 🗄️ Base de datos

- **Motor:** MySQL (modelo relacional normalizado hasta la **3FN**).
- **Modelado:** MySQL Workbench.
- **Control de acceso:** especialización de `USUARIO` en `CLIENTE`, `DOMICILIARIO` y `PANADERO`.
- **Entidades principales:** `USUARIO`, `CLIENTE`, `DOMICILIARIO`, `PANADERO`, `DIRECCION`, `PRODUCTO`, `PEDIDO`, `DETALLE_PEDIDO`, `RECIBO`.
- **Valores derivados (calculados, no almacenados):** total a pagar, subtotal y estado de stock.

---

## 🛠️ Tecnologías

| Componente | Tecnología |
|---|---|
| Base de datos | MySQL |
| Lenguaje / entorno de ejecución | *Por definir* |
| Framework | *Por definir* |
| Estilo de API | *Por definir* |
| Autenticación | *Por definir* |
| Generación de PDF (recibos) | *Por definir* |
| Control de versiones | Git y GitHub |

---

## ❓ Decisiones técnicas pendientes

- [ ] Lenguaje y entorno de ejecución
- [ ] Framework del servidor
- [ ] Estilo de comunicación con el frontend (por ejemplo, API REST u otro)
- [ ] Mecanismo de autenticación y manejo de sesiones
- [ ] Cifrado de contraseñas
- [ ] Librería para generar recibos en PDF
- [ ] Estrategia de despliegue

---

## 🚀 Instalación y ejecución

*Se completará cuando se defina el stack.*

```bash
# Pasos por definir
```

---

## 📁 Estructura del proyecto

*Se documentará cuando se defina la arquitectura.*

---

## 🌿 Flujo de trabajo en Git

### Ramas por módulo (Feature Branches)

```bash
# Por definir
```

### Commits semánticos

Formato: `<tipo>(<ámbito>): <descripción en imperativo y minúsculas, máx. 50 caracteres>`

- **Tipos:** `feat`, `docs`, `style`, `refactor`, `chore`
- **Ámbitos comunes:** `db`, `repo`, `admin`, `cliente`, `trimestre3`

Ejemplos:

```
docs(repo): agregar readme inicial del backend
feat(db): crear tablas de usuarios y roles
chore(repo): configurar gitignore
```

---

## 👥 Equipo

- Brayan Sneyder Devia Muñoz
- Martín Cruz Muñoz
- Jeison Alejandro Diaz Acosta
- Brandon Duvan Guevara Rodríguez
- Kevin Julian González Chavez
