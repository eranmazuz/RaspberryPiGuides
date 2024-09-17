# Secure ssh for raspberry pi
## Using PuttyGen to Generate an SSH Key Pair
1. Download and install putty
2. open `PuTTYgen`
3. We are going to choose the strongest encryption for the key in this time so for  `Type of key to generate` choose `ECDSA` and for `Curve to use for generating this key` choose `nistp521`
4. click on `Generate`
    ![](https://pimylifeup.com/wp-content/uploads/2018/05/01-PuttyGen.png)
5. Move your mouse across the window to generate random movements until the progress bar filled.
    ![](https://pimylifeup.com/wp-content/uploads/2018/05/02-PuttyGen-Generating-Key.png)
6. Give the `Key comment` a memorable name so you will know what it for.
7. fill the `Key passphrase` and `Confirm passphrase` with strong password.
8. click on `Save public key` and save the file in a secure location, give him memorable name `[file name]`
9. click on `Save private key` and save the file in a secure location, give him the same file name as the public key with the ending `.ppk` `[file name].ppk`
10. copy the public key from the application
   ![](https://pimylifeup.com/wp-content/uploads/2018/05/03-PuttyGen-Generated-Files.png)

## Setting the public SSH key on raspberry pi
1. log into the raspberry pi through the ssh
2. run `install -d -m 700 ~/.ssh`
3. run `nano ~/.ssh/authorized_keys` it will create the file if not exist and open it for editing.
4. paste the public key we copied into the file.
5. save the file press `ctrl + x` and then `Y` and then `enter`
6. run `sudo chmod 644 ~/.ssh/authorized_keys`
7. run `id [your username]`, you will get the username and it group.
8. run `sudo chown [your username]:[your user group] ~/.ssh/authorized_keys`

##Connecting to the raspberry pi through putty
1. open `PuTTY`
2. enter the ip address in the `Host Name` field.
3. in `Catgeory` go to `Connection` => `SSH` => `Auth` => `Credentials`
4. In the field `Private key file for authentication` put your private key
    ![](https://pimylifeup.com/wp-content/uploads/2019/03/Raspberry-Pi-SSH-Keys-02-Browse-To-key.jpg)
5. Save the new profile.

## disable the password login in the raspberry pi
1. log into the raspberry pi.
2. run `sudo nano /etc/ssh/sshd_config
3. search `#PasswordAuthentication yes` by using `ctrl + w`
4. replace `#PasswordAuthentication yes` with `PasswordAuthentication no`
5. search `#PubkeyAuthentication yes` by using `ctrl + w`
6. replace `#PubkeyAuthentication yes` with `PubkeyAuthentication yes`
7. save the file press `ctrl + x` and then `Y` and then `enter`
8. run `sudo reboot`