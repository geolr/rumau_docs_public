# Comparing

Listing, not any changes to filesystem

`robocopy "C:\Folder1" "C:\Folder2" /L /MIR /NJH /NJS /NP /NS /NC /NDL`

/L — List only: Shows what would be copied, but doesn’t actually copy.

/MIR — Mirror: Compares all files and subfolders recursively.

/NJH — No job header.

/NJS — No job summary.

/NP — No progress.

/NS — No size info.

/NC — No class (file type).

/NDL — No directory list.

This command will output a list of files that exist in Folder1 but not in Folder2, or are different in size or timestamp.

🧾 **What Robocopy Can Compare:**
File presence (missing or extra files)
File size differences
Timestamps (modified date)
Folder structure
Attributes (read-only, hidden, etc.)

🚫 **What Robocopy Cannot Compare Directly:**
File ownership
File permissions (ACLs) — unless you use /COPYALL or /SEC during actual copying
File content (e.g., hash comparison)

/LOG:comparison.txt save the output to file

Check more on /FFT (File Fidelity Tolerance)


# PowerShell
To compare the timestamps:
`(Get-ChildItem "G:\Sub_Appl_Data\HampsonRussel\SVG\GECA\2023\Bl31_21_General.prj\messages").LastWriteTimeUtc.Ticks`

`(Get-ChildItem "G:\Sub_Appl_Data\HampsonRussel\SWEC\africa_w\GECA\2023\Bl31_21_General.prj\messages").LastWriteTimeUtc.Ticks`

On-prem is more precise compared to SWEC!
