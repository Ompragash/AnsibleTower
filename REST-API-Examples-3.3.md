### Version: Ansible Tower >= 3.3.x 

For examples on Ansible Tower 3.2.x check this [link](https://github.com/Ompragash/AnsibleTower/blob/master/REST-API-EXAMPLES-3.2.md).

## REST API examples using curl:

- Request to see ping endpoint details:

`# curl -k https://tower_server/api/v2/ping/`

- Request to get token:

`# curl -k --user username:password -H "Content-Type: application/json" -X POST https://tower/api/v2/tokens/`

- Update an existing project in Ansible Tower:

`# curl -s -f -k -H "Authorization: Bearer token" -H 'Content-Type: application/json' -XPOST -d '{}' https://tower_server/api/v2/projects/ID/update/`

- Launch a job template in Ansible Tower:

`# curl -s -f -k -H "Authorization: Bearer token" -H 'Content-Type: application/json' -XPOST -d '{}' https://tower_server/api/v2/job_templates/ID/launch/`

- Launch a job template in Ansible Tower with variables pushed:

`# curl -s -f -k -H "Authorization: Bearer token" -H 'Content-Type: application/json' -XPOST -d '{"variable1": "value1", "variable2": "value2"}' https://tower_server/api/v2/job_templates/ID/launch/`

- Add a host to an inventory:

`# curl -s -f -k -H "Authorization: Bearer token" -H 'Content-Type: application/json' -XPOST -d '{ "name": "1.2.3.4", "description": "This is my new server", "inventory": "5", "enabled": true}' https://tower_server/api/v2/hosts/`

- Request to create a new organization:

`# curl -s -f -k -H "Authorization: Bearer token" -H 'Content-Type: application/json' -XPOST -d '{"name": "Org Name", "description": "Created using API"}' https://tower_server/api/v2/organizations/`

- Request to create a normal user:

`# curl -s -f -k -H "Authorization: Bearer token" -H 'Content-Type: application/json' -XPOST -d '{"username": "name", "first_name": "a", "last_name": "z", "is_superuser": false, "password": "$password", "email": "az@az.com"}' https://tower_server/api/v2/users/`

- Request to create a ad hoc command:

`# curl -s -f -k -H "Authorization: Bearer token" -H 'Content-Type: application/json' -XPOST -d '{"module_name": "dnf", "module_args": "name=htop state=latest", "inventory": 4, "credential": 1}' https://tower_server/api/v2/ad_hoc_commands/`

- Request to see standard output of a job:

`# curl --request GET   --url https://tower_server/api/v2/jobs/JOB_ID/stdout/?format=txt  --user username:password   --header 'content-type: text/plain' --insecure`
