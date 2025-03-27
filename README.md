# Currency Converter and Exchange Rate Tracker

## Overview

This project is a **Currency Converter and Exchange Rate Tracker** web application designed to help users convert currencies based on real-time exchange rates and track exchange rate fluctuations over time. The app leverages the **ExchangeRate-API** to fetch live exchange rates and provide historical data. It features a simple and intuitive user interface where users can select base and target currencies, input an amount, and view the converted value.

Additionally, this application is deployed on multiple web servers (Web01 and Web02) using a load balancer to ensure high availability and scalability.

## Features

- **Currency Conversion**: Convert an amount from one currency to another using real-time exchange rates.
- **Live Exchange Rate Tracking**: Fetch live exchange rates for multiple currencies.
- **Historical Data**: View historical exchange rate data over a specified period.
- **User Interface**: A user-friendly interface built using HTML, CSS, and JavaScript to interact with the application.

## Technologies Used

- **Backend**: Node.js with Express.js
- **API**: ExchangeRate-API (for real-time and historical exchange rate data)
- **Frontend**: HTML, CSS, JavaScript
- **Deployment**: PM2 (for process management) and Load Balancer for traffic distribution

## Prerequisites

Before running the app locally or on a server, make sure you have the following:

- Node.js and npm installed
- Access to the ExchangeRate-API (or any other external currency conversion API)
- PM2 (for production environment process management)

## Installation

### 1. Clone the repository

```bash
git clone https://github.com/SLICKMAN-TYRUS/currency-converter-app.git
cd currency-converter-app

2. Install dependencies
Run the following command to install the required dependencies:

bash
Copy code
npm install
3. Set up API keys
You will need to acquire an API key from ExchangeRate-API (or any other API you are using) and store it in the .env file or pass it as an environment variable. Ensure that the key is securely handled.

4. Run the app locally
Start the app locally using the following command:

bash
Copy code
npm start
This will run the app on http://localhost:3000.

Deployment
Web Server Setup (Web01 & Web02)
Deploying on Web01:

IP: 3.82.210.241

On Web01, the application is running on port 3000. The app was set up using Node.js, and PM2 is used for process management.

To start the app on Web01, use the following command:

bash
Copy code
pm2 start server.js --name currency-converter
Deploying on Web02:

IP: 3.95.138.224

On Web02, the application is deployed similarly, also using PM2 for process management.

Start the app on Web02:

bash
Copy code
pm2 start server.js --name currency-converter
Load Balancer (Lb01)
A load balancer was configured to distribute incoming traffic across Web01 and Web02 to ensure optimal load distribution and high availability. The load balancer helps ensure the app remains responsive even when one of the servers is down or under heavy load.

Load Balancer IP: [IP address of your Load Balancer]

Traffic Distribution: The load balancer alternates requests between Web01 (3.82.210.241) and Web02 (3.95.138.224) to ensure seamless operation.

To test the load balancer setup, navigate to the IP address of the load balancer in your browser, and the app should load regardless of whether it's handled by Web01 or Web02.

Testing the App
1. Testing Locally
Once you have the app running locally:

Visit http://localhost:3000 to test the currency conversion functionality.

Input an amount, select the base and target currencies, and check if the app correctly converts the value.

Check for historical data retrieval and proper error handling in case of API failure.

2. Testing on Web Servers
After deployment, you can test the app on the web servers:

Web01: Visit http://3.82.210.241:3000 to test the app hosted on Web01.

Web02: Visit http://3.95.138.224:3000 to test the app hosted on Web02.

3. Testing the Load Balancer
Test the load balancer by visiting the Load Balancer IP and ensure the app is accessible, with traffic being distributed between Web01 and Web02.

Troubleshooting
PM2 Issues: If the app isn't running properly on Web01 or Web02, check the logs for error messages:

bash
Copy code
pm2 logs currency-converter
API Failures: Ensure that your API key is correctly configured. If you encounter issues, check the API provider's status page or console for any service outages.

Server Down: If one of the web servers is down, the load balancer will direct traffic to the other server.

Credits
ExchangeRate-API: Used for fetching real-time and historical exchange rate data.

PM2: For process management and ensuring the app runs continuously.

Node.js & Express: For creating the server-side application.

Challenges
API Key Management: Securely handling the API keys and making sure they're not exposed to the public.

Load Balancer Configuration: Setting up the load balancer to correctly distribute traffic was a challenge, but it ensures the app can handle high traffic loads.

Testing: Ensuring everything works correctly across different servers and maintaining a seamless user experience was critical.

Demo Video
A short demo video has been included, showcasing how the app functions locally and through the load balancer.

This README provides a detailed walkthrough of the Currency Converter and Exchange Rate Tracker project, from setup and deployment to troubleshooting. Feel free to reach out with any questions or issues you encounter!

vbnet
Copy code

This should cover the entirety of the project with detailed steps on setup, deployment, and testing. Let me know if you'd like any further modifications!





