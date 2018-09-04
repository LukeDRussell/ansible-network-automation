# ansible-network-automation

A simple set of playbooks for learning how to use Ansible's network-engine based roles.

## Instructions for Use
1. Install ansible `pip install ansible` (Linux, MacOS, etc)
2. Clone this repository
3. Create a python environment and active it
4. Run `./setup_control_host.yaml` to install dependencies
5. Adjust your inventory file for your lab or test devices
6. Run `./get-facts.yaml` to test the repo and debug some of the collected structured data.