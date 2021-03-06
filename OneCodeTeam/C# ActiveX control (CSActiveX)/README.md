# C# ActiveX control (CSActiveX)
## Requires
- Visual Studio 2008
## License
- MS-LPL
## Technologies
- COM
- Windows SDK
## Topics
- COM
- Interop
- ActiveX
## Updated
- 03/02/2012
## Description

<h1><span style="font-family:������">ACTIVEX CONTROL DLL</span> (<span style="font-family:������">CSActiveX</span>)</h1>
<h2>Introduction</h2>
<p class="MsoNormal">The sample demonstrates an ActiveX control written in C#. ActiveX controls<span style="">
</span>(formerly known as OLE controls) are small program building blocks that can work in a variety of different containers, ranging from software development tools to end-user productivity tools. For example, it can be used to create distributed applications
 that work over the Internet through web browsers. ActiveX controls can be written in MFC, ATL, C&#43;&#43;, C#, Borland Delphi and Visual Basic. In this sample, we focus on writing an ActiveX control using C#. We will go through the basic steps of adding UI, properties,
 methods, and </p>
<p class="MsoNormal">events to the control. Please note that ActiveX controls or COM components written in .NET languages cannot be referenced by .NET applications in the form of interop assemblies. If you &quot;add reference&quot; to such a TLB, or drag
 &amp; drop such an ActiveX control to your .NET application, you will get an error &quot;The ActiveX type library 'XXXXX.tlb' was exported from a .NET assembly and cannot be added as a reference.&quot;. The correct approach is to add a reference to the .NET
 assembly directly. </p>
