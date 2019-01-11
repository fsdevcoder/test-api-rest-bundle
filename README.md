TestApiRestBundle
=================

##About


TestApiRestBundle allows you to test your Symfony REST API deeply. It checks the validity of your application and ensures it stays robust throughout time using PHPUnit and via unit, scenario and database testing.

#Table of contents

* [About](#markdown-header-about)
* [Installation](#markdown-header-installation)
* [Usages](#markdown-header-usages)
* [Tests folder structure](#markdown-header-tests-folder-structure)


##Installation


You can install using composer, assuming it's already installed globally : 

```
composer require --dev everycheck\test-api-rest-bundle
```

##Usages

* [Basic usages](Doc/SIMPLE_USAGE.md)

###Advanced usages

* [Test dynamic responses](Doc/PATTERN_USAGE.md)
* [Reuse response content](Doc/REUSE_USAGE.md)
* [Test email sending and their content](Doc/EMAIL_USAGE.md)


##Tests folder structure

To test one of your bundle, you just have to replicate the structure of that one and add some directories by the following structure

    .
    ├── tests                                       #   The basic Symfony test directory
    │   ├── AcmeFooBundle                           #   Name of your bundle
    │   │   ├── Controller                          
    │   │   │   ├── FooControllerTest.php           #   Controller your want to test
    │   │   │   └── ...                                    
    │   │   │
    │   │   ├── DataFixtures                        
    │   │   │   └── ORM                             
    │   │   │       ├─ LoadAcmeFooFixtures.php     #   Fixtures dedicated to one controller   
    |   |   |       └── ...
    │   │   │                                       
    │   │   ├── Payloads                            
    │   │   │   └── ...                             #   File posted to your API
    │   │   │                                       
    │   │   ├── Resources                           
    │   │   │   └── config                          
    │   │   │       ├── foo.yaml                    #   All the tests for a specific controller, set as a YAML file
    │   │   │       └── ...                    
    │   │   │   
    │   │   └── Responses                           #   All the expected responses coming from the endpoints of your API when testing it
    │   │       └── Expected
    │   │           └── ...
    │   └──
    └──
