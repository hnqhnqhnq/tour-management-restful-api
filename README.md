**Tour Management RESTful API**

*Project Overview*
This is a RESTful API for managing tours, users, and reviews, built using Node.js, Express, and MongoDB. The API supports CRUD operations for tours, user authentication, and review management.

*Setup Instructions*
1) Clone the Repository: Clone the project files to your local environment.
   
   ``
   git clone https://github.com/hnqhnqhnq/tour-management-restful-api.git
   cd tour-management-restful-api
   ``
   
2) Install Dependencies: Run the following command to install the required dependencies.
   
   ``
   npm install
   ``
   
3) Environment Variables: Create a config.env file in the root directory and define the following environment variables:
   
   ``
   NODE_ENV=development
   PORT=3000  
   DATABASE=<your-mongoDB-URI>  
   DATABASE_PASSWORD=<your-database-password>  
   JWT_SECRET=my-ultra-secure-and-ultra-long-secret  
   JWT_EXPIRES_IN=90d  
   JWT_COOKIE_EXPIRES_IN=90  
   EMAIL_USERNAME=<your-email-username>  
   EMAIL_PASSWORD=<your-email-password>  
   EMAIL_HOST=<your-email-host>  
   EMAIL_PORT=25  
   ``
   
6) Run the Application: Start the application in development mode using nodemon.
   
   ``
   npm run start:dev
   ``

*API Endpoints*  
Tours <br>

    Get All Tours  <br>
        URL: /api/v1/tours <br> 
        Method: GET<br>
        Description: Fetches all available tours.<br>
    Get a Single Tour<br>
        URL: /api/v1/tours/:id<br>
        Method: GET<br>
        Description: Fetches a tour by its ID.<br>
    Create a New Tour<br>
        URL: /api/v1/tours<br>
        Method: POST<br>
        Access: Protected (Admin/Lead Guide)<br>
        Description: Creates a new tour.<br>
    Update a Tour<br>
        URL: /api/v1/tours/:id<br>
        Method: PATCH<br>
        Access: Protected (Admin/Lead Guide)<br>
        Description: Updates an existing tour.<br>
    Delete a Tour<br>
        URL: /api/v1/tours/:id<br>
        Method: DELETE<br>
        Access: Protected (Admin/Lead Guide)<br>
        Description: Deletes a tour.<br>
    Get Tour Stats<br>
        URL: /api/v1/tours/tour-stats<br>
        Method: GET<br>
        Description: Get statistical insights on the tours.<br>
    Monthly Plan<br>
        URL: /api/v1/tours/monthly-plan/:year<br>
        Method: GET<br>
        Access: Protected (Admin/Lead Guide/Guide)<br>
        Description: Get a monthly plan of tours for a specific year.<br>

Users

    Sign Up
        URL: /api/v1/users/signup
        Method: POST
        Description: User registration.
    Login
        URL: /api/v1/users/login
        Method: POST
        Description: User login and authentication.
    Forgot Password
        URL: /api/v1/users/forgotPassword
        Method: POST
        Description: Requests a password reset.
    Reset Password
        URL: /api/v1/users/resetPassword/:token
        Method: PATCH
        Description: Resets the user's password using a token.
    Update Password
        URL: /api/v1/users/updateMyPassword
        Method: PATCH
        Description: Updates the user's password.
    Get User Profile
        URL: /api/v1/users/me
        Method: GET
        Description: Get details of the logged-in user.
    Update User Profile
        URL: /api/v1/users/updateMe
        Method: PATCH
        Description: Update the user's profile information.
    Delete User Profile
        URL: /api/v1/users/deleteMe
        Method: DELETE
        Description: Deletes the logged-in user's profile.

Reviews

    Get All Reviews
        URL: /api/v1/reviews
        Method: GET
        Description: Fetch all reviews.
    Create a Review
        URL: /api/v1/reviews
        Method: POST
        Access: Protected (Authenticated Users)
        Description: Create a new review.
