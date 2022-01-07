[comment]: # "Auto-generated SOAR connector documentation"
# MineMeld

Publisher: Splunk Community  
Connector Version: 1\.0\.1  
Product Vendor: Palo Alto Networks  
Product Name: MineMeld  
Product Version Supported (regex): "\.\*"  
Minimum Product Version: 4\.10\.0\.40961  

This app integrates with the Palo Alto Networks MindMeld threat intelligence processing tool to execute actions like 'upload indicator'

### Configuration Variables
The below configuration variables are required for this Connector to operate.  These variables are specified when configuring a MineMeld asset in SOAR.

VARIABLE | REQUIRED | TYPE | DESCRIPTION
-------- | -------- | ---- | -----------
**endpoint** |  required  | string | Endpoint URL
**username** |  required  | string | Username
**password** |  required  | password | Password

### Supported Actions  
[test connectivity](#action-test-connectivity) - Test connectivity  
[upload file](#action-upload-file) - Upload a file in the given node name  
[process indicator](#action-process-indicator) - Send indicator\(s\) to given node name \(blacklist, whitelist, etc\)  

## action: 'test connectivity'
Test connectivity

Type: **investigate**  
Read only: **True**

#### Action Parameters
No parameters are required for this action

#### Action Output
No Output  

## action: 'upload file'
Upload a file in the given node name

Type: **generic**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**vault\_id** |  required  | Vault ID of file to detonate | string |  `vault id` 
**node\_name** |  required  | Target Node Name \(For Example\: wlWhiteListIPv4\) | string | 
**file\_type** |  optional  | File type | string |  `file type` 
**dry\_run** |  optional  | Dry Run | boolean | 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.parameter\.dry\_run | boolean | 
action\_result\.parameter\.file\_type | string |  `file type` 
action\_result\.parameter\.node\_name | string | 
action\_result\.parameter\.vault\_id | string |  `vault id` 
action\_result\.data | string | 
action\_result\.summary | string | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'process indicator'
Send indicator\(s\) to given node name \(blacklist, whitelist, etc\)

Type: **investigate**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**indicator** |  required  | Indicator such as IP, Domain, or Url | string | 
**node\_name** |  required  | Target Node Name | string |  `file name` 
**file\_type** |  optional  | File type | string |  `file type` 
**dry\_run** |  optional  | Dry Run | boolean | 
**share\_level** |  optional  | Share Level | string | 
**is\_remove** |  optional  | Remove Indicator | boolean | 
**is\_update** |  optional  | Update Indicator | boolean | 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.parameter\.dry\_run | boolean | 
action\_result\.parameter\.file\_type | string |  `file type` 
action\_result\.parameter\.indicator | string | 
action\_result\.parameter\.is\_remove | boolean | 
action\_result\.parameter\.is\_update | boolean | 
action\_result\.parameter\.node\_name | string |  `file name` 
action\_result\.parameter\.share\_level | string | 
action\_result\.data | string | 
action\_result\.summary | string | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric | 