# 📊 Monitoreo con Prometheus y Grafana usando Docker

Práctica de monitoreo de aplicaciones y sistemas usando Prometheus, Grafana y Node Exporter con Docker Compose.

---

## 🛠️ Requisitos

- [Docker](https://www.docker.com/) instalado
- [Docker Compose](https://docs.docker.com/compose/) instalado

---

## 📁 Estructura del proyecto

```
monitoring-practice/
├── docker-compose.yml
├── prometheus.yml
└── README.md
```

---

## 🚀 Pasos para ejecutar

### 1. Clonar el repositorio

```bash
git clone <URL_DEL_REPO>
cd monitoring-practice
```

### 2. Levantar los contenedores

```bash
docker-compose up -d
```

### 3. Verificar que los servicios estén corriendo

```bash
docker ps
```

---

## 🌐 Acceso a los servicios

| Servicio     | URL                    | Usuario | Contraseña |
|--------------|------------------------|---------|------------|
| Prometheus   | http://localhost:9090  | -       | -          |
| Grafana      | http://localhost:3000  | admin   | admin      |
| Node Exporter| http://localhost:9100  | -       | -          |

---

## 📈 Configurar Grafana

1. Abre **http://localhost:3000** e inicia sesión con `admin` / `admin`.
2. Ve a **Configuration → Data Sources → Add data source**.
3. Selecciona **Prometheus**.
4. En la URL escribe: `http://prometheus:9090`
5. Haz clic en **Save & Test**.

### Crear un Dashboard

1. Ve a **Dashboards → New Dashboard**.
2. Haz clic en **Add new panel**.
3. En el campo de consulta (Query), usa alguna de estas métricas:
   - `node_cpu_seconds_total` — Uso de CPU
   - `node_memory_Active_bytes` — Memoria activa
   - `node_filesystem_avail_bytes` — Espacio en disco disponible
4. Haz clic en **Apply** y guarda el dashboard.

---

## 🛑 Detener los contenedores

```bash
docker-compose down
```

---

## 📚 Tecnologías utilizadas

- **Prometheus** – Sistema de monitoreo y alertas
- **Grafana** – Visualización de métricas
- **Node Exporter** – Exportador de métricas del sistema
- **Docker Compose** – Orquestación de contenedores
