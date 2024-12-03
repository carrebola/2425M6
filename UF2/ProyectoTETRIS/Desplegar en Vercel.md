# Despliegue en Vercel

![image](https://github.com/user-attachments/assets/d19f81a5-8e5c-4340-a740-36380bde4cd5)

Vercel es una plataforma en la nube que facilita el desarrollo, despliegue y escalado de aplicaciones web modernas, especialmente aquellas construidas con frameworks como Next.js, React y Vue.js. Su objetivo es simplificar el ciclo de vida del desarrollo web, permitiendo a los desarrolladores enfocarse en la creación de productos de calidad sin preocuparse por la infraestructura subyacente.

**Características principales de Vercel:**

- **Integración con sistemas de control de versiones:** Vercel se conecta fácilmente con repositorios en plataformas como GitHub, GitLab y Bitbucket, permitiendo despliegues automáticos cada vez que se realizan cambios en el código. 

- **Despliegue continuo y vistas previas:** Cada modificación en el código genera automáticamente una vista previa del despliegue, lo que facilita la revisión y prueba de cambios antes de su publicación en producción. 

- **Red de Entrega de Contenidos (CDN) global:** Vercel distribuye las aplicaciones a través de una CDN global, mejorando la velocidad y el rendimiento al acercar el contenido a los usuarios finales. 

- **Optimización automática:** La plataforma optimiza imágenes, código y otros recursos para asegurar una carga rápida en cualquier dispositivo. 

- **Funciones serverless:** Vercel permite la ejecución de funciones sin servidor, facilitando la creación de APIs y el manejo de procesos backend sin necesidad de gestionar servidores tradicionales. 

- **Escalabilidad automática:** Las aplicaciones desplegadas en Vercel escalan automáticamente según la demanda, garantizando disponibilidad y rendimiento óptimos sin configuraciones manuales. 

Para estudiantes de Desarrollo de Aplicaciones Web (DAW2), Vercel ofrece una solución integral que simplifica el proceso de despliegue y gestión de aplicaciones web, permitiendo centrarse en el desarrollo y la innovación sin las complejidades de la infraestructura. 

## Pasos para subir tu web a Vercel desde GitHub



**1. Preparar tu web en GitHub**

Asegúrate de que tu web funcione localmente: Si has creado una página web estática o una aplicación simple, verifica que todos los archivos (HTML, CSS, JS, etc.) estén en el repositorio y que funcionen correctamente. Puedes probar tu web en Codespaces para asegurarte de que todo esté bien.
Si usas un framework (Next.js, React, Vue.js, etc.), asegúrate de que la aplicación esté construida (build) correctamente.

**2. Crear una cuenta en Vercel**
Dirígete a vercel.com.
Regístrate usando tu cuenta de GitHub. Esto permitirá que Vercel acceda a tus repositorios y te permitirá desplegar tu web con facilidad.
Autoriza a Vercel para que pueda acceder a tus repositorios en GitHub.

**3. Conectar Vercel a tu repositorio de GitHub**
Una vez que estés dentro de tu cuenta en Vercel, haz clic en New Project (Nuevo proyecto).
Vercel te pedirá que selecciones un repositorio de GitHub. Elige el repositorio donde tienes tu web.
Haz clic en Import para comenzar el proceso de despliegue.

**4. Configurar tu proyecto en Vercel**
Después de importar el repositorio, Vercel detectará automáticamente el tipo de proyecto. Si es un proyecto estático (HTML, CSS, JS), no necesitarás hacer configuraciones adicionales. Para frameworks como Next.js o React, Vercel puede detectar automáticamente las configuraciones de build (construcción) necesarias.
Si tu proyecto requiere algún paso de construcción (por ejemplo, npm run build), Vercel lo detectará automáticamente o puedes configurarlo manualmente en los ajustes del proyecto.
En la sección de "Settings" (Configuraciones), puedes establecer las variables de entorno si tu aplicación lo requiere (aunque esto suele ser más común en proyectos más complejos).

**5. Desplegar tu web**
Haz clic en Deploy (Desplegar).
Vercel comenzará el proceso de despliegue. Si es una web estática, el proceso será rápido y Vercel generará una URL para que puedas acceder a tu sitio.

**6. Ver tu sitio en vivo**
Una vez que el despliegue haya finalizado, Vercel te proporcionará una URL única donde puedes acceder a tu web en vivo. Este dominio será algo como https://tuproject.vercel.app.
Si necesitas personalizar el dominio, puedes configurarlo en la pestaña Domains dentro del panel de control de Vercel.

**7. Habilitar despliegue continuo (opcional)**
Si haces cambios en tu repositorio de GitHub, Vercel puede desplegar automáticamente esos cambios. Para habilitar el despliegue continuo:
Cada vez que hagas un push a la rama principal o la rama que hayas configurado en GitHub, Vercel reconstruirá y desplegará automáticamente tu sitio web.
Esto te permite mantener tu sitio actualizado sin necesidad de realizar manualmente el despliegue.

