# Check that it works

1. Make sure your dedicated "OctaPi" router is powered on and fully booted up, the **client** is booted with peripherals attached and the **server** is booted with only a power lead attached.

1. Open a terminal on the **client**

    ![Terminal](images/terminal.png)

1. Make sure you are in the `/home/pi` directory and type the following command to run the `compute.py` example software provided with the client software examples you downloaded earlier:

    ```bash
    sudo python3 compute.py
    ```

    **Important:** Use the version of `compute.py` from the OctaPi client software examples as this specifies the 192.168.1.* network. If you use the version that comes with Dispy, it will default to the wrong IP address for OctaPi.

    The `compute.py` Python script runs 15 jobs on your server, each are just random delays before returning. If the OctaPi is working correctly, the jobs will complete in about a minute and a table showing the statistics for the application will be shown in the terminal.

    If the `compute.py` script does not work, review your steps one by one and check that client, server, and router are all set up correctly and working properly.

1. If the test worked, use the client to manually shutdown the server (replacing <remote_ip> with the IP address of the **server** you noted down earlier)

    ```bash
    ssh <remote_ip>;
    sudo shutdown -HP now
    ```

    You may need to use **nmap** again to find the server IP address if it changed when the Wi-Fi router rebooted.

    In future we will be using the `cluster_action.sh` script to do this.

1. Once the server is shutdown, remove the micro SD card.

1. Using an SD card duplicator or a computer which is able to read SD cards, create seven more identical copies of this SD card and insert these into the other servers so that you have a total of eight.