<p class="MsoNormal">CSActiveX exposes the following items: </p>
<p class="MsoNormal">1. A C# ActiveX control. </p>
<table class="MsoTableGrid" border="1" cellspacing="0" cellpadding="0" style="border-collapse:collapse; border:none">
<tbody>
<tr style="">
<td width="207" valign="top" style="width:155.55pt; border:solid windowtext 1.0pt; padding:0cm 5.4pt 0cm 5.4pt">
<p class="MsoNormal">Program ID</p>
</td>
<td width="331" valign="top" style="width:248.05pt; border:solid windowtext 1.0pt; border-left:none; padding:0cm 5.4pt 0cm 5.4pt">
<p class="MsoNormal">CSActiveX.CSActiveXCtrl</p>
</td>
</tr>
<tr style="">
<td width="207" valign="top" style="width:155.55pt; border:solid windowtext 1.0pt; border-top:none; padding:0cm 5.4pt 0cm 5.4pt">
<p class="MsoNormal">CLSID_CSActiveXCtrl</p>
</td>
<td width="331" valign="top" style="width:248.05pt; border-top:none; border-left:none; border-bottom:solid windowtext 1.0pt; border-right:solid windowtext 1.0pt; padding:0cm 5.4pt 0cm 5.4pt">
<p class="MsoNormal">80B59B58-98EA-303C-BE83-D26E5D8D6794<span style=""> </span>
</p>
</td>
</tr>
<tr style="">
<td width="207" valign="top" style="width:155.55pt; border:solid windowtext 1.0pt; border-top:none; padding:0cm 5.4pt 0cm 5.4pt">
<p class="MsoNormal">DIID_AxCSActiveXCtrl</p>
</td>
<td width="331" valign="top" style="width:248.05pt; border-top:none; border-left:none; border-bottom:solid windowtext 1.0pt; border-right:solid windowtext 1.0pt; padding:0cm 5.4pt 0cm 5.4pt">
<p class="MsoNormal">D4B8539E-3839-3913-8B1A-C551A9930864</p>
</td>
</tr>
<tr style="">
<td width="207" valign="top" style="width:155.55pt; border:solid windowtext 1.0pt; border-top:none; padding:0cm 5.4pt 0cm 5.4pt">
<p class="MsoNormal">DIID_AxCSActiveXCtrlEvents</p>
</td>
<td width="331" valign="top" style="width:248.05pt; border-top:none; border-left:none; border-bottom:solid windowtext 1.0pt; border-right:solid windowtext 1.0pt; padding:0cm 5.4pt 0cm 5.4pt">
<p class="MsoNormal">901EE2A0-C47C-43EC-B433-985C020051D5</p>
</td>
</tr>
<tr style="">
<td width="207" valign="top" style="width:155.55pt; border:solid windowtext 1.0pt; border-top:none; padding:0cm 5.4pt 0cm 5.4pt">
<p class="MsoNormal">LIBID_CSActiveX</p>
</td>
<td width="331" valign="top" style="width:248.05pt; border-top:none; border-left:none; border-bottom:solid windowtext 1.0pt; border-right:solid windowtext 1.0pt; padding:0cm 5.4pt 0cm 5.4pt">
<p class="MsoNormal">361188E4-99EB-4E43-A72F-C89451E756DD</p>
</td>
</tr>
</tbody>
</table>
<p class="MsoNormal"><span style="">&nbsp;</span><span style="">&nbsp; </span><span style=""></span></p>
<table class="MsoTableGrid" border="1" cellspacing="0" cellpadding="0" style="border-collapse:collapse; border:none">
<tbody>
<tr style="">
<td width="207" valign="top" style="width:155.55pt; border:solid windowtext 1.0pt; padding:0cm 5.4pt 0cm 5.4pt">
<p class="MsoNormal"><b style=""><span style=""></span></b></p>
</td>
<td width="406" valign="top" style="width:304.75pt; border:solid windowtext 1.0pt; border-left:none; padding:0cm 5.4pt 0cm 5.4pt">
<p class="MsoNormal"><b style=""><span style="">name </span></b></p>
</td>
<td width="255" valign="top" style="width:191.35pt; border:solid windowtext 1.0pt; border-left:none; padding:0cm 5.4pt 0cm 5.4pt">
<p class="MsoNormal"><b style=""><span style="">Describtion </span></b></p>
</td>
</tr>
<tr style="">
<td width="207" valign="top" style="width:155.55pt; border:solid windowtext 1.0pt; border-top:none; padding:0cm 5.4pt 0cm 5.4pt">
<p class="MsoNormal" align="center" style="text-align:center; vertical-align:middle">
UI<span style=""> </span></p>
</td>
<td width="406" valign="top" style="width:304.75pt; border-top:none; border-left:none; border-bottom:solid windowtext 1.0pt; border-right:solid windowtext 1.0pt; padding:0cm 5.4pt 0cm 5.4pt">
<p class="MsoNormal">CSActiveXCtrl<span style=""> </span></p>
</td>
<td width="255" valign="top" style="width:191.35pt; border-top:none; border-left:none; border-bottom:solid windowtext 1.0pt; border-right:solid windowtext 1.0pt; padding:0cm 5.4pt 0cm 5.4pt">
<p class="MsoNormal" align="center" style="text-align:center; vertical-align:middle">
The main UI of the control<span style=""> </span></p>
</td>
</tr>
<tr style="">
<td width="207" rowspan="5" style="width:155.55pt; border:solid windowtext 1.0pt; border-top:none; padding:0cm 5.4pt 0cm 5.4pt">
<p class="MsoNormal" align="center" style="text-align:center; vertical-align:middle">
Properties</p>
</td>
<td width="406" valign="top" style="width:304.75pt; border-top:none; border-left:none; border-bottom:solid windowtext 1.0pt; border-right:solid windowtext 1.0pt; padding:0cm 5.4pt 0cm 5.4pt">
<p class="MsoNormal">bool Visible<span style=""> </span></p>
</td>
<td width="255" rowspan="4" style="width:191.35pt; border-top:none; border-left:none; border-bottom:solid windowtext 1.0pt; border-right:solid windowtext 1.0pt; padding:0cm 5.4pt 0cm 5.4pt">
<p class="MsoNormal" align="center" style="text-align:center; vertical-align:middle">
Typical control properties</p>
</td>
</tr>
<tr style="">
<td width="406" valign="top" style="width:304.75pt; border-top:none; border-left:none; border-bottom:solid windowtext 1.0pt; border-right:solid windowtext 1.0pt; padding:0cm 5.4pt 0cm 5.4pt">
<p class="MsoNormal">bool Enabled<span style=""> </span></p>
</td>
</tr>
<tr style="">
<td width="406" valign="top" style="width:304.75pt; border-top:none; border-left:none; border-bottom:solid windowtext 1.0pt; border-right:solid windowtext 1.0pt; padding:0cm 5.4pt 0cm 5.4pt">
<p class="MsoNormal">int ForeColor<span style=""> </span></p>
</td>
</tr>
<tr style="">
<td width="406" valign="top" style="width:304.75pt; border-top:none; border-left:none; border-bottom:solid windowtext 1.0pt; border-right:solid windowtext 1.0pt; padding:0cm 5.4pt 0cm 5.4pt">
<p class="MsoNormal">int BackColor<span style=""> </span></p>
</td>
</tr>
<tr style="">
<td width="406" valign="top" style="width:304.75pt; border-top:none; border-left:none; border-bottom:solid windowtext 1.0pt; border-right:solid windowtext 1.0pt; padding:0cm 5.4pt 0cm 5.4pt">
<p class="MsoNormal">float FloatProperty<span style=""> </span></p>
</td>
<td width="255" valign="top" style="width:191.35pt; border-top:none; border-left:none; border-bottom:solid windowtext 1.0pt; border-right:solid windowtext 1.0pt; padding:0cm 5.4pt 0cm 5.4pt">
<p class="MsoNormal" align="center" style="text-align:center; vertical-align:middle">
Custom properties</p>
</td>
</tr>
<tr style="">
<td width="207" rowspan="2" valign="top" style="width:155.55pt; border:solid windowtext 1.0pt; border-top:none; padding:0cm 5.4pt 0cm 5.4pt">
<p class="MsoNormal" align="center" style="text-align:center; vertical-align:middle">
Methods<span style=""> </span></p>
</td>
<td width="406" valign="top" style="width:304.75pt; border-top:none; border-left:none; border-bottom:solid windowtext 1.0pt; border-right:solid windowtext 1.0pt; padding:0cm 5.4pt 0cm 5.4pt">
<p class="MsoNormal">void Refresh()</p>
</td>
<td width="255" valign="top" style="width:191.35pt; border-top:none; border-left:none; border-bottom:solid windowtext 1.0pt; border-right:solid windowtext 1.0pt; padding:0cm 5.4pt 0cm 5.4pt">
<p class="MsoNormal" align="center" style="text-align:center; vertical-align:middle">
Typical control methods</p>
</td>
</tr>
<tr style="">
<td width="406" valign="top" style="width:304.75pt; border-top:none; border-left:none; border-bottom:solid windowtext 1.0pt; border-right:solid windowtext 1.0pt; padding:0cm 5.4pt 0cm 5.4pt">
<p class="MsoNormal">string HelloWorld()</p>
</td>
<td width="255" valign="top" style="width:191.35pt; border-top:none; border-left:none; border-bottom:solid windowtext 1.0pt; border-right:solid windowtext 1.0pt; padding:0cm 5.4pt 0cm 5.4pt">
<p class="MsoNormal" align="center" style="text-align:center; vertical-align:middle">
Custom methods</p>
</td>
</tr>
<tr style="">
<td width="207" rowspan="2" style="width:155.55pt; border:solid windowtext 1.0pt; border-top:none; padding:0cm 5.4pt 0cm 5.4pt">
<p class="MsoNormal" align="center" style="text-align:center; vertical-align:middle">
Events<span style=""> </span></p>
</td>
<td width="406" valign="top" style="width:304.75pt; border-top:none; border-left:none; border-bottom:solid windowtext 1.0pt; border-right:solid windowtext 1.0pt; padding:0cm 5.4pt 0cm 5.4pt">
<p class="MsoNormal">void Click();</p>
</td>
<td width="255" valign="top" style="width:191.35pt; border-top:none; border-left:none; border-bottom:solid windowtext 1.0pt; border-right:solid windowtext 1.0pt; padding:0cm 5.4pt 0cm 5.4pt">
<p class="MsoNormal" align="center" style="text-align:center; vertical-align:middle">
Typical control events</p>
</td>
</tr>
<tr style="">
<td width="406" valign="top" style="width:304.75pt; border-top:none; border-left:none; border-bottom:solid windowtext 1.0pt; border-right:solid windowtext 1.0pt; padding:0cm 5.4pt 0cm 5.4pt">
<p class="MsoNormal">void FloatPropertyChanging(float NewValue, ref bool Cancel);<span style="">
</span></p>
</td>
<td width="255" valign="top" style="width:191.35pt; border-top:none; border-left:none; border-bottom:solid windowtext 1.0pt; border-right:solid windowtext 1.0pt; padding:0cm 5.4pt 0cm 5.4pt">
<p class="MsoNormal" align="center" style="text-align:center; vertical-align:middle">
Custom events</p>
<p class="MsoNormal">FloatPropertyChanging is fired before new value is set to the
<span style="">f</span>loatProperty property. The Cancel parameter allows the client to cancel the change of FloatProperty.<span style="">
</span></p>
</td>
</tr>
</tbody>
</table>
<h2><span style="">Building</span> the Sample</h2>
<p class="MsoListParagraphCxSpFirst" style=""><span style=""><span style="">1.<span style="font:7.0pt &quot;Times New Roman&quot;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span></span><span style="">Run your <span style="">&nbsp;</span>Visual Studio as Administrator.
</span></p>
<p class="MsoListParagraphCxSpLast" style=""><span style=""><span style="">2.<span style="font:7.0pt &quot;Times New Roman&quot;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span></span><span style="">Build the solution.</span></p>
<h2>Using the Code</h2>
<h3><span style="">A. Creating the project </span></h3>
<p class="MsoNormal">Step1. Create a Visual C# / Class Library project named CSActiveX in Visual Studio 2008. Delete the default Class1.cs file.
</p>
<p class="MsoNormal">Step2. In order to make the .NET assembly COM-visible, <span style="">
</span></p>
<p class="MsoNormal">first, open the property of the project. Click the Assembly Information button in the Application page, and select the &quot;Make Assembly COM-Visible&quot; box. This corresponds to the assembly attribute ComVisible in AssemblyInfo.cs<span style="">.
 T</span>he GUID value in the dialog is the libid of the component: </p>
