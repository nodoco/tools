Setting up jupyter notebook server as service in Ubuntu 16.04

## Step 1: Verify the jupyter notebook location:

$ ll /home/avkash/.local/bin/jupyter-notebook
-rwxrwxr-x 1 avkash avkash 222 Jun 4 10:00 /home/avkash/.local/bin/jupyter-notebook*

## Step 2: Configure your jupyter notebook with password and ip address as needed and make sure where it exist. We will use this file as configuration for jupyter as service.

jupyter config: /home/avkash/.jupyter/jupyter_notebook_config.py

## Step 3: Create a file name jupyter.service as below and save it into /usr/lib/systemd/system/ folder.

$ cat /usr/lib/systemd/system/jupyter.service
>[Unit]
>Description=Jupyter Notebook

>[Service]
>Type=simple
>PIDFile=/run/jupyter.pid
># Step 1 and Step 2 details are here..
># ------------------------------------
>ExecStart=/home/avkash/.local/bin/jupyter-notebook --config=/home/avkash/.jupyter/jupyter_notebook_config.py
>User=avkash
>Group=avkash
>WorkingDirectory=/home/avkash/tools/notebooks
>Restart=always
>RestartSec=10
>#KillMode=mixed
>
>[Install]
>WantedBy=multi-user.target

## Step 4: Now enabled the service as below:

$ sudo systemctl enable jupyter.service

## Step 5: Now enabled the service as below:

$ sudo systemctl daemon-reload

## Step 6: Now enabled the service as below:

$ sudo systemctl restart jupyter.service
The service is started now. You can test it as below:

$ systemctl -a | grep jupyter
 jupyter.service      loaded active running Jupyter Notebook
Thats it, enjoy!!

## Step 7: set up stable password

> jupyter notebook password
> Enter password:  ****
> Verify password: ****
> [NotebookPasswordApp] Wrote hashed password to /Users/you/.jupyter/jupyter_notebook_config.json

### 参考：
1. https://aichamp.wordpress.com/2017/06/13/setting-up-jupyter-notebook-server-as-service-in-ubuntu-16-04/
2. https://jupyter-notebook.readthedocs.io/en/stable/public_server.html

