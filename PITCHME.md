---?image=assets/images/gitpitch-audience.jpg
@title[UEFI_Driver_Wizard_Lab]
<br><br><br>
<span style="font-size:0.75em" >This slide deck has moved to:  
https://gitpitch.com/tianocore-training/UEFI_Driver_Wizard_Lab/master#/
</span>
<br><br>
## <span class="gold"   >UEFI & EDK II Training</span>

#### UEFI Driver Wizard Lab

<br>
<span style="font-size:0.75em" ><a href='http://www.tianocore.org'>tianocore.org</a></span>
Note:
  PITCHME.md for UEFI / EDK II Training  UEFI Driver Wizard Lab

  Copyright (c) 2018, Intel Corporation. All rights reserved.<BR>

  Redistribution and use in source (original document form) and 'compiled'
  forms (converted to PDF, epub, HTML and other formats) with or without
  modification, are permitted provided that the following conditions are met:

  1) Redistributions of source code (original document form) must retain the
     above copyright notice, this list of conditions and the following
     disclaimer as the first lines of this file unmodified.

  2) Redistributions in compiled form (transformed to other DTDs, converted to
     PDF, epub, HTML and other formats) must reproduce the above copyright
     notice, this list of conditions and the following disclaimer in the
     documentation and/or other materials provided with the distribution.

  THIS DOCUMENTATION IS PROVIDED BY TIANOCORE PROJECT "AS IS" AND ANY EXPRESS OR
  IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF
  MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO
  EVENT SHALL TIANOCORE PROJECT  BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL,
  SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO,
  PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS;
  OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY,
  WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR
  OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS DOCUMENTATION, EVEN IF
  ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.



---  
@title[Lesson Objective]
<BR>
### <p align="center"<span class="gold"   >Lesson Objective </span></p><br>

<!---  Add bullets using https://fontawesome.com/cheatsheet certificate
-->
<ul style="list-style-type:none">
 <li>@fa[certificate gp-bullet-cyan]<span style="font-size:0.9em">&nbsp;&nbsp;Setup the UEFI Driver Wizard</span></li><br>
 <li>@fa[certificate gp-bullet-yellow]<span style="font-size:0.9em">&nbsp;&nbsp;Create a UEFI Driver Template</span> </li>
</ul>


---?image=assets/images/binary-strings-black2.jpg
@title[UEFI Driver Wizard Section ]
<br><br><br><br><br><br>
### <span class="gold"  >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UEFI Driver Wizard</span>
<span style="font-size:0.9em" >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Creating a Template UEFI Driver with the </span><br>
<span style="font-size:0.9em" >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UEFI Driver Wizard</span>



---?image=/assets/images/slides/Slide3.JPG
@title[UEFI Driver Wizard  Overview]
<br>
<p align="left"><span class="gold" >UEFI Driver Wizard  Overview</span></p>
<br>
<div class="left1">
<ul style="list-style-type:none">
  <li><span style="font-size:0.8em" ><font color="cyan">&check;&nbsp;&nbsp;Open source tool  </font> </span>  </li>
  <li><span style="font-size:0.8em" ><font color="white">&check;&nbsp;&nbsp;Based on Driver Writer’s Guide for UEFI 2.3.1 content</font> </span>  </li>
  <li><span style="font-size:0.8em" ><font color="cyan">&check;&nbsp;&nbsp;Intel engineers contributed   </font> </span>  </li>
  <li><span style="font-size:0.8em" ><font color="white">&check;&nbsp;&nbsp;Located on <a href="http://www.tianocore.org">www.TianoCore.org</a>  </font> </span>  </li>
</ul>
</div>
<div class="right1">
  <span style="font-size:0.8em" > &nbsp;&nbsp;</span> 
</div>

Note:

---?image=/assets/images/slides/Slide5.JPG
@title[Installing Python for UEFI Driver Wizard]
<p align="right"><span class="gold" >Installing Python for UEFI Driver Wizard</span></p>
<span style="font-size:01.0em" ><font color="#92D050">Requirements and Options </font></span><br>
<br>
<ul style="list-style-type:disc">
  <li><span style="font-size:0.8em" >Work space  must contain BaseTools, MdePkg & MdeModulePkg Packages from <a href="https://github.com/tianocore/tianocore.github.io/wiki/Driver-Developer">UDK2018</a> for Driver development on Tianocore.org </span> </li>
  <li><span style="font-size:0.8em" >Uses previous lab’s setup `$HOME/src/edk2`   </span> </li>
  <li><span style="font-size:0.8em" >Python scripts from  <a href="https://github.com/tianocore/edk2-share/tree/master/DriverDeveloper/UefiDriverWizard">Github Link </a> then use instructions from README for Python and wxPython versions to install then run</span> </li>
  <ul style="list-style-type:none">
    <li><span style="font-size:0.6em" >&nbsp;&nbsp;<span style="background-color: #101010">`bash$ python launch.py`</span> </span></li>
  </ul>