<div class="scriptcode">
<div class="pluginEditHolder" pluginCommand="mceScriptCode">
<div class="title"><span>C#</span></div>
<div class="pluginLinkHolder"><span class="pluginEditHolderLink">Edit</span>|<span class="pluginRemoveHolderLink">Remove</span>
</div>
<span class="hidden">csharp</span>

<pre id="codePreview" class="csharp">
// Setting ComVisible to false makes the types in this assembly not visible 
// to COM components.  If you need to access a type in this assembly from 
// COM, set the ComVisible attribute to true on that type.
[assembly: ComVisible(true)]


// The following GUID is for the ID of the typelib if this project is exposed to COM
[assembly: Guid(&quot;361188e4-99eb-4e43-a72f-c89451e756dd&quot;)]

</pre>
</div>
</div>
<div class="endscriptcode">&nbsp;</div>
<p class="MsoNormal">Second, in the Build page of the project's property, select the option &quot;Register for COM interop&quot;. This option specifies whether your managed application will expose a COM object (a COM-callable wrapper) that allows a COM object
 to interact with your managed application. </p>
<h3><span style="">B. Adding the ActiveXCtrlHelper class </span></h3>
<p class="MsoNormal">ActiveXCtrlHelper provides the helper functions to register/unregister an ActiveX control, and helps to handle the focus and tabbing across the container and the .NET controls.
</p>
<h3><span style="">C. Adding a user control and expose it as an ActiveX control </span>
</h3>
<p class="MsoNormal">Step1. Right-click the project and choose Add / User Control in the context menu. Name the control as CSActiveXCtrl. Next, double-click the control to open its design view and design the UI.
</p>
<p class="MsoNormal">Step2. In the code view of CSActiveXCtrl.cs, add a public interface named AxCSActiveXCtrl to describe the COM interface of the coclass CSActiveXCtrl. Inside the interface, define the properties and methods to be exposed by the ActiveX
 control. Attach the GuidAttribute to the interface. The GUID value can be generated using Tools / Create GUID, and is used as the interface ID.
