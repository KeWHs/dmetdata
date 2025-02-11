### Raw Data Preparation
1. Download the raw data from the github source or use your own LC-MS/MS data instead.

2. Convert the raw data to mzML or mzXML format using Proteowizard **MSConvert** tool (https://proteowizard.sourceforge.io/).
* Detailed convertion parameters are as follows:
<br><p><img src="img/msconvert.png" alt="msconvert" width="450">

### DMetFinder Usage
1. Download the release version of DMetFinder and unpack the dmetfinder.zip file.

2. Place the **license key** in the same folder as the exe executable file.

3. Double click the **dmetfinder.exe** file to start the program.

4. Click the link shown in the terminal to open the web interface. Do not close the terminal window until you finish the analysis.
<br><p><img src="img/terminal.png" alt="terminal" width="450">

5. Upload raw data files and configure the analysis parameters.
* You can customize the analysis parameters in **Advanced** configs. Description of each parameter is provided in the [**HELP.md**](./HELP.md) file.
* Please fill in an **email** address, but it does not have to be a real one. The **debug** parameter is unnecessary.
* Finally, click **Submit Data** to start the analysis.
* The parameters circled in red are mandatory:
<br><p><img src="img/web_interface.png" alt="webinterface" width="300">

6. Wait for the analysis to complete. You can check the detailed logs in the terminal window.

7. Finally, the results will be displayed in the web interface.