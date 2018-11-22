### Version: Ansible Tower >= 3.2.x 

## REST API examples using curl:

- Request to see ping endpoint details:

`# curl -k https://tower_server/api/v2/ping/`

### *Store Tower Credential in a specific path*

`# cat credential_path.json`

`{ 
"username": "admin",
"password": "password" 
}`

- Request to get token:

`# curl -X POST -k -v -H 'Content-Type: application/json' --data @credential_path.json https://tower_server/api/v2/authtoken/`

- Request to update Tower License:

`# cat license_path.txt
{
    "company_name": "Ansible",
    "contact_email": "ansibler@ansible.com",
    "contact_name": "xxxx",
    "hostname": "x.x.x.x",
    "instance_count": 4000,
    "license_date": 1504099406,
    "license_key": "osietgidfighfdkutghoihgodsijhgdhfglfdu",
    "license_type": "enterprise",
    "subscription_name": "Ansible Tower by Red Hat, Standard (4000 Managed Nodes)",
    "eula_accepted": "True"
}`

`# curl -X POST  -k -v -H 'Content-Type: application/json' -H 'Authorization: Token a8dfdfdfdfdfdfdfd14ab1257f59b40d54294' --data @license_path.txt https://tower_url/api/v2/config/`