</p>
<div class="scriptcode">
<div class="pluginEditHolder" pluginCommand="mceScriptCode">
<div class="title"><span>C#</span></div>
<div class="pluginLinkHolder"><span class="pluginEditHolderLink">Edit</span>|<span class="pluginRemoveHolderLink">Remove</span>
</div>
<span class="hidden">csharp</span>

<pre id="codePreview" class="csharp">
/// &lt;summary&gt;
    /// AxCSActiveXCtrl describes the COM interface of the coclass 
    /// &lt;/summary&gt;
    [Guid(&quot;D4B8539E-3839-3913-8B1A-C551A9930864&quot;)]
    public interface AxCSActiveXCtrl
    {
        #region Properties


        bool Visible { get; set; }          // Typical control property
        bool Enabled { get; set; }          // Typical control property
        int ForeColor { get; set; }         // Typical control property
        int BackColor { get; set; }         // Typical control property
        float FloatProperty { get; set; }   // Custom property


        #endregion


        #region Methods


        void Refresh();                     // Typical control method
        string HelloWorld();                // Custom method
        
        #endregion
    }

</pre>
</div>
</div>
<div class="endscriptcode">&nbsp;</div>
<p class="MsoNormal">The detailed steps of adding properties and methods are documented below.
</p>
<p class="MsoNormal">Step3. In CSActiveXCtrl.cs, add a public interface, AxCSActiveXCtrlEvents, to describe the events of the control. Inside the interface, define the prototype of the events and assign DISPID to each. For example,
<span style=""></span></p>
<p class="MsoNormal">The detailed steps of adding events are documented below. </p>
<p class="MsoNormal">Please note that DISPID must be explicitly defined for each event, otherwise, the callback address cannot be found when the event is fired.
</p>
<p class="MsoNormal">Next, assign a GUID to the interface as the event ID, and define the interface type as InterfaceIsIDispatch.
</p>
<div class="scriptcode">
<div class="pluginEditHolder" pluginCommand="mceScriptCode">
<div class="title"><span>C#</span></div>
<div class="pluginLinkHolder"><span class="pluginEditHolderLink">Edit</span>|<span class="pluginRemoveHolderLink">Remove</span>
</div>
<span class="hidden">csharp</span>

