# Installing Pentaho Data Integration (PDI) Community Edition

Pentaho Data Integration (PDI) is a powerful open-source ETL (Extract, Transform, Load) tool that allows you to extract data from various sources, transform it, and load it into different destinations.

This guide will walk you through the installation process for PDI on Windows, Mac, and Linux.

## Prerequisites

Before you begin, ensure you have the following prerequisites:

- Java Runtime Environment (JRE) 8 or higher installed.
- Go to the official Java Website: [https://www.oracle.com/id/java/technologies/downloads/#java17](https://www.oracle.com/id/java/technologies/downloads/#java17)

## Installation

### Windows

1. **Download Pentaho Data Integration**:
   - Go to the official Pentaho website: [https://www.hitachivantara.com/en-us/products/pentaho-platform/data-integration-analytics/pentaho-community-edition.html](https://www.hitachivantara.com/en-us/products/pentaho-platform/data-integration-analytics/pentaho-community-edition.html)
   - Download the Windows version of PDI (usually a .zip or .exe file).

2. **Install PDI**:
   - Extract the downloaded zip file to a folder of your choice.
   - Run as administrator `spoon.bat` located in the PDI folder to start the PDI client.

### Mac

1. **Download Pentaho Data Integration**:
   - Go to the official Pentaho website: [https://www.hitachivantara.com/en-us/products/pentaho-platform/data-integration-analytics/pentaho-community-edition.html](https://www.hitachivantara.com/en-us/products/pentaho-platform/data-integration-analytics/pentaho-community-edition.html)
   - Download the macOS version of PDI (usually a .tar.gz file).

2. **Install PDI**:
   - Extract the downloaded tar.gz file to a directory of your choice.
   - Open a Terminal window.
   - Navigate to the PDI folder using the `cd` command.
   - Run the PDI client using the command: `./spoon.sh`.

### Linux

1. **Download Pentaho Data Integration**:
   - Go to the official Pentaho website: [https://www.hitachivantara.com/en-us/products/pentaho-platform/data-integration-analytics/pentaho-community-edition.html](https://www.hitachivantara.com/en-us/products/pentaho-platform/data-integration-analytics/pentaho-community-edition.html)
   - Download the Linux version of PDI (usually a .tar.gz file).

2. **Install PDI**:
   - Extract the downloaded tar.gz file to a directory of your choice.
   - Open a Terminal window.
   - Navigate to the PDI folder using the `cd` command.
   - Run the PDI client using the command: `./spoon.sh`.

## Configuration

After you have successfully installed PDI, you can configure it according to your needs. You can create and run ETL transformations using the PDI client (Spoon).

## Getting Started

Refer to the Pentaho documentation or online tutorials to get started with creating and running ETL jobs using Pentaho Data Integration.

## Troubleshooting

If you encounter any issues during installation or usage, refer to the Pentaho community forums or online resources for troubleshooting guidance.

## Additional Resources

- Pentaho Community Forums: [https://community.hitachivantara.com/community/products-and-solutions/pentaho](https://community.hitachivantara.com/community/products-and-solutions/pentaho)
- Pentaho Documentation: [https://help.pentaho.com](https://help.pentaho.com)

That's it! You should now have Pentaho Data Integration installed and ready to use on your Windows, Mac, or Linux machine.

# Creating Transformation and Job in Pentaho Data Integration (PDI) Community Edition
Pentaho is a popular open-source business intelligence (BI) and data integration tool that allows you to perform various ETL (Extract, Transform, Load) operations. To create transformations and jobs in Pentaho, you can follow these general steps:

1. **Install Pentaho Data Integration (PDI)**:
   - Download and install Pentaho Data Integration, which is also known as Kettle. You can find the installation files on the Pentaho website.

2. **Launch Pentaho Data Integration**:
   - Once installed, open Pentaho Data Integration (Spoon), the graphical interface for designing ETL processes.

3. **Creating a Transformation**:

   A transformation in Pentaho is a sequence of steps that extract, transform, and load data from source to destination. To create a transformation:

   - Open Spoon.
   - Click on "File" and select "New" -> "Transformation."

4. **Designing a Transformation**:

   - Add input sources (e.g., databases, CSV files) using "Input" steps.
   - Perform transformations using various transformation steps (e.g., "Filter Rows," "Sort Rows," "Calculator," etc.).
   - Connect steps to define the flow of data.
   - Configure each step by double-clicking it and providing the necessary settings and transformations.

5. **Saving a Transformation**:

   - Once you have designed your transformation, save it with a .ktr extension.

6. **Creating a Job**:

   A job in Pentaho is used to orchestrate and execute one or more transformations or tasks. To create a job:

   - Open Spoon.
   - Click on "File" and select "New" -> "Job."

7. **Designing a Job**:

   - Add transformations or tasks to the job by dragging them from the left pane into the job canvas.
   - Connect the transformations/tasks to define the execution flow.

8. **Configuring Job Entries**:

   - Double-click each transformation or task to configure its settings. For transformations, specify the path to the transformation file (.ktr).

9. **Saving a Job**:

   - Save the job with a .kjb extension.

10. **Running a Transformation or Job**:

    - You can execute a transformation or job by right-clicking on it and selecting "Run."

11. **Scheduling and Automating**:

    - Pentaho also provides options to schedule and automate the execution of jobs using the Pentaho Server or other scheduling tools.

12. **Monitoring and Debugging**:

    - Use Pentaho's monitoring and logging features to track the progress and identify issues in your transformations and jobs.

13. **Deployment**:

    - When you're satisfied with your transformations and jobs, you can deploy them to a production environment.

Remember that the specific steps and options may vary depending on the version of Pentaho you are using. Pentaho provides comprehensive documentation and tutorials to help you learn and use the tool effectively. Make sure to refer to the official Pentaho documentation and resources for detailed guidance on specific tasks and features.

# Scheduling a Pentaho Data Integration (PDI) Job

**1. Export Your PDI Job:**

   Ensure your PDI job is saved as a .kjb file within Pentaho Data Integration.

**2. Windows Task Scheduler:**

   If you're using Windows, schedule your PDI job with Windows Task Scheduler:

   - Open Windows Task Scheduler.
   - Click on "Create Basic Task" or "Create Task."
   - Set up the task and choose "Start a program" in the "Action" step.
   - In "Program/script," specify the path to the PDI kitchen or pan executable (e.g., `kitchen.bat` for Windows).
   - In "Add arguments," provide `/file:"C:\path\to\your\job.kjb"`.
   - Complete the wizard to schedule the task.

**3. Linux using Cron:**

   If you're using Linux, schedule your PDI job using the cron utility:

   - Open your terminal and run `crontab -e`.
   - Add a new line to schedule your job, e.g.:

     ```shell
     0 2 * * * /path/to/kitchen.sh /file:/path/to/your/job.kjb >> /path/to/logfile.log 2>&1
     ```

   - Adjust the schedule as needed.
   - Save and exit the editor.

Now, your PDI job will run automatically at the scheduled times on both Windows and Linux systems. Ensure you have the necessary permissions, and verify that the paths to the PDI executables, your job file, and any required scripts or batch files are correctly specified in the scheduled task or cron job. Additionally, monitor the logs for successful execution and troubleshoot any issues that may arise.
