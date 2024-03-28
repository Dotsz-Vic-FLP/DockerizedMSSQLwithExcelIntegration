
# Dockerized MSSQL with Excel Integration

## Introduction

This project aims to demonstrate the process of setting up a Microsoft SQL Server (MSSQL) instance using Docker, deploying a database, connecting it to Microsoft Excel, and running SQL queries. This setup is may be used for data analysis, allowing users to leverage containerized databases. 

## Prerequisites

-   Docker Desktop installed on your machine.
-   SQL Management Tool (We're using [SQL Server Management Studio](https://learn.microsoft.com/en-us/sql/ssms/download-sql-server-management-studio-ssms?view=sql-server-ver16#download-ssms), in this demo)
-   Microsoft Excel installed.
-   Basic knowledge of SQL queries.
-   Access to a terminal or command prompt.

## Tools Used

-   **Docker**: For creating and managing the MSSQL server container.
-   **Microsoft SQL Server (MSSQL)**: The database server used for storing and managing data.
-   **Microsoft Excel**: For data analysis and visualization, connected to the MSSQL database.

## Step 1: Setting Up the MSSQL Docker Container

### Starting the MSSQL Server Instance

1.  **Pull the MSSQL Server Docker Image**:
       
    `docker pull mcr.microsoft.com/mssql/server:2022-latest` 
    
2.  **Run the MSSQL Container**:
    
    -   Replace `<YourPassword>` with a strong password.

    `docker run -e "ACCEPT_EULA=Y" -e "SA_PASSWORD=<YourPassword>" -p 1433:1433 --name sqlserver mcr.microsoft.com/mssql/server:2022-latest` 
    
3.  **Verify Container is Running**:

    `docker ps` 
    
    -   Look for the `sqlserver` container in the list.

### Accessing the MSSQL Server

-   Use any SQL client to connect to the database using `localhost,1433` and the credentials provided during the container setup.

## Step 2: Deploying the Database

1.  **Access the SQL Server**: Connect using your preferred SQL management tool.
2.  **Create or Restore Database**:
    -   For a new database: `CREATE DATABASE MyDatabase;`
    -   For restoring from a backup, follow the specific instructions for your SQL management tool.

## Step 3: Connecting Excel to the MSSQL Database

1.  **Open Excel** and navigate to the **Data** tab.
2.  **Get Data > From Database > From SQL Server Database**.
3.  **Enter the Server Name**: `localhost,1433` and use the database credentials to log in.
4.  **Select the Table** or view you wish to import.


## Best Practices and Troubleshooting

-   **Security**: Always use strong, unique passwords for database access.
-   **Data Backup**: Regularly back up your SQL databases to prevent data loss.
-   **Troubleshooting**: If you encounter connection issues, ensure Docker is running and check the firewall settings to allow traffic on port 1433.

## Conclusion

This guide provides a foundation for integrating MSSQL with Excel using Docker, facilitating sophisticated data analysis workflows. By following these steps, users can efficiently manage and analyze data across platforms.

## References

-   [Docker Official Documentation](https://docs.docker.com/)
-   [MSSQL Docker Image Documentation](https://docs.microsoft.com/en-us/sql/linux/sql-server-linux-setup-docker)
-   [Microsoft Excel](https://support.microsoft.com/en-us/excel)
-   [SQL Server Management Studio](https://learn.microsoft.com/en-us/sql/ssms/download-sql-server-management-studio-ssms?view=sql-server-ver16#download-ssms)