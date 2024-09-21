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
Tours  
    Get All Tours  
        URL: /api/v1/tours  
        Method: GET
        Description: Fetches all available tours.
    Get a Single Tour
        URL: /api/v1/tours/:id
        Method: GET
        Description: Fetches a tour by its ID.
    Create a New Tour
        URL: /api/v1/tours
        Method: POST
        Access: Protected (Admin/Lead Guide)
        Description: Creates a new tour.
    Update a Tour
        URL: /api/v1/tours/:id
        Method: PATCH
        Access: Protected (Admin/Lead Guide)
        Description: Updates an existing tour.
    Delete a Tour
        URL: /api/v1/tours/:id
        Method: DELETE
        Access: Protected (Admin/Lead Guide)
        Description: Deletes a tour.
    Get Tour Stats
        URL: /api/v1/tours/tour-stats
        Method: GET
        Description: Get statistical insights on the tours.
    Monthly Plan
        URL: /api/v1/tours/monthly-plan/:year
        Method: GET
        Access: Protected (Admin/Lead Guide/Guide)
        Description: Get a monthly plan of tours for a specific year.

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
