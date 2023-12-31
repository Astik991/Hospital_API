# Hospital_API
This is an Hospital API creted for Coding Ninjas Backend Skill Test.
How to Approach in the API :
1. First of all I'm hoping that you have Postman & MongoDB installed in your System. If not please download from the browser and install it.
2. Then Download the zip file of this project.
3. Then unzip it in the folder of choice.
4. Then install all the dependencies using below shortcut
```
npm install
```
5. Then run the API using below shortcut
```
npm start
```
6. Create a `.env` file in the root directory with the following environment variables: -
    - `PORT=6000`
    - `MONGODB_URI=<your_mongodb_uri>`
    - `JWT_SECRET=<your_jwt_secret>`
7. Start the server: `npm start`
8. Open the app in your web browser at `http://localhost:6000`

That's it! You should now have the CN Hospital API app up and running on your local machine.

> Note: In order to use the app's functionality, you will need to have Node.js and npm installed on your system. If you don't have them installed, you can download and install them from the official Node.js [website](https://nodejs.org/en/).
## Dependencies

CN Hospital API requires the following dependencies:

-   `dotenv` - Loads environment variables from a `.env` file
-   `express` - Web framework for Node.js
-   `jsonwebtoken` - Generates and verifies JSON web tokens (JWTs)
-   `mongoose` - ODM (Object-Document Mapping) library for MongoDB and Node.js
-   `express-session` - for managing user sessions in Express.js applications.
-   `passport` - Authentication middleware for Node.js
-   `passport-jwt` - Passport strategy for authenticating with a JSON Web Token (JWT)

9. Then open the Postman and check connecting the routes as follows:
    Note: All the routes written below must be added after the following address:
   ```
   http://localhost:6000
   ```
## API Routes

### Doctor
-   **POST** `/doctors/register` - Register a new doctor with a username and password.
-   **POST** `/doctors/login` - Login with a username and password to receive a JWT.
    > Note: All routes except for `/doctors/register` and `/doctors/login` require a valid JWT to be included in the Authorization header of the request. The JWT should have the format `Bearer <token>`.

### Patients
-   **POST** `/patients/register` - Register a new patient with a phone number. If the patient already exists, the existing patient info is returned.
-   **POST** `/patients/:id/create_report` - Create a new report for the patient with the given id, which includes the status and the date. The report is created by the doctor who is currently authenticated.
-   **GET** `/patients/:id/all_reports` - List all the reports for the patient with the given id, sorted from oldest to newest.

### Reports

-   **GET** `/reports/:status` - List all the reports for all patients with the given status. The reports are sorted from oldest to newest.

## Folder structure

The project has a scalable folder structure with separate models, controllers, and routes:

-   `controllers/`
    -   `doctor_controller.js`
    -   `patients_controller.js`
    -   `reports_controller.js`
-   `models/`
    -   `doctor.js`
    -   `patient.js`
    -   `report.js`
-   `routes/`
-   -   `index.js`
    -   `doctors.js`
    -   `patients.js`
    -   `reports.js`
-   `index.js`
   
