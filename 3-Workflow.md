# How Jenkins Work:
##Pipeline Architecture (How all works)

```hcl
Developer → Push code → GitHub
                         ↓
                      Jenkins
                (Pipeline Triggered)
                         ↓
                 Maven Build (.war)
                         ↓
                    Ansible
                         ↓
               Deploy to Web Server
                         ↓
                 Application Live

```                 