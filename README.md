# Unit Test On php
## PHPUnit: go to PHPUnit [form chrome](https://phpunit.de/index.html)
first add Controller and main file to project 
then add composer for add Unit Test
 ```sh
$ composer require phpunit/phpunit ^9
```
after add composer up most create ```phpunit.xml``` file to set config for testing function and in this file set this config 
 ```sh
<?xml version="1.0" encoding="UTF-8"?>
<phpunit bootstrap="vendor/autoload.php"
    stopOnFailure="false">

    <testsuite name="Calculator">
        <directory>tests</directory>
    </testsuite>

</phpunit>
```
:warning: in ```composer.json``` you most add this config 
 ```sh
    "autoload": {
        "psr-4": {
            "App\\": "app"
        }
    }
```
create directory tests and testing file for test function <br>
in this file you can add config that you can set for test <br>
for example :
 ```sh
class CalculatorTest extends PHPUnit\Framework\TestCase{
    public function testAdd(){
        $calculator = new \App\Calculator;
        $result = $calculator->add(20, 5);

        $this->assertEquals(25, $result);
    }
}
```
and then in terminal you can test and run with this comand :
 ```sh
 ./vendor/bin/phpunit
```
:warning: you can use ```--testdox``` for document response in terminal
