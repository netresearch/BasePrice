Magenerds BasePrice Module
----------------------------
This Module for Magento® 2 displays base prices.

Facts
-----
* version: 1.0.4

Description
-----------
01/08/18
* This module displays base prices.

Requirements
------------
* PHP >= 5.6.5

Compatibility
-------------
* Magento >= 2.2.4

Installation Instructions
-------------------------

The Magenerds BasePrice Module for Magento® 2 is distributed in three formats:
* Drop-In
* [Composer Artifact](https://getcomposer.org/doc/05-repositories.md#artifact)
* [Composer VCS](https://getcomposer.org/doc/05-repositories.md#using-private-repositories)

### Install Source Files ###
The following sections describe how to install the module source files,
depending on the distribution format, to your Magento® 2 instance.

#### Drop-In ####
If you received a single ZIP file with no `composer.json` file included, extract
its contents to the project root directory. The module sources should then be
available in the following sub-directory:

    app
    └── code
        └── Magenerds
            └── BasePrice

#### Artifact ####
If you received multiple ZIP files with `composer.json` files included, move
them to a common directory on the server. The directory
`/var/www/share/marketplace/magenerds` is used in the following examples. Please
replace this path with the actual artifact directory of choice.

    /var
    └── www
        └── share
            └── marketplace
               └── magenerds
                    └── BasePrice-master.zip

Then navigate to the project root directory and run the following commands:

    composer config repositories.magenerds-baseprice vcs https://github.com/netresearch/BasePrice.git
    composer require magenerds/baseprice

 #### VCS ####
 If you prefer to install the module using [git](https://git-scm.com/), run the
 following commands in your project root directory:
 
    composer config repositories.magenerds-baseprice vcs https://github.com/netresearch/BasePrice.git
    composer require magenerds/baseprice
 
 ### Enable Module ###
 Once the source files are available, make them known to the application:
 
     ./bin/magento module:enable Magenerds_BasePrice
     ./bin/magento setup:upgrade
 
 Last but not least, flush cache and compile.
 
     ./bin/magento cache:flush
     ./bin/magento setup:di:compile
 
 Uninstallation
 --------------
 
 The following sections describe how to uninstall the module, depending on the
 distribution format, from your Magento® 2 instance.
 
 #### Composer Git and Composer Artifact ####
 
 To unregister the shipping module from the application, run the following command:
 
     ./bin/magento module:uninstall --remove-data Magenerds_BasePrice
 
 This will automatically remove source files and clean up the database.
 
 #### Drop-In ####
 
 To uninstall the module manually, run the following commands in your project
 root directory:
 
     ./bin/magento module:disable Magenerds_BasePrice
     rm -rf app/code/Magenerds/BasePrice

Features
--------------
When you use the baseprice module for the first time. The basic price is the price per unit of quantity, including VAT and other price components, and is intended to make it easier for consumers to compare prices, in particular for packaging with different filling quantities.

#### Admin Settings ####
_Stores > Configuration > MAGENERDS > Base Price > General_

1. General Setup
   1. If you want to change the text for the output in the frontend, do it in the input field "Base price template". Variables to use: _{BASE_PRICE}_, _{REF_AMOUNT}_, _{REF_UNIT}_
   2. Add your custom conversion mapping.
2. Product detail setup
   1. Set the product amount and unit.
   2. Set the reference amount and unit.
  

License
-------
[OSL - Open Software Licence 3.0](http://opensource.org/licenses/osl-3.0.php)

Developer
---------
* Florian Sydekum | [TechDivision GmbH](http://www.techdivision.com) | f.sydekum@techdivision.com
