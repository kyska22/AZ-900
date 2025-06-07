# **Modelos de Servicios en la Nube: IaaS, PaaS y SaaS**  
*(Explicación para la Certificación AZ-900 con Ejemplos y Laboratorios Prácticos)*  

## **🌩️ Introducción**  
Los modelos de servicios en la nube (**IaaS, PaaS y SaaS**) definen cómo se distribuyen las responsabilidades entre el proveedor de nube (Azure) y el cliente. Hoy exploraremos cada uno con **ejemplos reales** y **laboratorios prácticos** usando el *Free Tier de Azure*.  

---

## **🔗 Modelo de Responsabilidad Compartida**  
Antes de profundizar, es clave entender que **Azure y el cliente comparten responsabilidades** según el servicio usado:  

| **Componente**               | **On-Premises** | **IaaS**       | **PaaS**       | **SaaS**       |
|------------------------------|-----------------|----------------|----------------|----------------|
| **Centro de datos físico**   | Cliente         | Azure          | Azure          | Azure          |
| **Redes y conectividad**     | Cliente         | Azure          | Azure          | Azure          |
| **Sistema operativo**        | Cliente         | **Cliente**    | Azure          | Azure          |
| **Aplicaciones y datos**     | Cliente         | **Cliente**    | **Cliente**    | **Cliente***   |

> (*) En SaaS, el cliente solo gestiona sus datos.  

---

## **1. Infrastructure as a Service (IaaS)**  
### **📌 Definición**  
Azure proporciona la **infraestructura básica** (servidores, almacenamiento, redes), pero el cliente gestiona:  
- Sistemas operativos.  
- Aplicaciones.  
- Parches de seguridad.  

### **🔍 Ejemplo Práctico**  
**Escenario:** Migrar un servidor local a la nube sin modificar la aplicación (*lift-and-shift*).  
**Servicio Azure:** **Máquinas Virtuales (Azure VMs)**.  

#### **Laboratorio 1: Crear una VM en Azure (Free Tier)**  
1. **Paso 1:** Ve a [Azure Portal](https://portal.azure.com) → "Crear un recurso" → "Máquina virtual".  
2. **Paso 2:** Configura:  
   - **SO:** Ubuntu Server 20.04 LTS.  
   - **Tamaño:** *B1s (gratis en Free Tier)*.  
   - **Red virtual:** Crear nueva.  
3. **Paso 3:** Conéctate via SSH y instala un servidor web (Nginx):  
   ```bash
   sudo apt update && sudo apt install nginx -y
   ```  
4. **Resultado:** Tu app estará accesible en la IP pública de la VM.  

**Responsabilidades:**  
✔ **Azure:** Hardware, red, energía.  
✔ **Tú:** Instalar SO, aplicaciones y parches.  

---

## **2. Platform as a Service (PaaS)**  
### **📌 Definición**  
Azure gestiona **infraestructura + sistema operativo**, y tú te enfocas en:  
- Desarrollar aplicaciones.  
- Gestionar datos.  

### **🔍 Ejemplo Práctico**  
**Escenario:** Desplegar una aplicación web sin administrar servidores.  
**Servicio Azure:** **Azure App Service**.  

#### **Laboratorio 2: Desplegar una App en App Service (Free Tier)**  
1. **Paso 1:** En Azure Portal → "App Service" → "Crear".  
2. **Paso 2:** Configura:  
   - **Runtime stack:** Node.js 14 LTS.  
   - **Sistema operativo:** Linux (gratis).  
3. **Paso 3:** Despliega código desde GitHub o sube un archivo ZIP.  
4. **Resultado:** Tu app estará en `https://nombre-de-tu-app.azurewebsites.net`.  

**Responsabilidades:**  
✔ **Azure:** SO, servidores, escalabilidad.  
✔ **Tú:** Código y datos.  

---

## **3. Software as a Service (SaaS)**  
### **📌 Definición**  
Azure ofrece **aplicaciones completas** listas para usar. Tú solo gestionas:  
- Usuarios.  
- Datos ingresados.  

### **🔍 Ejemplo Práctico**  
**Escenario:** Usar correo empresarial sin instalar servidores.  
**Servicio Azure:** **Microsoft 365 (Outlook, Teams)**.  

**Responsabilidades:**  
✔ **Azure:** Todo (infraestructura, app, actualizaciones).  
✔ **Tú:** Datos y configuración de usuarios.  

---

## **📊 Comparativa Final**  
| **Modelo** | **Control del Cliente** | **Ejemplo Azure**       | **Ideal para**                  |
|------------|------------------------|-------------------------|----------------------------------|
| **IaaS**   | Alto (SO, apps)        | Azure VMs               | Migraciones "lift-and-shift".    |
| **PaaS**   | Medio (solo apps)      | App Service, Azure SQL  | Desarrolladores que quieren velocidad. |
| **SaaS**   | Bajo (solo datos)      | Microsoft 365           | Empresas que necesitan apps listas. |

---

## **🚀 Consejos para el Examen AZ-900**  
1. **Memoriza el modelo de responsabilidad compartida.**  
2. **Identifica escenarios:**  
   - ¿Necesitas control total? → **IaaS**.  
   - ¿Quieres enfocarte en código? → **PaaS**.  
   - ¿Solo usar una app? → **SaaS**.  
3. **Practica con Free Tier:** Los laboratorios anteriores son clave para entender las diferencias.  

---

## **🎯 Conclusión**  

Entender IaaS, PaaS y SaaS es **fundamental para la certificación AZ-900**. Azure ofrece flexibilidad para cada necesidad, desde infraestructura personalizada (IaaS) hasta aplicaciones listas (SaaS).  
---  
¡A practicar en [Azure Free Tier](https://azure.microsoft.com/es-es/free/)! 🌟