<pre id="codePreview" class="csharp">
/// &lt;summary&gt;
   /// AxCSActiveXCtrlEvents describes the events the coclass can sink
   /// &lt;/summary&gt;
   [Guid(&quot;901EE2A0-C47C-43ec-B433-985C020051D5&quot;)]
   [InterfaceType(ComInterfaceType.InterfaceIsIDispatch)]
   // The public interface describing the events of the control
   public interface AxCSActiveXCtrlEvents
   {
       #region Events


       // Must explicitly define DISPID for each event, otherwise, the 
       // callback address cannot be found when the event is fired.
       [DispId(1)]
       void Click();
       [DispId(2)]
       void FloatPropertyChanging(float NewValue, ref bool Cancel);


       #endregion
   }

</pre>
</div>
</div>
<div class="endscriptcode">&nbsp;</div>
<p class="MsoNormal">Step4. Set the class CSActiveXCtrl to implement the interface AxCSActiveXCtrl and attach [ComSourceInterfaces(typeof(AxCSActiveXCtrlEvents))] to the class.ComSourceInterfacesAttribute identifies the interface exposed as COM event sources
 for the attributed class. Next, add the attribute [ClassInterface(ClassInterfaceType.None)] to the class, which tells the type-library generation tools that we do not require a Class Interface. This ensures that the AxCSActiveXCtrl interface is the default
 interface. <span style=""></span></p>
