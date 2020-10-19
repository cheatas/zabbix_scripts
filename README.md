

Colletion of scripts that interact with zabbix.
<hr>


## `host_pull_zabbix.py`

Script to retrieve all hosts in the zabbix database and write them to the /etc/hosts file.
It is recommended to create a seperate API user with appropriate rights.

#### Usage

1. Fill in the required parameters; *username*, *password*, *zabbix_url*
2. Request the API token by uncommenting the line `print(get_api_token(zabbix_url))`. This will print the API token. 
3. Copy the printed API token and set the variable `api_token` to the aquired API token. The `print(get_api_token(zabbix_url))` line can be commented again. 
4. Uncomment 2 last lines and in the following run, the /etc/hosts file shoudl be populated


#### Caveats

Each time you request a API token for a user, it is stored in de database and can accumulate over time and you will need to manually remove them from the database. 

#### Todo

- Make it more intuitive by checking if the user already has a API token and request one if neccery. This token can then be saved localy and in the next run the user is only reminded to remove its credentials.

- Sort hosts based on selectable parameter before its written to the host file. 
