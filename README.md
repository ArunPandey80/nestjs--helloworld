

1. Set Up Your EC2 Instance
   Launch EC2 Instance:
      Go to the AWS Management Console.
      Navigate to the EC2 Dashboard.
      Click on “Launch Instance.”
      Choose an Amazon Machine Image (AMI). 
      Select an instance type. 
      Configure the instance details as needed.
      Add storage if necessary.
      Configure security groups to allow SSH (port 22) and HTTP/HTTPS (ports 80 and 443) access.
      Review and launch the instance. Download the key pair for SSH access.
   Connect to Your EC2 Instance:
      Connect your instance using EC2 connect.

2. Set Up the Environment
   Update Packages:
     sudo yum update -y - Installs Node.js and npm

   Install PM2:
     curl -sL https://rpm.nodesource.com/setup_16.x | sudo bash -
     sudo yum install -y nodejs

   Install Git:
    sudo npm install -g pm2

   Update Packages:
    sudo yum install git -y2. Set Up the Environment

   Install Node.js and npm:
    sudo yum update -y

   Install Git:
    sudo yum install git -y
     
3. Deploy Your NestJS Application
    Clone Your Repository:
      cd your-repo
   
    Install Dependencies:
      npm install
   
   Build the Application:
      npm run build
   
5. Configure and Start the Application
    Environment Variables:
      Create a .env file in the root of your project and configure your environment variables.
   
    Start the Application with PM2:
      pm2 start dist/main.js --name your-app-name
      pm2 save
      pm2 startup

6. Verify the Deployment
    Access Your Application:
      Open a web browser and navigate to http://your-ec2-public-dns.
      You should see your NestJS application running.
   
   Check Application Logs:
      pm2 logs
