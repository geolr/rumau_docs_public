# cmd

See the free space on shared storage/network drives: 
`dir <G:\...path>` should show free space in bytes

tree (also tree /f ?)

# PowerShell

`tnc` check for Test-NetConnection, includes ping, traceroute, ...

Simple list of directory contents:
`Get-ChildItem "G:\EXP\NO_Central_South_Africa\ArcGIS" | Format-Table Name`

Get a files properties, owner, size in GB
`Get-Item "C:\Path\To\Your\File.txt" | Select-Object Name, @{Name="SizeGB";Expression={[math]::Round($_.Length / 1GB, 2)}}, @{Name="Owner";Expression={(Get-Acl $_.FullName).Owner}}`

# File system

`\\\\?\\`, referred to as "extended length-path" is a prefix that can be used to circumvent the max-path-length limit in Windows

Show a MD5-hash value on the commandline, last argument is the type of hash: 
`certutil -hashfile "path to your file" MD5`

# Power Apps

## Source of data: Sharepoint list

Put some thought in 

Use the Settings view of the list to make sure by hover what the actual name of the column to use is. As the names can be changed later
