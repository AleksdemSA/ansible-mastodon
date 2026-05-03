# ansible-mastodon
Ansible role for Mastodon

### Requirements

requirements.yml
```yml
- name: mastodon
  src: https://github.com/AleksdemSA/ansible-mastodon.git
  scm: git
```

### Settings

example of playbookMastodon.yml
```yml
---
- name: Update webservices on mst
  hosts: mastodon_server

  roles:
    - role: mastodon
      vars:
        mastodon_version: "version-v4.5.9"
        mastodon_domain: "mst.example.org"
        mastodon_net_subnet: "10.88.0.0/24"
        mastodon_ip_postgres: "10.88.0.2"
        mastodon_ip_redis: "10.88.0.3"
        mastodon_ip_app: "10.88.0.4"
        mastodon_ip_elastic: "10.88.0.5"
        mastodon_data_dir: "/data"
        mastodon_letsencrypt_dir: "/etc/letsencrypt"
        mastodon_postgres_user: "postgres"
        mastodon_postgres_db: "mstdatabase"
        mastodon_postgres_pass: "mstpass"
        mastodon_secret_key_base: "SECRET_KEY"
        mastodon_otp_secret: "OTP_SECRET"
        mastodon_active_record_primary_key: "PRIMARY_KEY"
        mastodon_active_record_deterministic_key: "DETERMINISTIC_KEY"
        mastodon_active_record_salt: "RECORD_SALT"
        mastodon_smtp_server: "smtp.example.org"
        mastodon_smtp_port: 25
        mastodon_smtp_login: "SMTP_LOGIN"
        mastodon_smtp_pass: "SMTP_PASS"
        mastodon_admin_email: "EMAIL"
        mastodon_health_check_retries: 15
        mastodon_health_check_delay: 10
        mastodon_daily_maintenance_minutes: "0"
        mastodon_daily_maintenance_hourses: "1,4,9,12,23"
```

### Run playbook

```sh
ansible-galaxy install -p roles -f -r requirements.yml
ansible-playbook playbookMastodon.yml
```
