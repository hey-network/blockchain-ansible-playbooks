## Loom Testnet Non-validator node

1. Set up AWS credentials and save them under the `hey` profile name in `~/.aws/credentials`
2. Setup AWS VPC and note its id, subnet id, subnet cidr in the inventory file (both in the general vars and in the hosts description for the subnet)
2. Run playbook
    ```bash
    AWS_PROFILE=hey ansible-playbook -i inventory.yaml create-instances.yaml -vv
    ```
4. Update inventory with IP numbers
5. Provision loom
    ```bash
    AWS_PROFILE=hey ansible-playbook -i inventory.yml playbook.yml  --key-file ~/.ssh/loom_non_validator.pem --user ubuntu
    ```
