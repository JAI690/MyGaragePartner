
# Documentación: Chatbot para MyGarage

## **Descripción general**
El chatbot para MyGarage es un componente avanzado diseñado para mejorar la interacción y eficiencia de los asesores de venta en la búsqueda y gestión de productos. Este chatbot se integra con el ecosistema existente de MyGarage y permite procesar solicitudes en lenguaje natural para realizar tareas como:

- Identificar piezas requeridas.
- Sugerir equivalencias entre productos.
- Generar cotizaciones.
- Consultar disponibilidad y ubicación en el almacén.
- Ofrecer recomendaciones basadas en conocimiento mecánico.

## **Objetivo**
Automatizar y simplificar las tareas de los asesores de venta mediante una herramienta intuitiva que:
- Entienda el lenguaje natural.
- Ofrezca respuestas precisas y contextualizadas.
- Se integre de manera fluida en la aplicación existente de MyGarage.

## **Audiencia**
El chatbot está diseñado exclusivamente para asesores de venta y no está destinado al uso directo por parte de clientes finales en esta etapa inicial.

## **Arquitectura del sistema**

### **Componentes principales**
1. **Microservicio del chatbot:**
   - Implementado en Python para aprovechar modelos avanzados como OpenAI GPT-4.
   - Arquitectura basada en FastAPI para manejar solicitudes HTTP.
   - Integración con DynamoDB para consultar productos y ubicaciones.

2. **Frontend:**
   - Componente React embebido en la aplicación MyGarage.
   - Interfaz visual que permite interacción en tiempo real con el chatbot.

3. **Base de datos:**
   - **Products:** Contiene información sobre los productos (nombre, descripción, etc.).
   - **Warehouse:** Proporciona detalles sobre la ubicación de los productos en el almacén.

### **Flujo de trabajo del chatbot**
1. **Entrada del usuario:**
   - Solicitudes en lenguaje natural (e.g., “Quiero balatas cerámicas para un Kia Rio 2018”).
   - Comandos específicos (e.g., “Cotiza esto: filtros de aceite para Toyota Corolla 2015”).

2. **Procesamiento del texto:**
   - Uso de modelos avanzados para extraer datos como:
     - Marca, modelo, y año.
     - Sistema y pieza requerida.
     - Condiciones especiales.

3. **Búsqueda de datos:**
   - Consultar la tabla `Products` para obtener información del producto.
   - Consultar la tabla `Warehouse` para verificar disponibilidad y ubicación.
   - Sugerir productos equivalentes en caso de no disponibilidad.

4. **Generación de respuesta:**
   - Respuestas en formato conversacional que incluyen:
     - Disponibilidad del producto.
     - Ubicación en el almacén.
     - Precio.
     - Sugerencias de alternativas.

5. **Registro de interacciones:**
   - Guardar consultas y resultados en una base de datos para métricas y análisis futuros.

6. **Feedback:**
   - Mecanismo para que los asesores evalúen la utilidad de las respuestas y mejoren el modelo basado en interacciones.

## **Tecnologías utilizadas**
- **Lenguaje:** Python (para el microservicio del chatbot).
- **Frameworks:** FastAPI para el backend del chatbot.
- **Modelo de IA:** OpenAI GPT-4 o similar para procesamiento de lenguaje natural.
- **Bases de datos:** DynamoDB (áreas: `Products` y `Warehouse`).
- **Frontend:** React.

## **Funcionalidades principales**
1. **Identificación de piezas:**
   - Extrae marca, modelo, año, pieza y condiciones especiales del texto del usuario.
2. **Sugerencias y equivalencias:**
   - Ofrece alternativas basadas en catálogos y equivalencias de productos.
3. **Ubicación y disponibilidad:**
   - Consulta la ubicación y disponibilidad del producto en el almacén.
4. **Generación de cotizaciones:**
   - Crea cotizaciones con los productos seleccionados.
5. **Conocimiento mecánico:**
   - Proporciona recomendaciones basadas en sistemas de vehículos y tipos de piezas.

## **Requisitos**
### **Backend del chatbot:**
- API REST desplegada como microservicio independiente.
- Integración con DynamoDB para búsqueda de productos y ubicaciones.

### **Frontend:**
- Componente de chat embebido en la aplicación MyGarage.
- Diseño responsivo y fácil de usar.

### **Base de datos:**
- Tablas `Products` y `Warehouse` configuradas para consultas.

## **Escenarios futuros**
- **Gestor de órdenes:** Permitir la creación y gestión de órdenes desde el chatbot.
- **Mantenimiento preventivo:** Sugerir servicios con base en el historial del cliente.
- **Interacción con clientes:** Evolucionar para interactuar directamente con clientes en tiempo real.

## **Próximos pasos**
1. Implementar el microservicio del chatbot como MVP.
2. Integrar procesamiento avanzado de texto (GPT-4).
3. Diseñar el componente de chat para el frontend.
4. Probar e iterar con base en el feedback de los asesores.

---
Este documento sirve como guía para el diseño e implementación del chatbot en MyGarage. Los siguientes pasos estarán enfocados en desarrollar un prototipo funcional y su integración con el ecosistema existente.
