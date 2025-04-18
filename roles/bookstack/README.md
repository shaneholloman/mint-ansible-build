<img src="/logos/bookstack.png" alt="bookstack logo" width="100" height="100">

# BookStack role

Deploy BookStack container.

## Usage

Configure the role.

```yml
bookstack_image: solidnerd/bookstack:0.27.5
bookstack_hostname: book01
bookstack_description: Wiki # default: BookStack
bookstack_data_dir: /usr/share/book # default: "/usr/share/{{ bookstack_hostname }}"
bookstack_app_url: "https://wiki.example.com"
bookstack_db_hostname: mysql01
bookstack_db_user: bookstack
bookstack_db_password: "{{ vault_mysql_password }}"
bookstack_db_name: bookstack
bookstack_mail_driver: smtp
bookstack_mail_hostname: mail.example.com
bookstack_mail_port: "587"
bookstack_mail_from: noreply@mexample.com
bookstack_mail_username: bot@example.com
bookstack_mail_password: "{{ vault_bookstack_mail_password }}"
bookstack_mail_encryption: tls
```

And include it in your playbook.

```yml
- hosts: bookstack
  roles:
  - role: bookstack
```