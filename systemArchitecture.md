# PicckR System Architecture  


## Overview
PicckR is a delivery platform that connects senders, riders, and businesses in one system.  
It helps users create orders, track deliveries in real time, and make secure payments — all in one app.  


The system is built in three main parts:
1. **Frontend** – what users see and interact with  
2. **Backend** – the main engine that runs the logic  
3. **Database & Services** – where data is stored and updated  


## Frontend
- **Technology:** React (for website) and React Native (for mobile app on iOS and Android)  


- **Purpose:** To let users and riders interact with the platform.  


- **Main Features:**
  - Create and manage delivery orders  
  - Track rider location in real time  
  - Make and confirm payments  
  - View delivery history and wallet balance  


- **How it connects:**  
  The frontend sends and receives information from the backend using **APIs** (for data) and WebSocket/Firebase (for live tracking updates).  


## Backend
- **Technology:** NestJS (built on Node.js)  
- **Purpose:** This is the brain of PicckR — it handles everything that happens behind the scenes.  


- **What it does:**
  - Handles sign-up, login, and user accounts  
  - Creates, updates, and manages delivery orders  
  - Sends notifications to riders and users through Firebase  
  - Connects with Flutterwave and Paystack to handle payments  
  - Keeps track of wallet balances and refunds  


- **How it communicates:**  
  - The frontend sends requests (like “create order” or “track package”) to the backend.  
  - The backend checks, processes, and sends back the correct response.  




## Database & Services
- **Main Database:** PostgreSQL  
  - Stores users, orders, riders, payments, and delivery details.  
  - Keeps records safe and well organized.  
- **Realtime Tracking:**
  - Firebase Used for sending instant notifications and live rider locations.


- **File Storage:** AWS (for storing delivery proofs, receipts, and rider documents).  
- **Payment Gateways:** (Flutterwave and Paystack for secure and easy transactions.  )




## How It Works (Step by Step)
1. The user creates a new order from the app.  
2. The backend saves the order in the database.  
3. Nearby riders receive a delivery alert through Firebase.  
4. Riders can bid their price for the delivery (if enabled).  
5. Once a rider accepts, the backend updates the order status.  
6. The user can track the rider’s movement in real time.  
7. When the item is delivered, the rider marks it complete.  
8. Payment is processed automatically through Flutterwave or Paystack, and both the rider and user get notifications.  