<p class="MsoNormal">In addition, specify the GUID of the class, aka CLSID, using the Guid attribute:
</p>
<h3><span style="">D. ActiveX Control Registration </span></h3>
<p class="MsoNormal">Additional registry keys/values are required to be set for ActiveX controls when compared with ordinary COM components. The default COM registration routine does not meet the need. Inside CSActiveXCtrl, add the functions Register, Unregister
 and decorate them with ComRegisterFunctionAttribute, ComUnregisterFunctionAttribute. The custom routine gets called after Regasm
</p>
<p class="MsoNormal">finishes the default behaviors. The Register and Unregister functions call the helper methods in ActiveXCtrlHelper.
</p>
<h3><span style="">E. Adding Properties to the ActiveX control </span></h3>
<p class="MsoNormal">Step1. Add the prototype of property to the COM interface AxCSActiveXCtrl. For example,
</p>
<div class="scriptcode">
<div class="pluginEditHolder" pluginCommand="mceScriptCode">
<div class="title"><span>C#</span></div>
<div class="pluginLinkHolder"><span class="pluginEditHolderLink">Edit</span>|<span class="pluginRemoveHolderLink">Remove</span>
</div>
<span class="hidden">csharp</span>

<pre id="codePreview" class="csharp">
float FloatProperty { get; set; }

</pre>
</div>
</div>
<div class="endscriptcode">&nbsp;</div>
<p class="MsoNormal">Step2. Add the implementation of the property to the coclass CSActiveXCtrl. For example,
</p>
<div class="scriptcode">
<div class="pluginEditHolder" pluginCommand="mceScriptCode">
<div class="title"><span>C#</span></div>
<div class="pluginLinkHolder"><span class="pluginEditHolderLink">Edit</span>|<span class="pluginRemoveHolderLink">Remove</span>
</div>
<span class="hidden">csharp</span>

<pre id="codePreview" class="csharp">
private float fField = 0;
    public float FloatProperty
    {
        get { return this.fField; }
        set { this.fField = value; }
    }

</pre>
</div>
</div>
<div class="endscriptcode">&nbsp;</div>
<h3><span style="">F. Adding Methods to the ActiveX control </span></h3>
<p class="MsoNormal">Step1. Add the prototype of method to the COM interface AxCSActiveXCtrl. For example,
</p>
<div class="scriptcode">
<div class="pluginEditHolder" pluginCommand="mceScriptCode">
<div class="title"><span>C#</span></div>
<div class="pluginLinkHolder"><span class="pluginEditHolderLink">Edit</span>|<span class="pluginRemoveHolderLink">Remove</span>
</div>
<span class="hidden">csharp</span>

<pre id="codePreview" class="csharp">
string HelloWorld();

</pre>
</div>
</div>
<div class="endscriptcode">&nbsp;</div>
<p class="MsoNormal">Step2. Add the implementation of the method to the coclass CSActiveXCtrl. For example,
</p>
<div class="scriptcode">
<div class="pluginEditHolder" pluginCommand="mceScriptCode">
<div class="title"><span>C#</span></div>
<div class="pluginLinkHolder"><span class="pluginEditHolderLink">Edit</span>|<span class="pluginRemoveHolderLink">Remove</span>
</div>
<span class="hidden">csharp</span>

<pre id="codePreview" class="csharp">
    public string HelloWorld()
    {
        return &quot;HelloWorld&quot;;
    }

</pre>
</div>
</div>
<div class="endscriptcode">&nbsp;</div>
<h3><span style="">G. Adding Events to the ActiveX control </span></h3>
<p class="MsoNormal">Step1. Add the prototype of event to the event interface AxCSActiveXCtrlEvents, and explicitly assign a DISPID to it. For example,
</p>
<div class="scriptcode">
<div class="pluginEditHolder" pluginCommand="mceScriptCode">
<div class="title"><span>C#</span></div>
<div class="pluginLinkHolder"><span class="pluginEditHolderLink">Edit</span>|<span class="pluginRemoveHolderLink">Remove</span>
</div>
<span class="hidden">csharp</span>

