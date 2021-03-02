<h1 align="center">bid-d/magento2-init</h1>

<div align="center">

  <img src="https://img.shields.io/badge/magento-2.X-brightgreen.svg?logo=magento&longCache=true&style=flat-square" alt="Supported Magento Versions" />
  <a href="https://GitHub.com/Naereen/StrapDown.js/graphs/commit-activity" target="_blank"><img src="https://img.shields.io/badge/maintained%3F-yes-brightgreen.svg?style=flat-square" alt="Maintained - Yes" /></a>
  <a href="https://opensource.org/licenses/MIT" target="_blank"><img src="https://img.shields.io/badge/license-MIT-blue.svg" /></a>
</div>

# Table of contents
- [Table of contents](#table-of-contents)
  - [Docker Network](#docker-network)
  - [Usage](#usage)
  - [Prerequisites](#prerequisites)
  - [Version Tested](#version-tested)
  - [Setup](#setup)
  - [Credits](#credits)
    - [Bidd Nguyen](#bidd-nguyen)
  - [License](#license)
    
## Docker Network
<img src="https://raw.githubusercontent.com/bid-d/magento2-init/master/developer/docs/magento-network.png" alt="network image"/>

## Usage

This configuration is used for setting up a full magento 2 local development.

Folders:

- `developer/bin`: Shell file for initializing project
- `developer/images`: Configuration files for container
- `developer/env`: env variable for setting project
- `developer/lib`: Contains init shell file which used to automate setting up project 

## Prerequisites

-  Operating systems (Linux x86-64): such as RedHat Enterprise Linux (RHEL), CentOS, Ubuntu, Debian, and similar
-  Memory requirement: At least 2GB Ram
-  Hard Drive: SSD is preferred over HDD
-  [Docker and Docker-compose installed (For Ubuntu)](https://docs.docker.com/engine/install/ubuntu/)
-  Composer pre-installed is not required

## Version Tested
- PHP: 7.2
- Magento: 2.3.2

## Setup

- In your project directory, run this to initialize required files:
```bash
foo@ubuntu:~$ curl -s https://raw.githubusercontent.com/bid-d/magento2-init/arrowhitech/developer/lib/init | bash -s
```
- You can edit ENV configuration file for your local setup:

`/env/magento.env` file
```env
MYSQL_DATABASE=magentodb
MYSQL_USER=bidd
MYSQL_PASSWORD=bidd

BASE_URL=magento2.local
```
- You can also change the default Mysql root password.

`.env` file
```env
MYSQL_ROOT_PASSWORD=root
```
- Clone your repo in to the current directory
```bash
git clone git@yourrepo.link
```
- Setup your magento site:
```bash
foo@ubuntu:~$ curl -s https://raw.githubusercontent.com/bid-d/magento2-init/arrowhitech/developer/lib/setup | bash -s
```

## Credits

### Bidd Nguyen
My name is Bidd Nguyen and I'm the author of this repo. I've been PHP Web Developer (Laravel/Magento) and DevOps for more than three years. You can contact me directly at biddqb@gmail.com

## License

[MIT](https://opensource.org/licenses/MIT)