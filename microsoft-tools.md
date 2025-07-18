# cmd

See the free space on shared storage/network drives: 
`dir <G:\...path>` should show free space in bytes

tree (also tree /f ?)

# PowerShell

`tnc` check for Test-NetConnection, includes ping, traceroute, ...

Get a files properties, owner, size in GB
`Get-Item "C:\Path\To\Your\File.txt" | Select-Object Name, @{Name="SizeGB";Expression={[math]::Round($_.Length / 1GB, 2)}}, @{Name="Owner";Expression={(Get-Acl $_.FullName).Owner}}`

# File system

`\\\\?\\`, referred to as "extended length-path" is a prefix that can be used to circumvent the max-path-length limit in Windows

`certutil -hashfile "path to your file" MD5`

# Power Apps

## Source of data: Sharepoint list

Put some thought in 

Use the Settings view of the list to make sure by hover what the actual name of the column to use is. As the names can be changed later