<pre id="codePreview" class="csharp">
    [DispId(2)]
    void FloatPropertyChanging(float NewValue, ref bool Cancel);

</pre>
</div>
</div>
<div class="endscriptcode">&nbsp;</div>
<p class="MsoNormal">Step2. Inside the coclass CSActiveXCtrl, add a delegate with the above prototype as the event handler. Set the delegate to be [ComVisible(false)]. For example,
</p>
<div class="scriptcode">
<div class="pluginEditHolder" pluginCommand="mceScriptCode">
<div class="title"><span>C#</span></div>
<div class="pluginLinkHolder"><span class="pluginEditHolderLink">Edit</span>|<span class="pluginRemoveHolderLink">Remove</span>
</div>
<span class="hidden">csharp</span>

<pre id="codePreview" class="csharp">
    [ComVisible(false)]
    public delegate void FloatPropertyChangingEventHandler
    (float NewValue, ref bool Cancel);

</pre>
</div>
</div>
<div class="endscriptcode">&nbsp;</div>
<p class="MsoNormal">Next, add a public event: </p>
<div class="scriptcode">
<div class="pluginEditHolder" pluginCommand="mceScriptCode">
<div class="title"><span>C#</span></div>
<div class="pluginLinkHolder"><span class="pluginEditHolderLink">Edit</span>|<span class="pluginRemoveHolderLink">Remove</span>
</div>
<span class="hidden">csharp</span>

<pre id="codePreview" class="csharp">
public event FloatPropertyChangingEventHandler FloatPropertyChanging;

</pre>
</div>
</div>
<div class="endscriptcode">&nbsp;</div>
<p class="MsoNormal">And raise the event in the proper places. Please check null on the event before raising it. For example,
</p>
<div class="scriptcode">
<div class="pluginEditHolder" pluginCommand="mceScriptCode">
<div class="title"><span>C#</span></div>
<div class="pluginLinkHolder"><span class="pluginEditHolderLink">Edit</span>|<span class="pluginRemoveHolderLink">Remove</span>
</div>
<span class="hidden">csharp</span>

<pre id="codePreview" class="csharp">
if (null != FloatPropertyChanging)
        FloatPropertyChanging(value, ref cancel);

</pre>
</div>
</div>
<div class="endscriptcode">&nbsp;</div>
<h3><span style="">H. Adding the ToolBox Bitmap resource </span></h3>
<p class="MsoNormal">The ToolBox bitmap resource is specified in the regsitry key:<span style="">
</span>HKCR\CLSID\{CLSID of the control}\ToolBoxBitmap32\(see the RegisterControl method in ActiveXCtrlHelper)ToolBoxBitmap32 is used to identify the module name and the resource ID for a 16 x 16 bitmap as the toolbar button face. Each specified icon must be
 embedded as a win32 resource in the assembly. In order to embed the bitmap </p>
