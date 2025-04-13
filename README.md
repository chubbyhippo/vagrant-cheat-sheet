# Vagrant Commands Cheat Sheet

Vagrant is a tool for building and managing virtual machine environments. Below is a list of commonly used Vagrant commands to help you get started and work efficiently.

## General Commands

| Command                               | Description                                                                  |
|---------------------------------------|------------------------------------------------------------------------------|
| `vagrant init`                        | Initializes a new Vagrant environment by creating a `Vagrantfile`.          |
| `vagrant up`                          | Starts and provisions the virtual machine.                                  |
| `vagrant ssh`                         | SSH into the running virtual machine.                                       |
| `vagrant halt`                        | Stops the running virtual machine.                                          |
| `vagrant reload`                      | Restarts the virtual machine. Useful after changes to the `Vagrantfile`.    |
| `vagrant provision`                   | Re-runs provisioners (e.g., shell scripts, Ansible, Puppet) on the VM.      |
| `vagrant destroy`                     | Stops and deletes all resources created for the VM.                         |
| `vagrant status`                      | Shows the status of the VM (e.g., running, stopped).                        |
| `vagrant global-status`               | Lists all Vagrant environments on your system.                              |

## Networking Commands

| Command                               | Description                                                                  |
|---------------------------------------|------------------------------------------------------------------------------|
| `vagrant port`                        | Displays the list of forwarded ports.                                       |
| `vagrant ssh -c "<command>"`          | Runs a command on the VM directly via SSH.                                  |
| `vagrant share`                       | Shares the current environment using HashiCorp's Vagrant Share service.     |

## Box and Plugin Commands

| Command                               | Description                                                                  |
|---------------------------------------|------------------------------------------------------------------------------|
| `vagrant box add [box-name]`          | Downloads and adds a new box to your Vagrant installation.                   |
| `vagrant box list`                    | Lists all available boxes on your system.                                   |
| `vagrant box remove [box-name]`       | Removes a specific box from your system.                                    |
| `vagrant plugin install [plugin]`     | Installs a Vagrant plugin.                                                  |
| `vagrant plugin list`                 | Lists all installed Vagrant plugins.                                        |
| `vagrant plugin uninstall [plugin]`   | Uninstalls a specific Vagrant plugin.                                       |

## Snapshot Commands

| Command                               | Description                                                                  |
|---------------------------------------|------------------------------------------------------------------------------|
| `vagrant snapshot save [name]`        | Saves the current state of the VM as a snapshot.                            |
| `vagrant snapshot list`               | Lists all snapshots.                                                        |
| `vagrant snapshot restore [name]`     | Restores the VM to a specific snapshot.                                     |
| `vagrant snapshot delete [name]`      | Deletes a specific snapshot.                                                |

## Debugging and Logs

| Command                               | Description                                                                  |
|---------------------------------------|------------------------------------------------------------------------------|
| `vagrant --version`                   | Shows the Vagrant version installed.                                        |
| `vagrant validate`                    | Validates the `Vagrantfile` for syntax errors.                              |
| `vagrant reload --provision`          | Restarts the VM and runs provisioners again.                                |
| `vagrant ssh-config`                  | Outputs the SSH configuration for connecting to the VM manually.            |
| `vagrant destroy -f`                  | Forcefully destroys the VM without a confirmation prompt.                   |

---

## Useful Tips

1. **Custom Vagrantfile Path**  
   Initialize or use a custom `Vagrantfile` with the following command:  
   ```
   vagrant up --vagrantfile=path/to/Vagrantfile
   ```

2. **Debugging Vagrant**  
   Run Vagrant with increased verbosity for debugging using the `--debug` flag:  
   ```
   vagrant up --debug
   ```

3. **Synced Folders**  
   Use the host folder to sync files with the VM by editing your `Vagrantfile`:
   ```ruby
   config.vm.synced_folder "./host_folder", "/vm_folder"
   ```

4. **Pausing VMs**  
   Use `vagrant suspend` to save the current VM state and release system resources.
