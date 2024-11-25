# cashout
Descripción del Taller con Microservicios
Aplicación utilizando Spring Boot WebFlux y microservicios. El objetivo es implementar un sistema que permita a los usuarios realizar un "cashout" de productos. Parte del reto es implementar llamadas a otros microservicios desde dos de los endpoints principales.

Endpoints a Implementar
User Endpoints
Obtener Usuario por ID

Método: GET
URL: /users/{id}
Entrada: ID del usuario (Long)
Salida: Información del usuario (JSON)
{
  "id": 1,
  "name": "John Doe",
  "balance": 100.0
}

Crear Usuario
Método: POST
URL: /users
Entrada: Información del usuario (JSON)
{
  "name": "John Doe",
  "balance": 100.0
}
Salida: Información del usuario creado (JSON)
{
  "id": 1,
  "name": "John Doe",
  "balance": 100.0
}

Actualizar Balance del Usuario
Método: PUT
URL: /users/{id}/balance
Entrada: Monto a actualizar (JSON)
{
  "amount": 50.0
}
Salida: Información del usuario actualizado (JSON)
{
  "id": 1,
  "name": "John Doe",
  "balance": 150.0
}


Cashout Endpoints

Crear Cashout
Método: POST
URL: /cashouts
Entrada: Solicitud de cashout (JSON)
{
  "userId": 1,
  "amount": 50.0
}
Salida: Información del cashout creado (JSON)
{
  "id": 1,
  "userId": 1,
  "amount": 50.0
}
Nota: Este endpoint debe llamar a un microservicio externo que maneje los pagos para verificar y procesar el cashout.

Obtener Cashouts por ID de Usuario
Método: GET
URL: /cashouts/user/{userId}
Entrada: ID del usuario (Long)
Salida: Lista de cashouts (JSON)
[
  {
    "id": 1,
    "userId": 1,
    "amount": 50.0
  },
  {
    "id": 2,
    "userId": 1,
    "amount": 30.0
  }
]




