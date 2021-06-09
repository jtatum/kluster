    ansible all -m ping

    ansible all -bm reboot

    ansible-playbook site.yaml

    ansible rpi1 -m ansible.builtin.setup

    ansible-galaxy install -r requirements.yaml
