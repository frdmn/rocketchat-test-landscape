# rocketchat-test-landscape

This project includes pre-configured services (currently just LDAP) that are used within, and tested against a Rocket.Chat system.

## Installation

1. Make sure you've installed all requirements
2. Clone this repository:

    ```shell
    git clone https://github.com/frdmn/rocketchat-test-landscape
    ```

3. Install the project using `make`:

    ```shell
    docker-compose up -d
    ```

## Usage / Instructions

### LDAP

#### OpenLDAP

* Domain: `rocket.chat`
* Admin LDAP Bind: `cn=admin,dc=rocket,dc=chat`
* Admin LDAP Password: `RocketChatLDAPadmin`
* Employee users password: `Password1`

##### Configuration within Rocket.Chat

* Enable: `true`
* Host: Your LAN IP, e.g. `192.168.1.48` (Do not use `localhost` if RC is dockerized!)
* Port:
  * `389` for regular LDAP
  * `636` for encrypted LDAPS
* Encryption:
  * `No encrpytion` for regular LDAP
  * `SSL/LDAPS` for encrypted LDAPS
* Reject Unauthorized: `false` (in case of encrypted LDAPS)
* Base DN: `dc=rocket,dc=chat`
* Internes Log-Level: `Info`
* Auth -> User DN: `cn=admin,dc=rocket,dc=chat`
* Auth -> Password: `RocketChatLDAPadmin`
* Sync -> Username Field: `uid`
* Sync -> Default Domain: `rocket.chat`
* Sync -> Merge Existing Users: `true`
* User Search -> Filter: `(objectclass=*)`
* User Search -> Search Field: `uid,mail`

_Note_: Since the LDAP tree contains 1000 users, it takes about 3 minutes until the synchronization is finished!

## Contributing

1. Fork it
2. Create your feature branch:

    ```shell
    git checkout -b feature/my-new-feature
    ```

3. Commit your changes:

    ```shell
    git commit -am 'Add some feature'
    ```

4. Push to the branch:

    ```shell
    git push origin feature/my-new-feature
    ```

5. Submit a pull request

## Requirements / Dependencies

* Docker
* `docker-compose`
* running Rocket.Chat test system

## Version

1.0.0

## License

[MIT](LICENSE)
