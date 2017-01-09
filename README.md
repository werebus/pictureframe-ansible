*   Prepaire SD Card
    ```
    $ ansible-playbook -K prep_micro_sd.yml
    ```

*   Bootstrap Pi

    The 'SSH pasword' is `alarm`, and the 'SUDO password' is `root` (don't
    worry, we'll change that in the next step).

    ```
    $ ANSIBLE_HOST_KEY_CHECKING=False ansible-playbook -k -K bootstrap.yml
    ```

*   Run the main playbook

    ```
    $ ansible-playbook main.yml
    ```
