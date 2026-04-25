# Servidor-web-estatico-con-dominio-propio
Configuración de servidor web con dominio propio con certificado SSL | redirección HTTP > HTTPS
| Comando                                  | Función                                          |
| ---------------------------------------- | ------------------------------------------------ |
| ssh usuario@TU_IP_VPS                  | Conectarte a la VPS por SSH                      |
| sudo apt update && sudo apt upgrade -y| Actualizar lista de paquetes y sistema operativo |

Instalación y gestión de Nginx
| ------------------------------ | ---------------------------------------------------------------------- |
| sudo apt install nginx -y    | Instalar el servidor web Nginx                                         |
| sudo systemctl status nginx  | Verificar si Nginx está corriendo                                      |
| sudo systemctl start nginx   | Iniciar el servicio Nginx                                              |
| sudo systemctl enable nginx  | Habilitar Nginx para que inicie automáticamente al arrancar el sistema |
| sudo systemctl restart nginx | Reiniciar Nginx (aplica cambios de configuración)                      |
| sudo systemctl reload nginx  | Recargar configuración sin cortar conexiones activas                   |
| sudo nginx -t                | Probar que la sintaxis de la configuración de Nginx sea correcta       |

Configuración de reglas del firewall del sistema (Debian)
| ---------------------------------------------- | -------------------------------------------------- |
| sudo apt install ufw -y                      | Instalar Uncomplicated Firewall                    |
| sudo ufw default deny incoming               | Bloquear todo el tráfico entrante por defecto      |
| sudo ufw default allow outgoing              | Permitir todo el tráfico saliente por defecto      |
| sudo ufw allow ssh` o `sudo ufw allow 22/tcp | Permitir conexiones SSH (¡para no quedarte fuera!) |
| sudo ufw allow 'Nginx Full                   | Abrir puertos 80 (HTTP) y 443 (HTTPS) para Nginx   |
| sudo ufw allow 80/tcp                        | Abrir manualmente el puerto 80 (HTTP)              |
| sudo ufw allow 443/tcp                       | Abrir manualmente el puerto 443 (HTTPS)            |
| sudo ufw --force enable                      | Activar el firewall                                |
| sudo ufw status verbose                      | Ver estado detallado del firewall y reglas activas |
