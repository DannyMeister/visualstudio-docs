---
title: "WinCounter | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ff319ffc-f249-4c3f-9eb2-06e392e3ae80
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
translation.priority.ht: 
  - "cs-cz"
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "pl-pl"
  - "pt-br"
  - "ru-ru"
  - "tr-tr"
  - "zh-cn"
  - "zh-tw"
---
# WinCounter
The **WinCounter** option specifies a Windows or application performance counter to collect at set intervals during the profile run. Windows and application performance counters are listed as marks in the profiling data file. You can specify multiple performance counters to collect in separate options.  
  
 By default, counters are collected every 500 milliseconds. Use the **AutoMark** option to specify a different collection interval.  
  
 Only one **AutoMark** option is used. If multiple **AutoMark** options are specified, the last one is used.  
  
 The **WinCounter** option can only be used with the **Start** option.  
  
## Syntax  
  
```  
VSPerfCmd.exe /Start:Method /Wincounter:Path [/WinCounter:Path] [AutoMark:Milliseconds] [Options]  
```  
  
#### Parameters  
 `Path`  
 The Windows performance counter in PDH counter path format.  
  
## Required Options  
 The **WinCounter** option can only be used with the **Start** option.  
  
 **Start:** `Method`  
 The **Start** option initializes the profiler to the specified profiling method.  
  
## Exclusive Options  
 The **AutoMark** option can only be used with the **WinCounter** option.  
  
 **AutoMark:** `Milliseconds`  
 Specifies the number of milliseconds between Windows performance counter data collection.  
  
## Example  
 In the following example, two Windows performance counters are specified to be collected at an interval of 1000 milliseconds.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp /WinCounter:"\Processor(0)\% Processor Time" /WinCounter:"\System\Context Switches/sec" /AutoMark:1000  
```  
  
## See Also  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Profiling Stand-Alone Applications](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profiling ASP.NET Web Applications](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profiling Services](../profiling/command-line-profiling-of-services.md)