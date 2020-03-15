# Magento Assessment
Magento Assessment for MPCJ

#### Following are the steps to install the application on your local environment.

# 1. Download or clone the repository
The first step is to download the project to your local computer, which can be done either by clicking on the "Clone or download" button and clicking on "Download Zip" or you can clone it to the public folder of your local development server on your system by opening the command promt and executing the git clone command.
```
git clone https://github.com/badarkhan1/MagentoAssessment.git
```

# 2. Setup the environment file
Go to app/etc and create the env.php file and copy paste the following code, which also contains the database information.
```
<?php
return [
    'backend' => [
        'frontName' => 'admin_73qdhe'
    ],
    'crypt' => [
        'key' => 'a96736df11ecdd399d650592d0010b62'
    ],
    'db' => [
        'table_prefix' => '',
        'connection' => [
            'default' => [
                'host' => 'localhost',
                'dbname' => 'magentodb',
                'username' => 'root',
                'password' => '',
                'active' => '1',
                'driver_options' => [
                    1014 => false
                ],
                'model' => 'mysql4',
                'engine' => 'innodb',
                'initStatements' => 'SET NAMES utf8;'
            ]
        ]
    ],
    'resource' => [
        'default_setup' => [
            'connection' => 'default'
        ]
    ],
    'x-frame-options' => 'SAMEORIGIN',
    'MAGE_MODE' => 'default',
    'session' => [
        'save' => 'files'
    ],
    'cache' => [
        'frontend' => [
            'default' => [
                'id_prefix' => '6bc_'
            ],
            'page_cache' => [
                'id_prefix' => '6bc_'
            ]
        ]
    ],
    'lock' => [
        'provider' => 'db',
        'config' => [
            'prefix' => ''
        ]
    ],
    'cache_types' => [
        'config' => 1,
        'layout' => 1,
        'block_html' => 1,
        'collections' => 1,
        'reflection' => 1,
        'db_ddl' => 1,
        'compiled_config' => 1,
        'eav' => 1,
        'customer_notification' => 1,
        'config_integration' => 1,
        'config_integration_api' => 1,
        'google_product' => 1,
        'full_page' => 1,
        'config_webservice' => 1,
        'translate' => 1,
        'vertex' => 1
    ],
    'downloadable_domains' => [
        '127.0.0.1'
    ],
    'install' => [
        'date' => 'Sun, 15 Mar 2020 03:00:18 +0000'
    ],
    'queue' => [
        'consumers_wait_for_messages' => 1
    ]
];
```
```
Database name: magentodb
Username: root
Password:
```
# 3. Disable custom modules
In this step we must disable all of our custom modules present in app/code and in app/design. In our case move the module app/design/frontend/Badar to an external localtion.

# 4. Install setup
From the project's root directory run the following command to install the setup.
```
php bin/magento setup:install --admin-user="badarnadeem" --admin-password="zmalqp120" --admin-email="badarnadeem0001@gmail.com" --admin-firstname="badar" --admin-lastname="nadeem"
```

# 5. Upgrade
From the project's root directory run
```
php bin/magento setup:upgrade
```

# 6. Compile
```
php bin/magento setup:di:compile
```

Move all the custom modules back to their respective locations and repeat steps 5 and 6.

# 7. Run the application.

```
Store address: http://127.0.0.1/magento/
Admin address: http://127.0.0.1/magento/admin_73qdhe/

username: badarnadeem
email: badarnadeem0001@gmail.com
password: zmalqp120
