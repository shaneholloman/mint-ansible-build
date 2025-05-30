<img src="/logos/vercel.png" alt="vercel logo" width="100" height="100">

# Vercel role

Manage Vercel domain and dns entries.

## Usage

Configure the role.

```yml
vercel_token: # default: "{{ vault_vercel_token }}"
vercel_team_id: example-organization
vercel_dns:
  - domain: example.com
    records:
      - { name: www, type: ALIAS, value: www.example.com, state: present }
      - { name: '', type: A, value: 93.184.216.34, state: present }
```

And include it in your playbook.

```yml
- hosts: vercel
  roles:
  - role: vercel
```
