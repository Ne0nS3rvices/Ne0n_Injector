
--------------------------------------------Requirements--------------------------------------------
Administrator Privileges:

The injector must be run as an administrator to access and modify other processes.

Right-click the Ne0nInjector.exe file and select Run as Administrator.

.NET Runtime (if not self-contained):

If the injector is not published as a self-contained application, the .NET 6.0 runtime must be installed on the target machine.

--------------------------------------------How It Works--------------------------------------------
1. Running the Injector
Double-click the Ne0nInjector.exe file to launch the application.

Important: Always run the injector as an administrator. Right-click the EXE file and select Run as Administrator.

2. Selecting a Target Process
The injector automatically loads a list of all running processes into the dropdown menu.

Select the target process from the dropdown menu. The process name and PID (Process ID) are displayed.

3. Selecting a DLL File
Click the Browse button to open a file dialog.

Navigate to the DLL file you want to inject and select it.

The path to the DLL file will be displayed in the text box.

4. Injecting the DLL
Click the Inject DLL button to inject the selected DLL into the target process.

If the injection is successful, a message box will display: "DLL injected successfully!".

If the injection fails, an error message will be displayed with details about the failure.

5. Embedded EXE Execution
When the injector starts, it automatically extracts and runs an embedded EXE file (Ne0n.exe).

The embedded EXE is saved to a temporary location and executed.

If the EXE fails to run, an error message will be displayed.

--------------------------------------------DLL Injection Process--------------------------------------------

Open the Target Process:

The injector uses the OpenProcess function to gain access to the target process.

Allocate Memory in the Target Process:

The VirtualAllocEx function is used to allocate memory in the target process for the DLL path.

Write the DLL Path:

The WriteProcessMemory function writes the DLL path into the allocated memory.

Load the DLL:

The CreateRemoteThread function creates a remote thread in the target process to load the DLL using LoadLibraryA.

Clean Up:

The injector closes handles and frees resources after the injection is complete.
