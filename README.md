
# Django REST Authentication Example

Este es un proyecto simple que muestra cómo implementar la autenticación de usuarios utilizando Django REST Framework.

## Instalación

1. Clona este repositorio en tu máquina local.
2. Asegúrate de tener Python y Django instalados en tu sistema.
3. Instala los requerimientos del proyecto ejecutando `pip install -r requirements.txt`.
4. Ejecuta las migraciones con el comando `python manage.py migrate`.

## Uso

1. Inicia el servidor local ejecutando `python manage.py runserver`.
2. Puedes interactuar con las siguientes endpoints:

   - `/api/login/`: Endpoint para iniciar sesión.
   - `/api/register/`: Endpoint para registrar un nuevo usuario.
   - `/api/profile/`: Endpoint para ver el perfil del usuario autenticado.

## Endpoints

### `/api/login/`

- Método: POST
- Parámetros de entrada: `username`, `password`
- Respuesta exitosa:
  ```
  {
      "token": "<token_de_autenticación>",
      "user": {
          "id": <id_del_usuario>,
          "username": "<nombre_de_usuario>",
          "email": "<correo_electrónico>"
          ...
      }
  }
  ```
- Respuesta de error: 
  ```
  {
      "error": "Invalid password"
  }
  ```
  
### `/api/register/`

- Método: POST
- Parámetros de entrada: `username`, `password`, `email` (otros campos opcionales)
- Respuesta exitosa: Lo mismo que en el endpoint de login
- Respuesta de error: Detalles de los errores de validación
  
### `/api/profile/`

- Método: POST
- Parámetros de entrada: Ninguno (la autenticación se realiza mediante el token)
- Respuesta exitosa: Perfil del usuario autenticado
- Respuesta de error: 401 Unauthorized si no se proporciona un token válido
  
## Autor

Este proyecto fue desarrollado por Joseandres Montesino como ejemplo de implementación de autenticación en Django REST Framework.

## Licencia

Este proyecto está bajo la licencia MIT. Para más detalles, consulta el archivo [LICENSE](LICENSE).


