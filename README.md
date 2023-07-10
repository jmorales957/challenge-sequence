# Challenge Sequences

This is a web application project that allows you to track sequences. Below, I'll explain how you can run this application in your local environment.

## Configuration

Before starting the application, you need to configure an environment variable to set the API URL to be used. Make sure you have the URL of the API you want to connect to. Then, set the `API_URL` environment variable to the corresponding URL. For example:

API_URL=your_api_url


## Installing Dependencies

Before running the application, you need to install the necessary dependencies. Make sure you have [Yarn](https://yarnpkg.com/) installed on your machine. Open a terminal at the project's root directory and run the following command:

yarn install


This will install all the necessary dependencies for the application to function correctly.

## Running the Application

Once you have configured the API URL and installed the dependencies, you can run the application locally. To do this, execute the following command in the terminal:

yarn run dev


This will start the application on a local server, and you can access it through your web browser.

## Application Routes

The application offers the following routes:

- `/login`: This route allows you to log in to the application.
- `/sequences/create`: Use this route to create new sequences.
- `/sequences/total`: This route displays the sequence counter view.

You can access each route by entering the base URL of the application followed by the corresponding route. For example, if you are running the application at `http://localhost:3000`, you can access the login route using `http://localhost:3000/login`.

Enjoy using the application and keeping track of your sequences! If you have any questions or encounter any issues, feel free to refer to the additional documentation or contact us for assistance.
