Payload used
TF=$(mktemp).service 
echo '[Service] ExecStart=/bin/sh -c "cat /root/root.txt > /tmp/output"
[Install] 
WantedBy=multi-user.target' > $TF
/bin/systemctl link $TF
/bin/systemctl enable --now $TF can you explain this to me

This script creates and runs a systemd service that reads the contents of the `/root/root.txt` file and writes it to `/tmp/output`. Here's a breakdown of each part:

1. `TF=$(mktemp).service`: This creates a temporary file name using `mktemp` and stores it in the `TF` variable. The `.service` extension is added to indicate that this file is a systemd service unit file.
    
2. `echo '[Service] ...' > $TF`: This writes the systemd service unit configuration to the temporary file created in the previous step. The configuration specifies that when the service is started, it will execute the command `cat /root/root.txt > /tmp/output`.
    
3. `/bin/systemctl link $TF`: This creates a symbolic link from the temporary service unit file to the systemd service directory (`/etc/systemd/system/` on most systems), making the service available to systemd.
    
4. `/bin/systemctl enable --now $TF`: This enables and starts the newly created service. The `--now` option starts the service immediately after enabling it.
    

In summary, this script creates a systemd service that copies the contents of `/root/root.txt` to `/tmp/output` and then enables and starts the service.