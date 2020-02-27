# Introduction 
VT Service Processor is a windows service meant for assigning status of the orders of the Visibility Tool. 
This windows service was created as a solution for the number of deadlocks and timeouts occurred when the assigning of statuses were done through the ‘VT Service’ project.
The orders and statuses to be assigned are got from the queue table 'VTService_Status_Queue' of the 'UWReporting' database. The whole process is done with the help of multiple parallel threads in the windows service.  The threads are created based on Programs whose Ids are provided in the queue table.

# Getting Started

Installation process
1. Clone and build the project. 
2. Open the command prompt in Administrator mode
3. Change the directory in the command prompt to the path of InstalUtil.exe
    e.g. “C:\WINDOWS\Microsoft.NET\Framework\v4.0.30319”
4. Get the path to the executable the windows service 
    e.g. “C:\...\VT Service Processor\VTProcessor.Service\bin\Release\VTProcessor.Service.exe”
5.	Execute the following command to install the service
        InstallUtil.exe <path to executable>

    e.g. “InstallUtil.exe  C:\...\VT Service Processor\VTProcessor.Service\bin\Release\VTProcessor.Service.exe”

# Build and Test
1.	The solution can be built by opening the solution file ‘VTServiceProcessor.sln’ in visual studio and choosing the build option. 
2.	A unit test project is integrated in the solution, which can be used for testing.  ‘TestLaunchThreadsMethod’ function can be used to run the tests.
