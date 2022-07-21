run the below command to update the package list on your Ubuntu server.

     sudo apt update -y
     
Install the PostgreSQL packages by executing the below command. This command will also install the postgresql-contrib (additional Postgres features) and postgresql-client (Postgres CLI).

    sudo apt install -y postgresql postgresql-contrib postgresql-client     
    
 After the installation, verify the Postgres installation status by running the below command.

     sudo dpkg --status postgresql   
     

Once the installation completes, run the below systemctl command to start the PostgreSQL service.

    sudo systemctl start postgresql.service
     

Finally, verify the PostgreSQL status by running the below command.

    sudo systemctl status postgresql.service


log in to the PostgreSQL shell (psql) by running the below command.
      sudo -u postgres psql
      
.Run the following command at the prompt to initiate a password change. Provide a strong password of your choice and press Enter.

           \password      
           
Open the /etc/postgresql/12/main/pg_hba.conf file in nano for editing. This file is the main configuration file for PostgreSQL’s authentication methods.
            sudo nano /etc/postgresql/12/main/pg_hba.conf
            
            
 Find the line that reads as the below.

     # Database administrative login by Unix domain socket
      local   all             postgres                                                               peer                       
      
      
      
 
 Restart the PostgreSQL server for the changes to take effect.

          sudo systemctl restart postgresql
          
          
 Reconnect to the PostgreSQL server as the postgres user.

       sudo -u postgres psql         
       
       
       
 
      
      
      
      
