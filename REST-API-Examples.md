### Version: Ansible Tower >= 3.3.x 

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


