---
layout: post
title: Localization | PivotGrid | Syncfusion
description: Localization support for customizing data and resources for specific culture or language in PIvotGrid control.
platform: wpf
control: Pivot grid
documentation: ug
---

# Localization

Localization deals with customizing data and resources for specific culture or language. The built-in localization and globalization mechanism in WPF allows you to localize any string resource used by pivot grid controls. Localization can be done in the following ways.

* Localization using resource file.
* Localization using satellite assembly.

## Localization using resource file

Create and place the resource files in a separate location inside the user application. Then, access the culture specific resources from the current application assembly.

For this, first create a resource file for the pivot grid control and translate the strings to your culture. After the strings are translated, you might use the resources in your projects by setting the corresponding culture in your application.

Refer to the following code sample.

{% highlight C# %}

public MainWindow() {
    //Set the current thread culture to load the localization resource file.
    System.Threading.Thread.CurrentThread.CurrentUICulture = new System.Globalization.CultureInfo("ar-AE");
    InitializeComponent();
    if (System.Globalization.CultureInfo.CurrentUICulture.ToString() == "ar-AE") {
        this.FlowDirection = System.Windows.FlowDirection.RightToLeft;
    }
}

{% endhighlight %}

## Localization using satellite assembly

Here, the resource file should be embedded in a satellite assembly and can be used in the application for applying localization.

The following steps illustrate the process of creating satellite assembly:

Open the **Visual Studio Command prompt** and navigate to the folder that contains the **.resx* file in your application. 

Generate a **.resources* file that is to be embedded in the satellite assembly by entering the following command in the command prompt.

**system drive> Resgen MyResource.ar-AE.resx**

After executing the above command, a **.resources* file will be generated in the same folder. Then, enter the following command in the command prompt.

**system drive> AL.exe**

Create a satellite assembly for your culture by embedding the **.resources* file using the following command.

**system drive> al /target:lib /embed:MyResource.ar-AE.resources /culture:ar-AE /out:MyApp.resources.dll**

Now, MyResource.ar-AE.resources is the resource file embedded in the MyApp.resources.dll.

After executing the above command, the satellite assembly will be generated in the same folder. Finally, place the assembly in the following path:
**{Location of the application}\bin\debug\ar-AE\MayAppName.resources.dll**

N> Make sure that the name of satellite assembly should be in the format *MyAppName.resources.dll* and the name of the **.resx* file should be like Syncfusion.PivotAnalysis.Wpf.ar-AE.resx (Arabic). If the name of dll’s differs from your application name, then localization will not work.

![Localized pivot grid and display the data from right to left](Localization-Images/PivotGrid Shows localization behaviour.png)