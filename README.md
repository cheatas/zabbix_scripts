Colletion of scripts that interact with zabbix.
<hr>

## License
The code in this repository is free to use for both personal and commerical use.
It is required to mention my name and Github username in any publications both online and offline.
Name: Yadvir Singh
Github: @cheatas


## `host_pull_zabbix.py`

Script to retrieve all hosts in the zabbix database and write them to the /etc/hosts file.
It is recommended to create a seperate API user with appropriate rights.

#### Usage

1. Fill in the required parameters; *zabbix_url*, *zabbix_username*, *zabbix_password*
2. Request the API token by uncommenting the line `print(get_api_token(zabbix_url))`. This will print the API token. 
3. Copy the printed API token and set the variable `api_token` to the aquired API token. The `print(get_api_token(zabbix_url))` line can be commented again. 
4. Uncomment the last two lines as described in the script in the second run. The /etc/hosts file should now be populated.

5. If you are on a RHEL based host instead of a Debian based host uncomment the lines after "#For RHEL based hosts" and comment the lines under "#For Debian based hosts"

#### Caveats

Each time you request a API token for a user, it is stored in de database and can accumulate over time and you will need to manually remove them from the database. 

#### Todo

- Make it more intuitive by checking if the user already has a API token and request one if neccery. This token can then be saved localy and in the next run the user is only reminded to remove its credentials.

- Sort hosts based on selectable parameter before its written to the host file. 
