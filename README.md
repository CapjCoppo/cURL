# cURL

### **1. Introducción a cURL**
- **Objetivo**: Entender qué es cURL y sus casos de uso comunes.
  - ¿Qué es cURL? Herramienta de línea de comandos para transferir datos.
  - Casos de uso: APIs REST, descarga de archivos, pruebas de servidores, automatización.
  - Instalación:
    - Windows: Descargar desde [curl.se](https://curl.se) o usar WSL.
    - Linux/macOS: Usar el gestor de paquetes (`apt install curl`, `brew install curl`).

---

### **2. Comandos Básicos**
- **Objetivo**: Aprender a realizar peticiones HTTP básicas.
  - **GET Request**:
    ```bash
    curl https://jsonplaceholder.typicode.com/posts/1
    ```
  - **Guardar la respuesta en un archivo**:
    ```bash
    curl -o resultado.json https://ejemplo.com/api/datos
    ```
  - **Seguir redirecciones**:
    ```bash
    curl -L https://ejemplo.com
    ```
  - **Enviar parámetros en la URL**:
    ```bash
    curl "https://ejemplo.com/api?nombre=Juan&edad=25"
    ```

---

### **3. Headers y Métodos HTTP**
- **Objetivo**: Personalizar peticiones con headers y métodos.
  - **Especificar método HTTP** (POST, PUT, DELETE):
    ```bash
    curl -X POST https://ejemplo.com/api
    ```
  - **Enviar headers personalizados**:
    ```bash
    curl -H "Content-Type: application/json" -H "Authorization: Bearer token" https://ejemplo.com
    ```
  - **Ver los headers de la respuesta**:
    ```bash
    curl -i https://ejemplo.com
    ```

---

### **4. Envío de Datos (POST)**
- **Objetivo**: Aprender a enviar datos en formato JSON, formularios y archivos.
  - **Enviar JSON**:
    ```bash
    curl -X POST -H "Content-Type: application/json" -d '{"clave":"valor"}' https://ejemplo.com/api
    ```
  - **Enviar formulario**:
    ```bash
    curl -X POST -d "nombre=Juan" -d "email=juan@example.com" https://ejemplo.com/form
    ```
  - **Subir un archivo**:
    ```bash
    curl -F "file=@/ruta/archivo.txt" https://ejemplo.com/upload
    ```

---

### **5. Autenticación y Cookies**
- **Objetivo**: Manejar autenticación básica, tokens y cookies.
  - **Autenticación Básica**:
    ```bash
    curl -u usuario:contraseña https://ejemplo.com/protegido
    ```
  - **Usar cookies**:
    ```bash
    curl -b "cookie1=valor" https://ejemplo.com
    ```
  - **Guardar cookies en un archivo**:
    ```bash
    curl -c cookies.txt https://ejemplo.com/login
    curl -b cookies.txt https://ejemplo.com/dashboard
    ```

---

### **6. Protocolos Adicionales (FTP, SFTP)**
- **Objetivo**: Usar cURL con otros protocolos.
  - **Descargar un archivo via FTP**:
    ```bash
    curl -u usuario:contraseña -O ftp://ejemplo.com/archivo.txt
    ```
  - **Subir archivo via SFTP**:
    ```bash
    curl -T archivo.txt sftp://usuario@ejemplo.com/directorio/ --insecure
    ```

---

### **7. Opciones Avanzadas**
- **Objetivo**: Dominar funcionalidades avanzadas de cURL.
  - **Modo verbose** (para depuración):
    ```bash
    curl -v https://ejemplo.com
    ```
  - **Limitar velocidad de descarga**:
    ```bash
    curl --limit-rate 100K -O https://ejemplo.com/archivo-grande.zip
    ```
  - **Usar proxies**:
    ```bash
    curl -x http://proxy:puerto https://ejemplo.com
    ```
  - **Ignorar certificados SSL** (solo para pruebas):
    ```bash
    curl --insecure https://ejemplo.com
    ```

---

### **8. Automatización y Scripting**
- **Objetivo**: Integrar cURL en scripts y automatizar tareas.
  - **Ejemplo en Bash**:
    ```bash
    #!/bin/bash
    response=$(curl -s https://ejemplo.com/api)
    echo "Respuesta: $response"
    ```
  - **Usar variables de entorno para tokens**:
    ```bash
    curl -H "Authorization: Bearer $TOKEN" https://ejemplo.com/api
    ```
  - **Programar tareas con cron** (ejemplo de descarga diaria):
    ```bash
    0 2 * * * curl -O https://ejemplo.com/backup/diario.zip
    ```

---

### **9. Proyectos Prácticos**
- **Ejercicios para aplicar conocimientos**:
  1. Crear un script que consulte una API pública (e.g., OpenWeatherMap) y muestrar el clima.
  2. Automatizar la descarga de archivos de un servidor FTP.
  3. Simular un login en un sitio web y acceder a una página protegida usando cookies.
  4. Probar una API REST (GET, POST, PUT, DELETE) con autenticación JWT.

---

### **10. Recursos Adicionales**
- **Documentación Oficial**: [curl.se/docs](https://curl.se/docs/)
- **Libro**: "Everything curl" de Daniel Stenberg (gratis en [curl.se/book.html](https://curl.se/book.html)).
- **Herramientas Relacionadas**:
  - `jq` para procesar JSON en la terminal.
  - Postman o Insomnia para pruebas gráficas de APIs.
- **Comunidad**: Stack Overflow, GitHub, foros de desarrollo.

---

### **Consejos Finales**
- Practica con APIs públicas (e.g., [JSONPlaceholder](https://jsonplaceholder.typicode.com/), [GitHub API](https://docs.github.com/es/rest)).
- Usa `curl --help` o `man curl` para explorar opciones.
- Combina cURL con scripts en Bash/Python para automatizar flujos.

¡Éxito en tu aprendizaje! 🚀
