

# # W3-ASP.NET-Core-Web-App

This repository contains a simple Template  ASP.NET Core Web App Created with Visual Studio to practice app deployment with IIS (Internet Information Services) on a Windows server.


# Usage Instructions:
Hopefully if you follow the instructions below you should have your app up and running by the end of it.

## 1) Create a folder on your windows machine and clone this repo into it.
Nothing special here , just create a folder and name it as to your liking.
## 2) Publish the App

Before the app can be deployed using the IIS ,it needs to be Published(compiled) and it can be done in several ways:
1) **Using Visual studio** ,right click on your app folder in the Solution Explorer and select "Publish" which will prompt you to select a path to a location in which the Publish files will be saved .
2) **Using cmd.exe** ,for this you will need to download the [.NET SDK](https://dotnet.microsoft.com/en-us/download/dotnet/thank-you/sdk-6.0.300-windows-x64-installer) and install it on the windows machine on which you wish to publish.
3) Once installed, go to the folder containing the cloned Github repo (if you see the W3-ASP.NET-Core-Web-App.sln file, you are in the correct place) and open cmd (just write cmd in the the location bar of Windows Explorer).
In the **cmd** type :  `dotnet publish -c Release` .

That is it, now you should have a folder named Publish containing the ready app. 

It should be located in:  \W3-ASP.NET-Core-Web-App\bin\Release\net6.0\

**Note that these two methods aren't the only ones , you may use whichever method suits you best.**

## 3) Set Up the IIS
- First you will need to download the [ASP.NET Core 6.0 Runtime (v6.0.5) - Windows Hosting Bundle](https://dotnet.microsoft.com/en-us/download/dotnet/thank-you/runtime-aspnetcore-6.0.5-windows-hosting-bundle-installer) and install it.
- Next you need to Enable IIS and required IIS components on Windows Server , use this [GUIDE](https://enterprise.arcgis.com/en/web-adaptor/latest/install/iis/enable-iis-2016-components-server.htm)
- Enable the IIS :  **Control Panel >> Programs and Features >> Turn Windows features on or off**.
Tick the Internet Information Services box and press **ok**.
- Now open the IIS : **Windows Administrative Tools >> Internet Information Services (IIS) Manager**.
- On the left under Connections open your machine , right click on Application Pools and select **Add application Pool** , name it as you wish.
- Again under Connections ,right click on sites, select **Add Website...**
- Name your site, select the pool you created as the application pool, Under Physical path browse to the **Publish** folder which was created in section 2) of this guide and select it (the correct Publish folder should contain a **web.config** file).
- Set the port to 5100 and click **ok**.
Now you can enter http://localhost:5100/ in your web browser and see the app running.

## 4) Possible errors

When trying to access the app on http://localhost:5100/ you may encounter an error, do not panic, it is probably because the IIS cant access the **web.config** file.

To solve this go to https://docs.microsoft.com/en-us/troubleshoot/developer/webapps/iis/health-diagnostic-performance/http-error-500-19-webpage and scroll down until you find the correct section for your error (Should be under **HRESULT code 0x80070005**), follow the steps described there and your problem should be solved, I know mine was ;).

For other errors you may reference the menu on the left of the page or download a [.pdf manual](https://opdhsblobprod04.blob.core.windows.net/contents/339277257e174fac944c6129b3f0ed8e/0ea7d1829755983a40a0d6aea3878a7c?skoid=2d004ef0-5468-4cd8-a5b7-14c04c6415bc&sktid=975f013f-7f24-47e8-a7d3-abc4752bf346&skt=2022-06-02T05%3A20%3A31Z&ske=2022-06-09T05%3A25%3A31Z&sks=b&skv=2020-10-02&sv=2020-08-04&se=2022-06-03T19%3A26%3A39Z&sr=b&sp=r&sig=%2BXZPfW9tiDABiRpt%2BM0D1ocbeJ129jpq2KwQBiY%2BqaA%3D) for later use/reference.



## Thank you for visiting!



