# zilminer

> Zilliqa miner with OpenCL and CUDA support.

**zilminer** is an Ethash GPU mining worker that support Zilliqa's Proof-of-Work process. 

This project is a fork of [ethminer](https://github.com/ethereum-mining/ethminer). Please do see [ethminer README](ethminer.README.md) for more details.

## Features

* Zilliqa Getwork protocol
* All ethminer features 


## Install

Standalone **executables** for *Linux*, *macOS* and *Windows* are provided in
the [Releases] section.
Download an archive for your operating system and unpack the content to a place
accessible from command line. After which, the zilminer will be ready to go.


## Usage

The **zilminer** is a command line program. This means you will have to launch it either
from a Windows command prompt or Linux Bash console. You can also create shortcuts to
predefined commands using a Linux Bash script or Windows batch/cmd file.
For the full list of available commands, please enter the following:

```sh
zilminer --help
```

## Settings on Zilliqa Node
1. Setup Zilliqa Node by following the [Zilliqa Mining Guide](https://github.com/Zilliqa/Zilliqa/wiki/Mining)
2. Change the `constants.xml` for the following parameter:
    * Set `GETWORK_SERVER_MINE` to `true`.
    * Set `GETWORK_SERVER_PORT` to the port you will be using to GetWork. (default is `4202`)
    * Set the other mining parameters to `false`:
       ```
       <CUDA_GPU_MINE>false</CUDA_GPU_MINE>
       <FULL_DATASET_MINE>false</FULL_DATASET_MINE>
       <OPENCL_GPU_MINE>false</OPENCL_GPU_MINE>
       <REMOTE_MINE>false</REMOTE_MINE>
       ```
3. Launch your node and find out your IP address with the following command:
    ```
    curl https://ipinfo.io/ip
    ```

## Settings on zilminer client

Key in the following command in your command prompt:
```sh
zilminer --max-submit=1 --farm-recheck 10000 --work-timeout=7200 --farm-retries=10 --retry-delay=10 \
         --ergodicity=2 -P zil://wallet_address.worker_name@zil_node_ip:get_work_port
```
> Please change the *wallet_address*, *worker_name*, *zil_node_ip*, and *get_work_port* accodingly.

* For `wallet_address`: You can use the [Zilliqa Wallet](https://wallet.zilliqa.com/) to create a new keypair and a Zilliqa address.
* For `worker_name` You can key in any abitrary worker name you desire.
* For `zil_node_ip`: Please key in the IP address of the Zilliqa node.
* For `get_work_port`: Please key in the port used in `GETWORK_SERVER_PORT`. Default is `4202`.

## Build

### Building from source

See [docs/BUILD.md](docs/BUILD.md) for build/compilation details.
