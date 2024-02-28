
# Django REST Authentication Example

This is a simple project that shows how to implement user authentication using the Django REST Framework.

## Facility

1. Clone this repository to your local machine.
2. Make sure you have Python and Django installed on your system.
3. Install the project requirements by running `pip install -r requirements.txt`.
4. Run the migrations with the command `python manage.py migrate`.

## Use

1. Start the local server by running `python manage.py runserver`.
2. You can interact with the following endpoints:

   - `/api/login/`: Endpoint to log in.
   - `/api/register/`: Endpoint to register a new user.
   - `/api/profile/`: Endpoint to view the profile of the authenticated user.

## Endpoints

### `/api/login/`

- Method: POST
- Input parameters: `username`, `password`
- Successful response:
  ```
  {
      "token": "<authentication_token>",
      "user": {
          "id": <user_id>,
          "username": "<username>",
          "email": "<email>"
          ...
      }
  }
  ```
- Error response:
  ```
  {
      "error": "Invalid password"
  }
  ```
  
### `/api/register/`

- Method: POST
- Input parameters: `username`, `password`, `email` (other optional fields)
- Successful response: The same as in the login endpoint
- Error response: Details of validation errors
  
### `/api/profile/`

- Method: POST
- Input parameters: None (authentication is done using the token)
- Successful response: Authenticated user profile
- Error response: 401 Unauthorized if no valid token is provided
  
## Author

This project was developed by Joseandres Montesino as an example of an authentication implementation in the Django REST Framework.

## License

This project is under the MIT license. For details, see the [LICENSE](LICENSE) file.