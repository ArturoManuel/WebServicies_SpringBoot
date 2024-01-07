Este código pertenece a un servicio web Spring Boot diseñado para gestionar operaciones relacionadas con empleados en una base de datos MySQL. El servicio ofrece una API REST con varias endpoints que permiten realizar consultas y actualizaciones sobre la información de los empleados.

## Endpoints

1. **List Employees**
    - Endpoint: `GET /employees/listar`
    - Description: Returns a list of all employees in the database.
    - Example:
      ```bash
      curl -X GET http://localhost:8080/employees/listar
      ```
![image](https://github.com/ArturoManuel/WebServicies_SpringBoot/assets/90386913/6cb1588c-24a7-4499-98f8-018c40a88fe6)


2. **Search Employee**
    - Endpoint: `GET /employees/buscar?id={id}`
    - Description: Retrieves the details of a specific employee by their ID.
    - Example:
      ```bash
      curl -X GET http://localhost:8080/employees/buscar?id=100
      ```
![image](https://github.com/ArturoManuel/WebServicies_SpringBoot/assets/90386913/a342f9d9-90ea-449d-81e4-4f4e8a4514bb)


3. **Employees by Manager**
    - Endpoint: `GET /employees/byManager?managerId={managerId}`
    - Description: Lists all employees who report to a specified manager.
    - Example:
      ```bash
      curl -X GET http://localhost:8080/employees/byManager?managerId=100
      ```
![image](https://github.com/ArturoManuel/WebServicies_SpringBoot/assets/90386913/e78f8d1b-84f2-4931-a553-3d0927b87e17)


4. **Complete Employee Information**
    - Endpoint: `GET /employees/completeInfo?employeeId={employeeId}`
    - Description: Provides detailed information about an employee.
    - Example:
      ```bash
      curl -X GET http://localhost:8080/employees/completeInfo?employeeId=3
      ```

5. **Update Feedback**
    - Endpoint: `POST /employees/updateFeedback`
    - Description: Updates the feedback for an employee.
    - Example:
      ```bash
      curl -X POST -d "employeeId=4&feedback=Great job!" http://localhost:8080/employees/updateFeedback
      ```

6. **Update Meeting Status**
    - Endpoint: `POST /employees/updateMeeting`
    - Description: Updates the status of a meeting between an employee and their manager.
    - Example:
      ```bash
      curl -X POST -d "employeeId=5&managerId=3" http://localhost:8080/employees/updateMeeting
      ```


La clase EmployeeController es un controlador REST que utiliza EmployeesRepository para interactuar con la base de datos MySQL. EmployeesRepository es una interfaz que extiende JpaRepository, proporcionando métodos CRUD estándar junto con operaciones personalizadas definidas mediante anotaciones @Query.

El archivo de configuración de Spring Boot (generalmente application.properties o application.yml) contiene detalles de conexión a la base de datos, como la URL, el nombre de usuario y la contraseña, así como la configuración del puerto del servidor y la estrategia de nomenclatura física para Hibernate.
