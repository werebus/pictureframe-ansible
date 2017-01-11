*   **Prepare SD Card** - performed on your local system.

    You will be promped for a device name; be very careful here, the entire
    device will be overwritten. This playbook also won't work if your SD card
    is a device like `mmcblk0`. This playbook replicates the steps [here][1].
    The Pi 1 uses a different fs image than the 2 and 3. Edit
    `group_vars/local.yml` as appropriate.

    ```
    $ ansible-playbook -K prep_micro_sd.yml
    ```

*   **Bootstrap the Pi.**

    You will be prompted for two passwords. The 'SSH pasword' is `alarm`, and
    the 'SUDO password' is `root` (don't worry, we'll change that in the next
    step, but you likely want to be behind NAT for this). This playbook does
    the minimum required to run Ansible "normally" - Installs python and sudo,
    and sets up a sudo-capable admin user.

    ```
    $ ANSIBLE_HOST_KEY_CHECKING=False ansible-playbook -k -K bootstrap.yml
    ```

*   **Run the main playbook.**

    ```
    $ ansible-playbook main.yml
    ```

[1]: https://archlinuxarm.org/platforms/armv8/broadcom/raspberry-pi-3
