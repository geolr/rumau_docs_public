# Nextcloud

## snap
sudo snap refresh --channel=
is the way to upgrade to newer channel. worked nicely

## backing up
spinning disk WD PiDrive 

try this:
'ssh user@remote_host "tar -czvf - /remote/source/directory/" > /media/usb_drive/directory.tar.gz'