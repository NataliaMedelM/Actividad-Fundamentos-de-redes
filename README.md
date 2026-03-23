# Actividad-Fundamentos-de-redes

# 🧩 1. ¿Qué es cada dispositivo?

## Tabla

| Concepto | Definición simple | Nivel técnico (breve) | Ejemplo real |
|----------|------------------|----------------------|--------------|
| Router | Dispositivo que conecta tu red con Internet. | Usa direcciones IP para enviar datos entre redes diferentes. | El router WiFi de tu casa. |
| Switch | Dispositivo que conecta varios equipos dentro de una red. | Usa direcciones MAC para enviar datos al equipo correcto. | Red de computadores en una oficina. |
| Hub | Dispositivo antiguo que conecta equipos pero envía todo a todos. | No filtra información, hace broadcast siempre. | Equipos viejos de red (ya no se usan). |

## 👉 Regla
- Máximo 3 líneas por definición  
- Debe poder explicarse a alguien sin conocimientos técnicos  

## 📌 Conceptos
- **Dirección IP:** Identificador único de un dispositivo en una red  
- **Dirección MAC:** Identificador físico único de una tarjeta de red  
- **Broadcast:** Envío de información a todos los dispositivos de la red  

---

# ⚙️ 2. ¿Cómo funciona realmente?

## 📡 ¿Qué hace el router con los paquetes de datos?
El router recibe paquetes con una dirección IP destino y decide por dónde enviarlos hacia otra red (como Internet). También puede cambiar la IP privada por una pública para que puedas navegar.

## 🔀 ¿Cómo decide un switch a dónde enviar la información?
El switch mira la dirección MAC del destino y usa una tabla interna para enviar los datos solo al dispositivo correcto. Si no sabe, los envía a todos (broadcast).

## 📢 ¿Por qué el hub es considerado obsoleto?
Porque envía toda la información a todos los dispositivos (broadcast), lo que genera lentitud, colisiones y poca seguridad. No es eficiente.

## 👉 Tip
- IP  
- MAC  
- Broadcast  

---

# 💻 3. Conexión directa con desarrollo (CLAVE)

## 🌐 ¿Qué rol cumple el router cuando haces una petición a una API?

```js
fetch("https://api.miapp.com")
```

Cuando haces una petición como esta, el router envía esa solicitud desde tu red hacia Internet, permitiendo que llegue al servidor de la API.

## 🏢 ¿Por qué un switch es importante en un backend o data center?
Porque conecta servidores y permite que se comuniquen rápido y sin interferencias. Evita que toda la red se sature.

## 🚨 ¿Qué problemas de red podrían afectar tu aplicación aunque el código esté “correcto”?

- Internet caído → la app no carga  
- DNS lento → demora en encontrar el servidor  
- Alta latencia → respuestas lentas  
- Pérdida de paquetes → errores en peticiones  
- Fallos de red interna → servicios no se conectan  

👉 Aquí deben pensar como developers, no como técnicos de redes.

---

# 🌍 4. Caso práctico real

## Escenario
> “Tu aplicación está en producción, pero los usuarios no pueden acceder.”

## 📡 ¿Podría ser problema de router? ¿por qué?
Sí, porque si el router falla o está mal configurado, la aplicación no puede salir a Internet y nadie puede acceder.

## 🔀 ¿Podría ser problema de switch? ¿por qué?
Sí, porque si el switch falla, los servidores no pueden comunicarse entre sí (por ejemplo, backend con base de datos).

## 🧠 ¿Cómo distinguir si es problema de red o de código?

- Si no hay conexión → problema de red  
- Si hay errores como “500” → problema de código  
- Si todo está lento → puede ser red  
- Revisar logs ayuda a identificar el problema  

---

# 🧪 5. Analogía obligatoria

## Primera analogía
- Router = Oficina de correos entre ciudades  
- Switch = Recepcionista que sabe a quién entregar cada mensaje  
- Hub = Persona que grita el mensaje a todos  

## Segunda analogía (mejorada)
- Router = Guardia de frontera entre países  
  Decide a qué país enviar a cada persona según su destino  

- Switch = Conserje de un edificio  
  Sabe exactamente en qué departamento vive cada persona y la dirige directo ahí  

- Hub = Persona que reparte cartas tirándolas en todos los departamentos  
  No sabe quién es el destinatario, así que todos reciben todo  

---

# 🎤 Presentación

## 1. Diferencia clave
- Router conecta redes (usa IP)  
- Switch conecta dispositivos (usa MAC)  
- Hub envía todo a todos  

## 2. Ejemplo real en desarrollo
Cuando haces una petición a una API:
- Router → la envía a Internet  
- Switch → mueve datos dentro del servidor  

## 3. Analogía
- Router = correos  
- Switch = recepcionista  
- Hub = gritar a todos  
