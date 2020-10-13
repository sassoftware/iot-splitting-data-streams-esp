# Executing the Splitter Examples in the Trial Environment

## Register for Free Trial

1.	Go to the [SAS Event Stream Processing](https://www.sas.com/en_us/software/event-stream-processing.html) home page.

2.	Click **Get Free Trial**.

3.	Follow the instructions…

## Log onto Trial Environment

Once registered, you will receive an e-mail message with a link to your environment in the SAS Cloud.

<img src='images/email.png'>

Click the provided link and proceed to log onto the environment.

## Download Files from GitHub

All files required to execute the ESP Router example are available in the [files](files) directory of this page. Download the following files:

- [basic_splitter1_input.csv](files/basic_splitter1_input.csv) – Input data for basic_splitter1 model
- [basic_splitter2_input.csv](files/basic_splitter2_input.csv) – Input data for basic_splitter2 model
- [complex_splitter1_input.csv](files/complex_splitter1_input.csv) – Input data for complex_splitter1 model
- [complex_splitter2_input.csv](files/complex_splitter2_input.csv) – Input data for complex_splitter2 model
- [basic_splitter1.xml](files/basic_splitter1.xml) – Model file for basic_splitter1
- [basic_splitter2.xml](files/basic_splitter2.xml) – Model file for basic_splitter2
- [complex_splitter1.xml](files/complex_splitter1.xml) – Model file for complex_splitter1
- [complex_splitter2.xml](files/complex_splitter2.xml) – Model file for complex_splitter2

## Upload Data

After you have successfully logged in, you can upload the files required by the models:

- [basic_splitter1_input.csv](files/basic_splitter1_input.csv) – Input data for basic_splitter1 model
- [basic_splitter2_input.csv](files/basic_splitter2_input.csv) – Input data for basic_splitter2 model
- [complex_splitter1_input.csv](files/complex_splitter1_input.csv) – Input data for complex_splitter1 model
- [complex_splitter2_input.csv](files/complex_splitter2_input.csv) – Input data for complex_splitter2 model
 
1.	On the left side, click **Data**.

    *The Data Management Screen appears.*

    <img src='images/data_management_125.png'>
    
2.	Click <img src='images/upload_button.png'>.

    *The Upload Files screen appears.*

    <img src='images/upload_files.png'>
    
3.	Click **browse** and use standard Windows techniques to select the files you want to upload. 
	
5.	Click **Close** to close the Upload Files window.

The files are automatically uploaded to your account’s Uploads directory. The path to the directory is:

~~~bash
/home/*your_email_address*/uploads
~~~

## Access SAS ESP Studio

1.	On the left side of the SAS Cloud screen, click **Apps**.

    *The Applications screen appears.*
	
3.	Click **SAS Event Stream Processing**.

    *The Choose Interface screen appears.*

3.	Click **SAS ESP Studio** to start the application.

## Upload Model to SAS ESP Studio

You need to upload the appropriate xml file for the model to SAS ESP Studio to access it there. There are four model files from which to choose:

- [basic_splitter1.xml](files/basic_splitter1.xml) – Model file for basic_splitter1
- [basic_splitter2.xml](files/basic_splitter2.xml) – Model file for basic_splitter2
- [complex_splitter1.xml](files/complex_splitter1.xml) – Model file for complex_splitter1
- [complex_splitter2.xml](files/complex_splitter2.xml) – Model file for complex_splitter2

1.	In the upper-right corner of SAS ESP Studio, click <img src='images/upload_icon.png'> to reveal the **More actions** menu and select **Upload projects**.

    *The Upload Projects screen appears.*

    <img src='images/upload_project.png'>
    
2.	Click <img src='images/add_icon.png'>.

3.	Navigate to the xml file that contains the model that you want to upload and click **Open**.

4.	Click **Upload**. The file is uploaded, and the Upload Projects window displays the file, project name, and a green checkmark if the upload was successful.

5.	Click **Close** to close the **Upload Projects** window. The model appears using the Project Name specified in the model.

6.	Double-click the project to open it.

## Edit Input Data Connectors and Subscriber Connectors

You must edit any Input Data (Publisher) Connectors and Subscriber Connectors to specify the path to the files you uploaded and any files that will be created. The path includes the `/home/*your_email_address*/uploads` directory to which you uploaded files.

To determine if a window includes a connector, look for the <img src='images/connector_icon.png'> icon. If the icon appears on the left of a window it indicates an Input Data (Publisher) Connector exists. If the icon appears on the right of a window it indicates a Subscriber Connector.

The following table lists the four models and the windows that contain Input Data (Publisher) Connectors:

| Model | Window |
| ------ | ------ |
| basic_splitter1.xml | Source1 |
| basic_splitter2.xml | Source1 |
| complex_splitter1.xml | Source1 |
| complex_splitter2.xml | Source1 |

The following table lists the four models and the windows that contain Subscriber Connectors:

| Model | Window |
| ------ | ------ |
| basic_splitter1.xml | Compute1 |
| | Compute2 |
| | Compute3 |
| basic_splitter2.xml | Compute1 |
| | Compute2 |
| complex_splitter1.xml | Compute2 |
| | Compute3 |
| | Compute4 |
| complex_splitter2.xml | Compute2 |
| | Compute3 |

### Editing Input Data (Publisher) Connectors

Use the following steps to edit an Input Data (Publisher) Connector:

1.	Ensure the Properties are displayed on the right side of the screen.

2.	Click the window containing the Input Data (Publisher) Connector to select it.

3.	Expand the **Input Data (Publisher) Connectors** section.

4.	Select the connector and click <img src='images/edit_icon.png'> to open the **Connector Configuration** window.

    <img src='images/connector.png'>
    
5.	Edit the **Fsname** field to include the full path to the file.

6.	Click **OK** to close the **Connector Configuration** window.	

### Editing Subscriber Connectors

Use the following steps to edit a Subscriber Connector:

1.	Ensure the Properties are displayed on the right side of the screen.

2.	Click the window containing the Subscriber Connector to select it.

3.	Expand the **Subscriber Connectors** section.

4.	Select the connector and click <img src='images/edit_icon.png'> to open the **Connector Configuration** window.

    <img src='images/connector2.png'>
 
5.	Edit the **Fsname** field to include the full path to the file.

6.	Click **OK** to close the **Connector Configuration** window.	


## Testing the Model in SAS ESP Studio

SAS ESP Studio allows you to test a model.

1.	Ensure the project is open in ESP Studio.
    
2.	If necessary, click <img src='images/save_icon.png'> to save your changes. A project must be saved before it can be tested.

3.	Click <img src='images/enter_test_mode_button.png'> to open the **Test** window.

    <img src='images/test_window.png'>
    
4.	Click <img src='images/run_test_button.png'> to begin the test. The model will start on the server and the connectors will begin publishing and subscribing.
    
    <img src='images/testing.png'>

5.	Click any of the tabs to view the output from that window.

6.	To stop the test, click <img src='images/stop_button.png'>.

## Enable Logging on the SAS ESP Server

If you receive an error or the connectors cannot start when you test a model, you can enable logging on the SAS ESP Server to view the messages from the log.

1.	Click **ESP Servers** to display the ESP Servers screen.

2.	Click the ESP Trial Server entry to select it, and then click <img src='images/properties.png'> to open the properties for the server.

3.	Click **Enable logging on the ESP server** and then click **OK**.

4.	Run the test again with logging enabled.

## Executing the Model on the ESP Server

You can use the ESP Servers feature of SAS ESP Studio to execute a model on the ESP XML Server.

1.	Click **ESP Servers** to display the ESP Servers screen.

    <img src='images/esp_servers.png'>
    
2.	On the bottom half of the screen, click <img src='images/load_project_icon.png'>  (Load project) to display the Load Projects screen.

    <img src='images/load_project.png'>
    
3.	Select the appropriate project and click **Load**.

    *The project appears under Projects on the ESP Servers screen.*

4.	Click the project to select it, and then click <img src='images/start_button.png'> to start the project on the SAS ESP Server. The status indicator turns green.

## View Model Output Using SAS ESP Streamviewer

You can use SAS ESP Streamviewer to subscribe to windows in the model and view the output.

1.	Ensure the model is running on the SAS ESP Server.

2.	On the left side of the SAS Cloud screen, click **Apps**.

    *The Applications screen appears.*
	
4.	Click **SAS Event Stream Processing**.

    *The Choose Interface screen appears.*

4.	Click **SAS ESP Streamviewer** to start the application.

    *SAS ESP Streamviewer starts, and a new dashboard appears.*

    <img src='images/esp_streamviewer.png'>
    
5.	Click <img src='images/model_viewer_icon.png'> to open the ESP Model Viewer.

6.	Select the appropriate window and click <img src='images/updating_subscriber_icon.png'> to add an updating subscriber to the dashboard. Click **Close** to close the ESP Model Viewer.

7.	You can click <img src='images/edit_chart_icon.png'> In the upper-right corner of the table and then select **Edit** to change the display type to a chart or graph.