<p class="MsoNormal">CSActiveX.bmp into the assembly as a win32 resource, we need to
<span style=""></span></p>
<p class="MsoNormal">Step1. Place the CSActiveX.bmp file in the root folder of the project.
</p>
<p class="MsoNormal">Step2. Add a .rc file (CSActiveX.rc) to the project with the content:
</p>
<p class="MsoNormal"><span style="">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span>101 BITMAP CSActiveX.bmp </p>
<p class="MsoNormal">101 is the resource ID, BITMAP is the resource type, and CSActiveX.bmp is theresource name.
</p>
<p class="MsoNormal">Step3. Open Project Properties, and turn to the Build Events page. In Pre-build event command line, enter this command:
</p>
<p class="MsoNormal"><span style="">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span>@echo. </p>
<p class="MsoNormal"><span style="">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span>IF EXIST &quot;$(DevEnvDir)..\..\..\Microsoft SDKs\Windows\v6.0A\bin\rc.exe&quot; (&quot;$(DevEnvDir)..\..\..\Microsoft SDKs\Windows\v6.0A\bin\rc.exe&quot; /r &quot;$(ProjectDir)CSActiveX.rc&quot;) ELSE (IF EXIST &quot;$(DevEnvDir)..\..\SDK\v2.0\Bin\rc.exe&quot;
 (&quot;$(DevEnvDir)..\..\SDK\v2.0\Bin\rc.exe&quot; /r &quot;$(ProjectDir)CSActiveX.rc&quot;) ELSE (IF EXIST &quot;$(DevEnvDir)..\Tools\Bin\rc.exe&quot; (&quot;$(DevEnvDir)..\Tools\Bin\rc.exe&quot; /r &quot;$(ProjectDir)CSActiveX.rc&quot;) ELSE (IF EXIST &quot;$(DevEnvDir)..\..\VC\Bin\rc.exe&quot;
 (&quot;$(DevEnvDir)..\..\VC\Bin\rc.exe&quot; /r &quot;$(ProjectDir)CSActiveX.rc&quot;) ELSE (IF EXIST &quot;C:\Program Files (x86)\microsoft sdks\windows\v6.0A\bin\rc.exe&quot; (&quot;c:\Program Files (x86)\microsoft sdks\windows\v6.0A\bin\rc.exe&quot; /r
 &quot;$(ProjectDir)CSActiveX.rc&quot;) ELSE (IF EXIST &quot;C:\Program Files\microsoft sdks\windows\v6.0A\bin\rc.exe&quot; (&quot;c:\Program Files\microsoft sdks\windows\v6.0A\bin\rc.exe&quot; /r &quot;$(ProjectDir)CSActiveX.rc&quot;) ELSE (@Echo Unable to
 find rc.exe, using default manifest instead)))))) </p>
<p class="MsoNormal"><span style="">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span>@echo. </p>
<p class="MsoNormal">The command searches for the Resource Compiler (rc.exe), and use the tool to compile the resource definition file and the resource files (binary files such as icon, bitmap, and cursor files) into a binary resource (.RES) file: CSActiveX.RES.
</p>
<p class="MsoNormal">Step4. Turn to the Application page of Project Properties.<span style="">
</span></p>
<p class="MsoNormal"><span style="">&nbsp;</span>In the section &quot;Specify how application resources will be managed&quot;, select &quot;Resource File&quot;, and enter the full path of CSActiveX.RES that is generated in step 3.
</p>
<p class="MsoNormal">Step5. (Optional) If you perfer a relative path to the full path of CSActiveX.RES, you need to modify the project file (CSActiveX.csproj). The &quot;Resource File&quot; value corresponds to the XML element:
</p>
<div class="scriptcode">
<div class="pluginEditHolder" pluginCommand="mceScriptCode">
<div class="title"><span>XML</span></div>
<div class="pluginLinkHolder"><span class="pluginEditHolderLink">Edit</span>|<span class="pluginRemoveHolderLink">Remove</span>
</div>
<span class="hidden">xml</span>

<pre id="codePreview" class="xml">
&lt;Win32Resource&gt;CSActiveX.res&lt;/Win32Resource&gt;

</pre>
</div>
</div>
<div class="endscriptcode">&nbsp;</div>
<p class="MsoNormal"></p>
<h2>More Information<span style=""> </span></h2>
<p class="MsoListParagraph" style=""><span style="font-family:Symbol"><span style="">��<span style="font:7.0pt &quot;Times New Roman&quot;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span></span><a href="http://msdn.microsoft.com/en-us/vbasic/bb419144.aspx">Interop Forms Toolkit 2.0</a>
</p>
<hr>
<div><a href="http://go.microsoft.com/?linkid=9759640" style="margin-top:3px"><img alt="" src="http://bit.ly/onecodelogo">
</a></div>
