<h1 align="center">bid-d/magento2-init</h1>

<div align="center">

  <img src="https://img.shields.io/badge/magento-2.X-brightgreen.svg?logo=magento&longCache=true&style=flat-square" alt="Supported Magento Versions" />
  <a href="https://GitHub.com/Naereen/StrapDown.js/graphs/commit-activity" target="_blank"><img src="https://img.shields.io/badge/maintained%3F-yes-brightgreen.svg?style=flat-square" alt="Maintained - Yes" /></a>
  <a href="https://opensource.org/licenses/MIT" target="_blank"><img src="https://img.shields.io/badge/license-MIT-blue.svg" /></a>
</div>

# Table of contents
- [Table of contents](#table-of-contents)
  - [Usage](#usage)
  - [Prerequisites](#prerequisites)
  - [Setup](#setup)
    - [Automated Setup](#automated-setup)
    - [Manual Setup](#manual-setup)
  - [Credits](#credits)
    - [Bid-d Nguyen](#bid-d-nguyen)
  - [License](#license)
    
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

## Setup

You can either use [automated setup](#automated-setup) with default env values or [manual setup](#manual-setup) where you can defind your own env variable

### Automated Setup
Run this command line from the directory you want to install the project

```bash
curl -s https://raw.githubusercontent.com/bid-d/magento2-init/master/developer/lib/init | bash -s
```
This command above will install magento 2 project at your current directory with base url at https://magento2.local and version 2.4.1 with default values:

```env
MYSQL_HOST=mysql
MYSQL_ROOT_PASSWORD=root
MYSQL_DATABASE=magentodb
MYSQL_USER=bidd
MYSQL_PASSWORD=bidd

VERSION=2.4.1
BASE_URL=magento2.local
ADMIN_USER=admin
ADMIN_PASSWORD=admin123
ADMIN_FIRSTNAME=bidd
ADMIN_LASTNAME=bidd
ADMIN_EMAIL=bidd@admin.org

REDIS_HOST=redis

ELASTICSEARCH_HOST=elasticsearch
ELASTICSEARCH_PORT=9200
```

You can change the base url with `-d` flag and the version with `-v` flag:
```bash
curl -s https://raw.githubusercontent.com/bid-d/magento2-init/master/developer/lib/init | bash -s -- -d yourbaseurl -v version
```

### Manual Setup
```bash
# Get the repository
foo@ubuntu:~$ git clone https://github.com/bid-d/magento2-init.git

# CD to repository
foo@ubuntu:~$ cd magento2-init

# You nano or vim to edit env variables (I use vim in my case)
foo@ubuntu:~/magento2-init$ vim developer/env/magento.env

# Edit and save, then edit MYSQL_ROOT_PASSWORD if you want to change this default value too. Do not touch the COMPOSER_PATH for caching
foo@ubuntu:~/magento2-init$ vim developer/env/.env

# Copy manual setup shell script to current directory
foo@ubuntu:~/magento2-init$ cp developer/lib/init_manual .

# Execute the script
foo@ubuntu:~/magento2-init$ ./init_manual

# All done for manual installation, congrats!

```

## Credits

### Bid-d Nguyen
My name is Hung Nguyen and I'm the author of this repo. I've been PHP Web Developer (Laravel/Magento) and DevOps for more than three years. You can contact me directly at biddqb@gmail.com

## License

[MIT](https://opensource.org/licenses/MIT)
