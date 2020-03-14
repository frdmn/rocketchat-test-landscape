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
