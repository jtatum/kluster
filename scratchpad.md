    ansible all -m ping

    ansible all -bm reboot

    ansible-playbook kluster.yaml --skip-tags slow

    ansible rpi1 -m ansible.builtin.setup

    ansible-galaxy install -r requirements.yaml
