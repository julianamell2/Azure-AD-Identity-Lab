# 🛡️ Proyecto: Infraestructura Híbrida AD & Azure IAM Lab

## 📌 Resumen del Proyecto
Este laboratorio consiste en el diseño y despliegue de un entorno empresarial controlado en **Microsoft Azure**. El objetivo fue simular una infraestructura real de Active Directory para practicar la gestión de identidades (IAM), políticas de seguridad (GPO) y el monitoreo de eventos en un entorno de seguridad defensiva (SOC).
# 🔐 Laboratorio de Seguridad con Active Directory en Azure (SOC / IAM)

## 📌 Descripción General

Este proyecto consistió en construir un entorno completo de **Active Directory en Microsoft Azure** para simular escenarios reales empresariales enfocados en:

- Gestión de Identidades y Accesos (IAM)
- Operaciones de Seguridad (SOC)
- Administración de Windows Server
- Políticas de Grupo (GPO)
- Monitoreo y Auditoría
- Controles de Seguridad Blue Team
- Integración híbrida con Microsoft Entra ID

El objetivo principal fue obtener experiencia práctica configurando, administrando, asegurando y monitoreando un dominio Windows en la nube.

---

# 🏗️ Arquitectura del Laboratorio

## ☁️ Proveedor Cloud

- Microsoft Azure

## 🌐 Red Virtual

| Componente | Valor |
|-----------|------|
| Nombre VNet | VNet-AD-Learning |
| Segmento CIDR | 10.0.1.0/24 |
| DNS Principal | 10.0.1.4 |

---

# 💻 Máquinas Virtuales

| Nombre | Función | Sistema Operativo | IP |
|-------|--------|------------------|----|
| DC-LAB-01 | Controlador de Dominio / DNS | Windows Server 2022 | 10.0.1.4 |
| CLIENTE-01 | Equipo Cliente | Windows Server 2022 | Dinámica |

---

# 🏢 Configuración de Active Directory

| Configuración | Valor |
|-------------|------|
| Dominio | seguridad.lab |
| NetBIOS | SEGURIDAD |
| Nivel Funcional | Windows Server 2016 |

---

# 🔑 Gestión de Identidades (IAM)

## 👤 Administración de Usuarios

Creación y gestión de usuarios como:

- empleado1
- ventas1
- ventas2
- ventas3

## 🏢 Unidades Organizativas (OU)

Se crearon las siguientes OUs:

- Sistemas
- Ventas
- Directivos

## 👥 Grupos de Seguridad

Se creó:

- GG_Ventas

Aplicando permisos por grupos en lugar de asignarlos usuario por usuario.

---

# 🔐 Endurecimiento de Seguridad

## Política de Contraseñas

Se implementó una directiva donde:

- Mínimo 12 caracteres por contraseña

## Política de Bloqueo de Cuenta

Configuración aplicada:

- Bloqueo tras 5 intentos fallidos
- Desbloqueo automático tras 10 minutos

Protección frente a ataques de fuerza bruta.

---

# 📊 Monitoreo y Auditoría (SOC)

## Auditoría de Inicio de Sesión

Registro de:

- Inicios de sesión exitosos
- Intentos fallidos
- Cierres de sesión

## Auditoría de Administración de Cuentas

Monitoreo de:

- Restablecimiento de contraseñas
- Cambios en usuarios
- Bloqueos de cuentas

## Auditoría de Acceso a Objetos

Se habilitó auditoría en carpetas compartidas para detectar:

- Eliminación de archivos
- Accesos no autorizados
- Modificaciones de archivos sensibles

Prueba realizada con:

- `Nomina_Ventas_2026.txt`

---

# 📂 Recursos Compartidos

## Carpeta Compartida

Se creó:

- Datos_Ventas

Usada para permisos, auditoría y acceso por red.

## Mapeo Automático de Unidad por GPO

Se configuró una GPO para mapear la carpeta solo a usuarios pertenecientes a:

- GG_Ventas

---

# 🛡️ Control de Aplicaciones

## Implementación de AppLocker

Se configuraron reglas para impedir ejecución de software no autorizado.

### Pruebas realizadas:

Bloqueado:

- Bloc de notas para usuarios GG_Ventas
- Instalación de Google Chrome

---

# 📦 Despliegue de Software por GPO

Se realizó instalación remota automática de:

- 7-Zip

Mediante reinicio del equipo.

---

# 🗂️ Redirección de Carpetas

Se configuró Folder Redirection para proteger archivos de usuarios ante fallos del equipo.

Carpeta central:

- Usuarios

---

# 🖨️ Servicios de Impresión

Se instaló el rol de administración de impresión y se desplegó una impresora compartida por GPO.

También fue establecida como impresora predeterminada.

---

# 🔓 Delegación de Control

Se otorgaron permisos delegados a usuarios no administradores para:

- Restablecer contraseñas
- Consultar información de usuarios
- Agregar usuarios al grupo Ventas
- Administrar cuentas específicas

---

# ☁️ Integración Híbrida con Microsoft Entra ID

El laboratorio fue conectado con **Microsoft Entra Connect** para sincronizar identidades locales con la nube.

## Funcionalidades implementadas:

- Sincronización de usuarios locales hacia Microsoft Entra ID
- Escenario híbrido On-Premise + Cloud
- Preparación para Single Sign-On (SSO)
- Administración moderna de identidades

Esto permitió practicar entornos reales donde coexistente Active Directory local y servicios cloud.

---

# 🚨 Escenarios de Seguridad Simulados

Se realizaron pruebas como:

- Ataques de fuerza bruta
- Eliminación no autorizada de archivos
- Ejecución bloqueada de programas
- Restricción de instalaciones
- Bloqueo automático de cuentas

---

# 🧠 Habilidades Demostradas

## Active Directory

- AD DS
- Diseño de OUs
- Gestión de grupos
- Delegación

## Administración Windows

- GPO
- Compartición de recursos
- Solución de RDP
- Print Server

## Ciberseguridad

- Hardening
- Auditoría
- Blue Team
- Detección
- Gestión de accesos

## Cloud

- Azure Networking
- Máquinas virtuales
- DNS interno
- Microsoft Entra ID

---

# 🎯 Roles Relacionados

Este proyecto aporta experiencia para posiciones como:

- SOC Analyst
- IAM Analyst
- Administrador Windows
- Azure Administrator
- Cybersecurity Analyst
- Blue Team Junior

---

# 📸 Evidencias

Capturas de evidencias `/img`
## 📸 Evidencias del Laboratorio


 Capturas claves

![Dominio](img/Imagen1.png)
![Dominio](img/Imagen2.png)
![Dominio](img/Imagen3.png)
![Dominio](img/Imagen4.png)
![Dominio](img/Imagen5.png)
![Dominio](img/Imagen6.png)
![GPO](img/Imagen17.png)
![GPO](img/Imagen18.png)
![GPO](img/Imagen19.png)
![Entra Connect](img/Imagen56.png)
![Entra Connect](img/Imagen57.png)
![Entra Connect](img/Imagen58.png)

A continuación se muestran todas las capturas del proyecto:

![Imagen1](img/Imagen1.png)
![Imagen2](img/Imagen2.png)
![Imagen3](img/Imagen3.png)
![Imagen4](img/Imagen4.png)
![Imagen5](img/Imagen5.png)
![Imagen6](img/Imagen6.png)
![Imagen7](img/Imagen7.png)
![Imagen8](img/Imagen8.png)
![Imagen9](img/Imagen9.png)
![Imagen10](img/Imagen10.png)
![Imagen11](img/Imagen11.png)
![Imagen12](img/Imagen12.png)
![Imagen13](img/Imagen13.png)
![Imagen14](img/Imagen14.png)
![Imagen15](img/Imagen15.png)
![Imagen16](img/Imagen16.png)
![Imagen17](img/Imagen17.png)
![Imagen18](img/Imagen18.png)
![Imagen19](img/Imagen19.png)
![Imagen20](img/Imagen20.png)
![Imagen21](img/Imagen21.png)
![Imagen22](img/Imagen22.png)
![Imagen23](img/Imagen23.png)
![Imagen24](img/Imagen24.png)
![Imagen25](img/Imagen25.png)
![Imagen26](img/Imagen26.png)
![Imagen27](img/Imagen27.png)
![Imagen28](img/Imagen28.png)
![Imagen29](img/Imagen29.png)
![Imagen30](img/Imagen30.png)
![Imagen31](img/Imagen31.png)
![Imagen32](img/Imagen32.png)
![Imagen33](img/Imagen33.png)
![Imagen34](img/Imagen34.png)
![Imagen35](img/Imagen35.png)
![Imagen36](img/Imagen36.png)
![Imagen37](img/Imagen37.png)
![Imagen38](img/Imagen38.png)
![Imagen39](img/Imagen39.png)
![Imagen40](img/Imagen40.png)
![Imagen41](img/Imagen41.png)
![Imagen42](img/Imagen42.png)
![Imagen43](img/Imagen43.png)
![Imagen44](img/Imagen44.png)
![Imagen45](img/Imagen45.png)
![Imagen46](img/Imagen46.png)
![Imagen47](img/Imagen47.png)
![Imagen48](img/Imagen48.png)
![Imagen49](img/Imagen49.png)
![Imagen50](img/Imagen50.png)
![Imagen51](img/Imagen51.png)
![Imagen52](img/Imagen52.png)
![Imagen53](img/Imagen53.png)
![Imagen54](img/Imagen54.png)
![Imagen55](img/Imagen55.png)
![Imagen56](img/Imagen56.png)
![Imagen57](img/Imagen57.png)
![Imagen58](img/Imagen58.png)
