# YinkaAjao_currency-converter
Project Title
Currency Converter Application

Description:
This project is a user-friendly currency converter application that fetches live exchange rates using the ExchangeRate API. Users can select their respective currency codes, input amounts, and convert currencies dynamically.

Deployment and Load Balancer Configuration

#### **1. Prerequisites**
- Access to `Web01`, `Web02`, and `Lb01` servers.
- Web server software (e.g., Apache/Nginx).
- SSH access and Git installed.

#### **2. Deployment Steps**
1. **Prepare the Application:**
   - Ensure the codebase is clean and ready for production
   - Remove sensitive data from the codebase and set up environment variables.
   - Test locally to confirm functionality.

2. **Deploy to Web Servers:**
   - SSH into `Web01` and `Web02`.
   - Clone the GitHub repository and move files to the web root.
   - Restart the web server and confirm the app is accessible via server IPs.

3. **Configure the Load Balancer:**
   - SSH into `Lb01`.
   - Install and configure HAProxy with the `roundrobin` algorithm:
     - Forward traffic to `Web01` and `Web02`.
   - Restart HAProxy and test by accessing the load balancer's IP.

#### **3. Testing**
- Access the app via the load balancer and confirm functionality.
- Refresh to verify traffic alternates between servers.
- Simulate high traffic and check performance.
- Test failover by stopping a server and ensuring the load balancer redirects traffic to the active one.
