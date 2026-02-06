# 🔔 Automatización de alertas de backups – Veeam

## 📌 Descripción
Proyecto de automatización diseñado para procesar alertas provenientes de
Veeam Backup & Replication, con el objetivo de detectar fallos reales y
warnings persistentes, reduciendo el ruido operativo y mejorando la respuesta
ante incidentes de backup.

La solución evita alertar de forma repetitiva por eventos transitorios y
prioriza únicamente los casos que requieren acción.

---

## 🎯 Problema
En entornos productivos con múltiples jobs de backup es común encontrar:

- Gran volumen de correos automáticos
- Warnings que se repiten día tras día sin seguimiento
- Dificultad para diferenciar errores críticos de eventos menores
- Riesgo de pasar por alto fallos reales (alert fatigue)

---

## ✅ Solución implementada
Se desarrolló un flujo de automatización que:

- Captura alertas enviadas por Veeam vía correo electrónico
- Analiza el asunto y el contenido del mensaje
- Clasifica el estado del backup (Success / Warning / Error)
- Detecta warnings persistentes entre ejecuciones consecutivas
- Registra el estado histórico del job
- Permite escalar solo cuando corresponde

---

## ⚙️ Tecnologías utilizadas
- Veeam Backup & Replication
- Microsoft Power Automate
- SharePoint Online (almacenamiento de estado)
- Email (buzón compartido)
- Expresiones y lógica condicional

---

## 🧠 Lógica de funcionamiento (alto nivel)

1. Veeam envía alertas por correo ante cada ejecución
2. Power Automate detecta nuevos correos del remitente configurado
3. Se extrae el nombre del job y el estado del backup
4. Se consulta el histórico del job
5. Se evalúa si el warning es nuevo o persistente
6. Se actualiza el registro y se decide si notificar o no

---
