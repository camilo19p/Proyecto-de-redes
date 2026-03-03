# 🌐 Proyecto de Redes - Simulación en Cisco Packet Tracer
  
👤 Autor
Camilo Andrés Martínez Peña

## 📋 Descripción

Simulación de una red empresarial multi-sitio en **Cisco Packet Tracer**, que implementa subnetting con **VLSM**, enrutamiento dinámico con **RIP v2**, y servicios de red centralizados (**DHCP**, **DNS** y **Web Server**).

La red simula cuatro entornos o sedes denominados: **Ternera**, **Alamedas**, **Recreo** y **Castellana**, interconectadas mediante routers y enlaces WAN.

---

## 🗺️ Topología de Red

La topología está compuesta por **4 redes LAN** y **6 enlaces punto a punto** entre routers.

| Sede       | Red asignada       | Hosts requeridos |
|------------|--------------------|------------------|
| Ternera    | 192.168.226.0/24   | 53 direcciones   |
| Recreo     | 192.168.228.0/24   | 28 direcciones   |
| Alamedas   | 192.168.227.0/24   | 12 direcciones   |
| Castellana | 192.168.229.0/24   | 5 direcciones    |

### 🔗 Tabla de Enlaces WAN

| Enlace   | Red            |
|----------|----------------|
| Enlace 1 | 192.168.1.0/24 |
| Enlace 2 | 192.168.2.0/24 |
| Enlace 3 | 192.168.3.0/24 |
| Enlace 4 | 192.168.4.0/24 |
| Enlace 5 | 192.168.5.0/24 |
| Enlace 6 | 192.168.6.0/24 |

---

## ⚙️ Configuraciones Implementadas

### 1. 🖧 Diseño de Topología
- Construcción de la topología en Cisco Packet Tracer con la distribución de dispositivos por sede.
- Nombramiento de PCs y Routers según estándar definido.
- Asignación y marcado de direcciones IP en cada interfaz y dispositivo.

### 2. 🔧 Configuración de Routers (CLI)
- Configuración del **hostname** en cada router.
- Asignación de direcciones IP a todas las interfaces activas (LAN y WAN).
- Activación de interfaces con `no shutdown`.

```bash
# Ejemplo de configuración de router
Router(config)# hostname R-Ternera
R-Ternera(config)# interface gigabitEthernet 0/0
R-Ternera(config-if)# ip address 192.168.226.1 255.255.255.0
R-Ternera(config-if)# no shutdown
3. 🔄 Enrutamiento Dinámico - RIP v2

Configuración de RIP versión 2 en todos los routers.
Publicación de todas las redes conectadas.
Verificación de conectividad total entre todas las sedes.

Bash# Ejemplo de configuración RIP v2
R-Ternera(config)# router rip
R-Ternera(config-router)# version 2
R-Ternera(config-router)# network 192.168.226.0
R-Ternera(config-router)# network 192.168.1.0
R-Ternera(config-router)# no auto-summary
4. 🏠 Servidor DHCP

Configuración de pools DHCP para las 4 sedes (Ternera, Recreo, Alamedas, Castellana).
Cada pool incluye: IP de red, máscara de subred, Default Gateway y DNS Server.
Los equipos de todas las sedes reciben configuración IP de forma dinámica.

PoolRedDefault GWTernera192.168.226.0192.168.226.1Recreo192.168.228.0192.168.228.1Alamedas192.168.227.0192.168.227.1Castellana192.168.229.0192.168.229.1
5. 💻 Configuración de PCs

Todos los PCs configurados en modo DHCP.
Verificación de asignación automática de IP, máscara, gateway y DNS.

6. 🌍 Servidor DNS

Configuración de servidor DNS con un dominio personalizado.
Resolución de nombres para acceder al servidor Web mediante dominio.

7. 🌐 Servidor Web

Servidor Web configurado y activo.
Página web personalizada cargada como simulación de aplicativo web.
Accesible desde cualquier PC de la red mediante el dominio DNS configurado.

🛠️ Tecnologías y Herramientas

Protocolo de enrutamiento: RIP v2
Servicios: DHCP, DNS, HTTP (Web Server)
Direccionamiento: IPv4 / VLSM

🚀 Cómo abrir el proyecto

Descargar e instalar Cisco Packet Tracer (requiere cuenta Cisco Networking Academy).
Clonar o descargar este repositorio.
Abrir el archivo Proyecto de Redes - Simulación en Cisco Packet Tracer.pkt desde Packet Tracer.
Explorar la topología y verificar las configuraciones en cada dispositivo.


✅ Resultados

✔️ Conectividad total entre todas las sedes mediante RIP v2.
✔️ Asignación dinámica de IPs a todos los equipos vía DHCP.
✔️ Resolución de dominio funcional mediante servidor DNS.
✔️ Acceso al servidor Web desde cualquier PC de la red.