</ul>

Note:

Same as slide


---?image=/assets/images/slides/Slide7.JPG
@title[Requirements for Your Driver ]
<p align="center"><span class="gold" ><b>Requirements for Your Driver </b></span></p>
@snap[north-west span-80 ]
<br>
<br>
@box[bg-grey-25 text-white rounded my-box-pad2  ](<p style="line-height:70%" ><span style="font-size:0.9em; font-weight: bold;" > <br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
<br>
@snapend


@snap[north-west span-80 ]
<br>
<br>
<br>
<span style="font-size:0.9em" >&nbsp;&nbsp;&nbsp;Using UEFI Driver Wizard</span>
<ul>
   <li><span style="font-size:0.7em" >UEFI Device Driver </span></li>
   <li><span style="font-size:0.7em" >UEFI Version 2.7 (0x00020046) </span><br><span style="font-size:0.6em" >`#define EFI_2_70_SYSTEM_TABLE_REVISION ((2<<16) | (70DEC))` </span></li>
   <li><span style="font-size:0.7em" >Unloadable driver </span></li>
   <li><span style="font-size:0.7em" >Support IA32 & x64 CPUs </span></li>
   <li><span style="font-size:0.7em" >Returns component name information </span></li>
   <li><span style="font-size:0.7em" >Test console device </span></li>
   <li><span style="font-size:0.7em" >Option to produce strings & forms for setup  </span></li>
</ul>
@snapend

Note:



---
@title[Template File Contents]
<p align="right"><span class="gold" ><b>Template File Contents </b></span></p>

@snap[north-west span-60 fragment]
<br>
<br>
<br>
@box[bg-gold2 text-white rounded my-box-pad2  ](<p style="line-height:70%" ><span style="font-size:0.9em; font-weight: bold;" > Proper UEFI driver entry point <br>&nbsp;</span></p>)
<br>
@snapend


@snap[north-east span-65 fragment]
<br>
<br>
<br>
<p style="line-height:50%" ><br><br>&nbsp;</p>
@box[bg-royal text-white rounded my-box-pad2  ](<p style="line-height:70%" ><span style="font-size:0.9em; font-weight: bold;" >Basic driver libraries/headers<br>&nbsp;</span></p>)
<br>
@snapend


@snap[north-west span-70 fragment]
<br>
<br>
<br>
<br>
<br>
<br>
<p style="line-height:50%" ><br>&nbsp;<br>&nbsp;</p>
@box[bg-purple-pp text-white rounded my-box-pad2  ](<p style="line-height:70%" ><span style="font-size:0.9em; font-weight: bold;" > Skeletons for common driver functions<br>&nbsp;</span></p>)
<br>
@snapend



@snap[north-east span-90 fragment]
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<p style="line-height:50%" ><br>&nbsp;<br>&nbsp;</p>
@box[bg-navy text-white rounded my-box-pad2  ](<p style="line-height:80%" ><span style="font-size:0.9em; font-weight: bold;" >Error values until ported EFI_UNSUPPORTED, EFI_DEVICE_ERROR<br>&nbsp;</span></p>)
<br>
@snapend





Note:
- Establishes a proper UEFI Driver Entry Point
- References to basic driver libraries/headers based on Driver Wizard form input
- Inserted in .INF, .H and .C files
- Skeletons for common driver functions
- Includes comments based on information from the Driver Writer’s Guide for UEFI 2.3.1
- Functions may return error values until ported : (EFI_UNSUPPORTED, EFI_DEVICE_ERROR)



---?image=/assets/images/slides/Slide_LabSec.JPG
@title[Lab 1: Create a UEFI Driver section]
<br>
<br>
<p align="Left"><span class="gold" >Lab 1: Create a UEFI Driver with the UEFI Driver Wizard </span></p>
<br>
<div class="left1">
<ul>
  <li><span style="font-size:0.8em" >In this lab, you'll create a new UEFI driver using the UEFI Driver Wizard.</span></li>
  <li><span style="font-size:0.8em" >This will create a set of "c" code files to be used as a template UEFI Driver used in the subsequent driver labs</span></li>

</ul>
</div>
<div class="right1">
<span style="font-size:0.8em" >&nbsp;  </span>
</div>
 
Note:
---
@title[Lab 1: Install UEFI Driver Wizard, Python & wxPython ]
<br>
<p align="right"><span class="gold" >Lab 1: Install UEFI Driver Wizard, Python & wxPython</span></p>
<ol>
   <li><span style="font-size:0.8em" >Perform <a href="https://gitpitch.com/tianocore-training/Platform_Build_LAB/master#/">Lab Setup</a> from previous Labs  </span></li>
   <li><span style="font-size:0.8em" >From the `~FW/DriverWizard` folder, copy and paste folder “`~FW/DriverWizard/UefiDriverWizard`” to `~$Home`  </span></li>
   <li><span style="font-size:0.8em" >Check  if version 2.7.x is the default of Python from Terminal Prompt </span></li>
   <ul style="list-style-type:none">
       <li><span style="font-size:0.6em" ><span style="background-color: #101010">`bash$ python –V`&nbsp;&nbsp;</span></span></li>
       <li><span style="font-size:0.6em" ><span style="background-color: #300a24">`Python 2.7.12`&nbsp;&nbsp;&nbsp;&nbsp;</span></span></li>
   </ul>
   <li><span style="font-size:0.8em" >Install the wxPython  (Version 3.0 ) </span></li>
   <ul style="list-style-type:none">
       <li><span style="font-size:0.6em" ><span style="background-color: #101010">`bash$ sudo apt-get install python-wxgtk3.0` &nbsp;&nbsp;</span></span></li>
   </ul>
</ol>

Note:

same as slide


---?image=/assets/images/slides/Slide16.JPG
@title[Lab 1: UefiDriverWizard -Select Work Space]
<p align="right"><span class="gold" >Lab 1: UefiDriverWizard -Select Work Space</span></p>

Note:
- Terminal Prompt (Cnt-Alt-T)
  - `bash$ cd ~UefiDriverWizard`
  - `bash$ python launch.py`

- Select a Work Space
- Control+O – to  browse for a directory

- Browse to ~src/edk2 

- Select Open



---?image=/assets/images/slides/Slide18.JPG
@title[Lab 1: -Create a New UEFI Driver]
<p align="center"><span class="gold" >Lab 1: Create a <u>N</u>ew UEFI Driver</span></p>

Note:
- Control+N – to Open Menu 


---?image=/assets/images/slides/Slide20.JPG
@title[Lab 1: New UEFI Driver Menu]
<p align="left"><span class="gold" >&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp; &nbsp;Lab 1:</span></p>
<p align="left"><span class="gold" >New UEFI Driver Menu</span></p>
<div class="left1">
<ul style="list-style-type:disc">
  <li><span style="font-size:0.7em" >“UEFI Driver Path” – Type: <b>“MyWizardDriver”</b></span>  </li>
    <ul style="list-style-type:none">
     <li><span style="font-size:0.5em" >&nbsp;&nbsp;<i>Note:</i> “UEFI Driver Name” is filled in </span>  </li>
  </ul>
 <li><span style="font-size:0.7em" ><b>Ensure</b> all the forms, radio buttons, and boxes are filled in and <b>selected exactly</b> like the image to the right.</span>  </li>
 <br>
 <li><span style="font-size:0.65em" ><i>Note:</i>A new, specific driver GUID will populate, so it will be different than this image</span>  </li>
   <br>
  <ul style="list-style-type:none">
       <li><span style="font-size:0.8em" >&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp; &nbsp; <b>Click</b>  </li>
  </ul>
</ul>
</div>
<div class="right1">
<ul style="list-style-type:none">
  <li><span style="font-size:0.8em" >&nbsp;  </li>
</ul>
</div>

Note:
- “UEFI Driver Version” – Type: “1.0”
- “UEFI Driver Type” – Select: “UEFI Driver Model Device Driver”
- “Opetional Features …” – Select:
  - 	Unloadable
  - 	Driver Supporte EFI Version Protocol
  - 	HII Packages for Strings, Fonts, or images
- “CPU Architecture” – Select: “IA32” and “X64”





---?image=/assets/images/slides/Slide22.JPG
@title[Lab 1: UEFI Driver Model Optional Features]
<br>
<p align="left"><span class="gold" >Lab 1: UEFI Driver Model Optional Features</span></p>
<div class="left1">
<ul style="list-style-type:none">
  <li><span style="font-size:0.8em" ><b>Ensure</b> all the forms, radio buttons, and boxes are filled in and <b>selected exactly</b> like the image to the right.</span>  </li>
  <br>
  <br>
  <li><span style="font-size:0.6em" >&check;&nbsp;&nbsp;"Componnt Name 2 Prorocol”  </span>  </li>
  <li><span style="font-size:0.6em" >&check;&nbsp;&nbsp;"Componnt Name Prorocol”   </span>  </li>
  <li><span style="font-size:0.6em" >&check;&nbsp;&nbsp;"HII Packages for Forms . . .”  </span>  </li>
  <br>
  <br>
  <li><span style="font-size:0.8em" >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp; &nbsp;&nbsp;&nbsp; &nbsp; &nbsp; <b>Click</b>  </li>
 </ul>
</div>
<div class="right1">
<ul style="list-style-type:none">
  <li><span style="font-size:0.8em" >&nbsp;  </li>
</ul>
</div>

Note:

- UEFI Driver Model Opetional Features  – Select:
  -	Componnt Name 2 Prorocol
  -	Componnt Name 2 Prorocol
  -	HII Packages for Forms and HII based configuruation





---?image=/assets/images/slides/Slide24.JPG
@title[Lab 1: UEFI Driver Consumed Protocol]
<br>
<p align="left"><span class="gold" >Lab 1: UEFI Driver Consumed Protocol</span></p>
<span style="font-size:0.8em" ><b>Select</b></span> <br>
<span style="font-size:0.7em" >&check;&nbsp;&nbsp;"PCI Driver that consumes the PCI I/O Protocol”  </span>  
<div class="left1">
<ul style="list-style-type:none">
  <br>
  <br>
  <br>
  <br>
  <br>
  <br>
  <br>
  <br>
  <li><span style="font-size:0.8em" >&nbsp;&nbsp; &nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp; &nbsp; <b>Click</b>  </li>
</ul>
</div>
<div class="right1">
<ul style="list-style-type:none">
  <li><span style="font-size:0.8em" >&nbsp;  </li>
</ul>
</div>

Note:

Same as slide





---?image=/assets/images/slides/Slide26.JPG
@title[Lab 1: UEFI Driver Produced Protocols]
<p align="right"><span class="gold" >Lab 1: UEFI Driver Produced Protocols</span></p>
<br>
<div class="left1">
<ul style="list-style-type:none">
  <li><span style="font-size:0.8em" ><b>Select</b></span>  </li>
  <li><span style="font-size:0.7em" >&check;&nbsp;&nbsp;"Byte stream device (i.e.UART) &nbsp; <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; producing Serial I/O Protocol”  </span>  </li>
  <br>
  <br>
  <br>
  <br>
  <br>
  <br>
  <br>
  <li><span style="font-size:0.8em" >&nbsp;&nbsp; &nbsp; &nbsp;&nbsp;&nbsp; &nbsp; &nbsp; <b>Click</b>  </li>
</ul>
</div>
<div class="right1">
<ul style="list-style-type:none">
  <li><span style="font-size:0.8em" >&nbsp;  </li>
</ul>
</div>

Note:

Same as slide



---?image=/assets/images/slides/Slide28.JPG
@title[Lab 1: UEFI Driver Created]
<br>
<p align="left"><span class="gold" >Lab 1: UEFI Driver Created</span></p>
<span style="font-size:0.8em" > UEFI Driver template created</span>

Note:

Same as slide

---  
@title[Summary]
<BR>
### <p align="center"><span class="gold"   >Summary </span></p><br>
<ul style="list-style-type:none">
 <li>@fa[certificate gp-bullet-cyan]<span style="font-size:0.9em">&nbsp;&nbsp;Setup the UEFI Driver Wizard</span></li><br>
 <li>@fa[certificate gp-bullet-yellow]<span style="font-size:0.9em">&nbsp;&nbsp;Create a UEFI Driver Template</span> </li>
</ul>


 

---?image=assets/images/gitpitch-audience.jpg
@title[Questions]
<br>
![Questions](/assets/images/questions.JPG) 


---?image=assets/images/gitpitch-audience.jpg
@title[Logo Slide]
<br><br><br>
![Logo Slide](/assets/images/TianocoreLogo.png =10x)


---
@title[Acknowledgements]
#### <p align="center"><span class="gold"   >Acknowledgements</span></p>

```c++
/**
Redistribution and use in source (original document form) and 'compiled' forms (converted
to PDF, epub, HTML and other formats) with or without modification, are permitted provided
that the following conditions are met:

Redistributions of source code (original document form) must retain the above copyright 
notice, this list of conditions and the following disclaimer as the first lines of this 
file unmodified.

Redistributions in compiled form (transformed to other DTDs, converted to PDF, epub, HTML
and other formats) must reproduce the above copyright notice, this list of conditions and 
the following disclaimer in the documentation and/or other materials provided with the 
distribution.

THIS DOCUMENTATION IS PROVIDED BY TIANOCORE PROJECT "AS IS" AND ANY EXPRESS OR IMPLIED 
WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND 
FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL TIANOCORE PROJECT BE 
LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES 
(INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, 
DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, 
WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) 
ARISING IN ANY WAY OUT OF THE USE OF THIS DOCUMENTATION, EVEN IF ADVISED OF THE POSSIBILITY 
OF SUCH DAMAGE.

Copyright (c) 2018, Intel Corporation. All rights reserved.
**/

```
