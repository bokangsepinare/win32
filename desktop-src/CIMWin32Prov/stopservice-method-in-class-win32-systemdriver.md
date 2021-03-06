---
Description: Places the service represented by the Win32\_SystemDriver object in the stopped state.
ms.assetid: 0fa8ef44-39eb-448e-8d33-38a5af9a0c13
ms.tgt_platform: multiple
title: StopService method of the Win32_SystemDriver class (Sdoias.h)
ms.topic: reference
ms.date: 05/31/2018
topic_type: 
- APIRef
- kbSyntax
api_name: 
- Win32_SystemDriver.StopService
api_type: 
- COM
api_location: 
- CIMWin32.dll
---

# StopService method of the Win32\_SystemDriver class

The **StopService** [WMI class](https://docs.microsoft.com/windows/desktop/WmiSdk/retrieving-a-class) method places the service represented by the [**Win32\_SystemDriver**](win32-systemdriver.md) object in the stopped state.

This topic uses Managed Object Format (MOF) syntax. For more information about using this method, see [Calling a Method](https://docs.microsoft.com/windows/desktop/WmiSdk/calling-a-method).

## Syntax


```mof
uint32 StopService();
```



## Parameters

This method has no parameters.

## Return value

Returns a value of 0 (zero) if the service was successfully stopped, 1 (one) if the request is not supported, and any other number to indicate an error.

<dl> <dt>

**0**
</dt> <dd>

The request was accepted.

</dd> <dt>

**1**
</dt> <dd>

The request is not supported.

</dd> <dt>

**2**
</dt> <dd>

The user did not have the necessary access.

</dd> <dt>

**3**
</dt> <dd>

The service cannot be stopped because other services that are running are dependent on it.

</dd> <dt>

**4**
</dt> <dd>

The requested control code is not valid, or it is unacceptable to the service.

</dd> <dt>

**5**
</dt> <dd>

The requested control code cannot be sent to the service because the state of the service ([**Win32\_BaseService**](win32-baseservice.md).**State** property) is equal to 0, 1, or 2.

</dd> <dt>

**6**
</dt> <dd>

The service has not been started.

</dd> <dt>

**7**
</dt> <dd>

The service did not respond to the start request in a timely fashion.

</dd> <dt>

**8**
</dt> <dd>

An unknown failure occurred when starting the service.

</dd> <dt>

**9**
</dt> <dd>

The directory path to the service executable file was not found.

</dd> <dt>

**10**
</dt> <dd>

The service is already running.

</dd> <dt>

**11**
</dt> <dd>

The database to add a new service is locked.

</dd> <dt>

**12**
</dt> <dd>

A dependency for which this service relies on has been removed from the system.

</dd> <dt>

**13**
</dt> <dd>

The service failed to find the service needed from a dependent service.

</dd> <dt>

**14**
</dt> <dd>

The service has been disabled from the system.

</dd> <dt>

**15**
</dt> <dd>

The service does not have the correct authentication to run on the system.

</dd> <dt>

**16**
</dt> <dd>

This service is being removed from the system.

</dd> <dt>

**17**
</dt> <dd>

There is no execution thread for the service.

</dd> <dt>

**18**
</dt> <dd>

There are circular dependencies when starting the service.

</dd> <dt>

**19**
</dt> <dd>

There is a service running under the same name.

</dd> <dt>

**20**
</dt> <dd>

There are invalid characters in the name of the service.

</dd> <dt>

**21**
</dt> <dd>

Invalid parameters have been passed to the service.

</dd> <dt>

**22**
</dt> <dd>

The account which this service is to run under is either invalid or lacks the permissions to run the service.

</dd> <dt>

**23**
</dt> <dd>

The service exists in the database of services available from the system.

</dd> <dt>

**24**
</dt> <dd>

The service is currently paused in the system.

</dd> </dl>

## Examples

The following PowerShell code stops the "Microsoft USB Printer class" service.


```PowerShell
$usbPrintDriver = Get-WmiObject -query "SELECT * FROM Win32_SystemDriver WHERE Name = 'usbprint'"
$Return = $usbPrintDriver.StopService()
"Stop Service Called. Return value is " + $return.ReturnValue + "."
"To figure out what this means, go look at the docs above this code snippet."
```



## Requirements



|                                     |                                                                                         |
|-------------------------------------|-----------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista<br/>                                                                |
| Minimum supported server<br/> | Windows Server 2008<br/>                                                          |
| Namespace<br/>                | Root\\CIMV2<br/>                                                                  |
| Header<br/>                   | <dl> <dt>Sdoias.h</dt> </dl>     |
| MOF<br/>                      | <dl> <dt>CIMWin32.mof</dt> </dl> |
| DLL<br/>                      | <dl> <dt>CIMWin32.dll</dt> </dl> |



## See also

<dl> <dt>

[Operating System Classes](https://docs.microsoft.com/previous-versions//aa392727(v=vs.85))
</dt> <dt>

[**Win32\_SystemDriver**](win32-systemdriver.md)
</dt> </dl>

 

 




