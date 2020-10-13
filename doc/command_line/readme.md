# Running the Splitter Examples from the Command Line

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
- [run_basic_splitter1.sh](files/run_basic_splitter1.sh) – Startup script to execute basic_splitter1 model
- [run_basic_splitter2.sh](files/run_basic_splitter2.sh) – Startup script to execute basic_splitter2 model
- [run_complex_splitter1.sh](files/run_complex_splitter1.sh) – Startup script to execute complex_splitter1 model
- [run_complex_splitter2.sh](files/run_complex_splitter2.sh) – Startup script to execute complex_splitter2 model

## Create Server Directory

Create a server directory for the project’s files. The following is an example of the command to create a directory:

~~~bash
mkdir /home/zestem/splitter
~~~

## Execute the Model

- [Executing the basic_splitter1 Model](https://gitlab.sas.com/IOT/tutorials/ESP-tutorials/splitting-data-streams-in-esp/-/blob/master/doc/readme.md#executing-the-basic_splitter1-model)
- [Executing the basic_splitter2 Model](https://gitlab.sas.com/IOT/tutorials/ESP-tutorials/splitting-data-streams-in-esp/-/blob/master/doc/readme.md#executing-the-basic_splitter2-model)
- [Executing the complex_splitter1 Model](https://gitlab.sas.com/IOT/tutorials/ESP-tutorials/splitting-data-streams-in-esp/-/blob/master/doc/readme.md#executing-the-complex_splitter1-model)
- [Executing the complex_splitter2 Model](https://gitlab.sas.com/IOT/tutorials/ESP-tutorials/splitting-data-streams-in-esp/-/blob/master/doc/readme.md#executing-the-complex_splitter2-model)


### Executing the basic_splitter1 Model

#### Edit Startup Script

You must edit the startup script, `run_basic_splitter1.sh` to specify the correct server directories on your system.

1.	Open `run_basic_splitter1.sh` with a text editor. The following is a listing of the file:

    ~~~bash
    # Copyright © 2020, SAS Institute Inc., Cary, NC, USA.  All Rights Reserved.
    # SPDX-License-Identifier: Apache-2.0

    # Register (DateFlux) ESP environment
    export DFESP_HOME=/opt/sas/viya/home/SASEventStreamProcessingEngine/6.2

    export PATH=$DFESP_HOME/bin:$PATH
    export LD_LIBRARY_PATH=$DFESP_HOME/lib:$DFESP_HOME/lib/tk:/opt/sas/viya/home/SASFoundation/sasexe:$DFESP_HOME/ssl/lib

    export PROJDIR=/home/zestem/splitter

    dfesp_xml_server -http 61002 -pubsub 61003 -model file:///home/zestem/splitter/basic_splitter1.xml
    ~~~
    
2.	Go to the `export PROJDIR=` line and edit the value to be the directory you created. The following is an example.

    ~~~bash
    export PROJDIR=/home/zestem/splitter
    ~~~
    
3.	Go to the last line (command to start XML Server) and edit the `-model` parameter to include the full path to the model’s xml file. Ensure there are the correct number of forward slashes (/) at the beginning of the filename. The following is an example:

    ~~~bash
    -model file:///home/zestem/splitter/basic_splitter1.xml
    ~~~
    
4.	Save your changes.
	
#### Upload Files

Upload the files for the basic_splitter1 example (`basic_splitter1_input.csv`, `basic_splitter1.xml`, and `run_basic_splitter1.sh`) to the directory you created. Change the permission of the `run_basic_splitter1.sh` startup script so it is executable. The following is an example of the command to do this:

~~~bash
chmod 777 /home/zestem/splitter/run_basic_splitter1.sh
~~~

#### Execute Project

1.	Change directories to the directory containing the files you uploaded. The following is an example:

    ~~~bash
	cd /home/zestem/splitter
	~~~
	
2.	Type the following to execute the startup script and start the basic_splitter1 model:

    ~~~bash
	./run_basic_splitter1.sh
	~~~

    The terminal should display information about the model executing on the ESP XML Server.
    
#### View Results

There are three files created in the directory you specified as the project directory:

- basic_splitter1_output1.csv – Created by Compute1 window. Can be viewed with Excel or a text editor.
- basic_splitter1_output2.csv – Created by Compute2 window. Can be viewed with Excel or a text editor.
- basic_splitter1_output3.csv – Created by Compute3 window. Can be viewed with Excel or a text editor.

### Executing the basic_splitter2 Model

#### Edit Startup Script

You must edit the startup script, `run_basic_splitter2.sh` to specify the correct server directories on your system.

1.	Open `run_basic_splitter2.sh` with a text editor. The following is a listing of the file:

    ~~~bash
    # Copyright © 2020, SAS Institute Inc., Cary, NC, USA.  All Rights Reserved.
    # SPDX-License-Identifier: Apache-2.0

    # Register (DateFlux) ESP environment
    export DFESP_HOME=/opt/sas/viya/home/SASEventStreamProcessingEngine/6.2

    export PATH=$DFESP_HOME/bin:$PATH
    export LD_LIBRARY_PATH=$DFESP_HOME/lib:$DFESP_HOME/lib/tk:/opt/sas/viya/home/SASFoundation/sasexe:$DFESP_HOME/ssl/lib

    export PROJDIR=/home/zestem/splitter

    dfesp_xml_server -http 61002 -pubsub 61003 -model file:///home/zestem/splitter/basic_splitter2.xml
    ~~~
    
2.	Go to the `export PROJDIR=` line and edit the value to be the directory you created. The following is an example.

    ~~~bash
    export PROJDIR=/home/zestem/splitter
    ~~~

3.	Go to the last line (command to start XML Server) and edit the `-model` parameter to include the full path to the model’s xml file. Ensure there are the correct number of forward slashes (/) at the beginning of the filename. The following is an example:

    ~~~bash
    -model file:///home/zestem/splitter/basic_splitter2.xml
    ~~~
    
4.	Save your changes.

#### Upload Files

Upload the files for the basic_splitter2 example (`basic_splitter2_input.csv`, `basic_splitter2.xml`, and `run_basic_splitter2.sh`) to the directory you created. Change the permission of the `run_basic_splitter2.sh` startup script so it is executable. The following is an example of the command to do this:

~~~bash
chmod 777 /home/zestem/splitter/run_basic_splitter2.sh
~~~
    
#### Execute Project

1.	Change directories to the directory containing the files you uploaded. The following is an example:

    ~~~bash
	cd /home/zestem/splitter
	~~~
	
2.	Type the following to execute the startup script and start the basic_splitter2 model:

    ~~~bash
	./run_basic_splitter2.sh
	~~~

    The terminal should display information about the model executing on the ESP XML Server.

#### View Results

There are two files created in the directory you specified as the project directory:

- basic_splitter2_output1.csv – Created by Compute1 window. Can be viewed with Excel or a text editor.
- basic_splitter2_output2.csv – Created by Compute2 window. Can be viewed with Excel or a text editor.

### Executing the complex_splitter1 Model

#### Edit Startup Script

You must edit the startup script, `run_complex_splitter1.sh` to specify the correct server directories on your system.

1.	Open `run_complex_splitter1.sh` with a text editor. The following is a listing of the file:

    ~~~bash
    # Copyright © 2020, SAS Institute Inc., Cary, NC, USA.  All Rights Reserved.
    # SPDX-License-Identifier: Apache-2.0

    # Register (DateFlux) ESP environment
    export DFESP_HOME=/opt/sas/viya/home/SASEventStreamProcessingEngine/6.2

    export PATH=$DFESP_HOME/bin:$PATH
    export LD_LIBRARY_PATH=$DFESP_HOME/lib:$DFESP_HOME/lib/tk:/opt/sas/viya/home/SASFoundation/sasexe:$DFESP_HOME/ssl/lib

    export PROJDIR=/home/zestem/splitter

    dfesp_xml_server -http 61002 -pubsub 61003 -model file:///home/zestem/splitter/complex_splitter1.xml
    ~~~

2.	Go to the export PROJDIR= line and edit the value to be the directory you created. The following is an example.

    ~~~bash
    export PROJDIR=/home/zestem/splitter
    ~~~

3.	Go to the last line (command to start XML Server) and edit the `-model` parameter to include the full path to the model’s xml file. Ensure there are the correct number of forward slashes (/) at the beginning of the filename. The following is an example:

    ~~~bash
    -model file:///home/zestem/splitter/complex_splitter1.xml
    ~~~
    
4.	Save your changes.

#### Upload Files

Upload the files for the complex_splitter1 example (`complex_splitter1_input.csv`, `complex_splitter1.xml`, and `run_complex_splitter1.sh`) to the directory you created. Change the permission of the `run_complex_splitter1.sh` startup script so it is executable. The following is an example of the command to do this:

~~~
chmod 777 /home/zestem/splitter/run_complex_splitter1.sh
~~~

#### Execute Project

1.	Change directories to the directory containing the files you uploaded. The following is an example:

    ~~~bash
	cd /home/zestem/splitter
	~~~
	
2.	Type the following to execute the startup script and start the complex_splitter1 model:

    ~~~bash
	./run_complex_splitter1.sh
	~~~

    The terminal should display information about the model executing on the ESP XML Server.
    
#### View Results

There are three files created in the directory you specified as the project directory:

- complex_splitter1_output1.csv – Created by Compute2 window. Can be viewed with Excel or a text editor.
- complex_splitter1_output2.csv – Created by Compute3 window. Can be viewed with Excel or a text editor.
- complex_splitter1_output3.csv – Created by Compute4 window. Can be viewed with Excel or a text editor.

### Executing the complex_splitter2 Model

#### Edit Startup Script

You must edit the startup script, `run_complex_splitter2.sh` to specify the correct server directories on your system.

1.	Open `run_complex_splitter2.sh` with a text editor. The following is a listing of the file:

    ~~~bash
    # Copyright © 2020, SAS Institute Inc., Cary, NC, USA.  All Rights Reserved.
    # SPDX-License-Identifier: Apache-2.0

    # Register (DateFlux) ESP environment
    export DFESP_HOME=/opt/sas/viya/home/SASEventStreamProcessingEngine/6.2

    export PATH=$DFESP_HOME/bin:$PATH
    export LD_LIBRARY_PATH=$DFESP_HOME/lib:$DFESP_HOME/lib/tk:/opt/sas/viya/home/SASFoundation/sasexe:$DFESP_HOME/ssl/lib

    export PROJDIR=/home/zestem/splitter

    dfesp_xml_server -http 61002 -pubsub 61003 -model file:///home/zestem/splitter/complex_splitter2.xml
    ~~~
2.	Go to the export PROJDIR= line and edit the value to be the directory you created. The following is an example.

    ~~~bash
    export PROJDIR=/home/zestem/splitter
    ~~~

3.	Go to the last line (command to start XML Server) and edit the `-model` parameter to include the full path to the model’s xml file. Ensure there are the correct number of forward slashes (/) at the beginning of the filename. The following is an example:

    ~~~bash
    -model file:///home/zestem/splitter/complex_splitter2.xml
    ~~~
    
4.	Save your changes.

#### Upload Files

Upload the files for the complex_splitter2 example (`complex_splitter2_input.csv`, `complex_splitter2.xml`, and `run_complex_splitter2.sh`) to the directory you created. Change the permission of the `run_complex_splitter2.sh` startup script so it is executable. The following is an example of the command to do this:

~~~bash
chmod 777 /home/zestem/splitter/run_complex_splitter2.sh
~~~

#### Execute Project

1.	Change directories to the directory containing the files you uploaded. The following is an example:

    ~~~bash
	cd /home/zestem/splitter
	~~~
	
2.	Type the following to execute the startup script and start the complex_splitter2 model:

    ~~~bash
	./run_complex_splitter2.sh
	~~~

    The terminal should display information about the model executing on the ESP XML Server.

#### View Results

There are two files created in the directory you specified as the project directory:

- complex_splitter2_output1.csv – Created by Compute1 window. Can be viewed with Excel or a text editor.
- complex_splitter2_output2.csv – Created by Compute2 window. Can be viewed with Excel or a text editor.

