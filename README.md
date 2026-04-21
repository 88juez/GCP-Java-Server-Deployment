# Implementación y Optimizaciónde servidor Minecraft en GCP

Este repositorio documenta el despliegue de un servidor de aplicaciones Java (Minecraft Engine) en la nube, enfocado en la optimización de recursos limitados y la persistencia de servicios.

## 🛠️ Tecnologías y Herramientas
* **Cloud:** Google Cloud Platform (Compute Engine).
* **OS:** Linux Debian (Administración vía SSH).
* **Runtime:** Java Virtual Machine (JVM).
* **Redes:** DNS Dinámico (DuckDNS), Reserva de IP Estática y reglas de Firewall (VPC).
* **Persistencia:** Linux Screen para gestión de procesos en segundo plano.

## 🚀 Desafíos Técnicos y Soluciones

### 1. Optimización de Memoria (JVM Tuning)
Dada la restricción de RAM en la instancia, se configuraron flags avanzados de Java para balancear el consumo del sistema operativo y la aplicación, utilizando el Garbage Collector G1GC para minimizar la latencia.
* **Comando optimizado:** `java -Xmx1200M -Xms1200M -XX:+UseG1GC -jar server.jar nogui`

### 2. Disponibilidad y Networking
* **IP Estática:** Se realizó la reserva de una dirección IP externa para evitar la pérdida de conectividad tras reinicios.
* **DNS:** Implementación de un nombre de dominio personalizado mediante DuckDNS.

### 3. Persistencia de Servicio
Implementación de `screen` en Linux, permitiendo que el servidor permanezca activo de forma independiente a la sesión de usuario o desconexión del terminal SSH.

## 📸 Evidencias
<img width="899" height="713" alt="Captura de pantalla 2026-04-21 053203" src="https://github.com/user-attachments/assets/5872ed83-5b50-4142-9775-30a1795955f7" />
<img width="1029" height="479" alt="Captura de pantalla 2026-04-21 053318" src="https://github.com/user-attachments/assets/d1470a20-d508-4f8e-8e59-be20dac736ed" />
<img width="1038" height="678" alt="Captura de pantalla 2026-04-21 053338" src="https://github.com/user-attachments/assets/3c4ae064-e0df-48ac-9f31-f9044c52f9d0" />
<img width="862" height="514" alt="Captura de pantalla 2026-04-21 071111" src="https://github.com/user-attachments/assets/e12a2956-df5b-48c4-b3e2-4caf647e3390" />
<img width="950" height="90" alt="Captura de pantalla 2026-04-21 080842" src="https://github.com/user-attachments/assets/c9c93b61-8339-4124-ab40-8d79a40cbfb5" />
