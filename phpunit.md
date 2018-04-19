# phpunit

## option

```
phpunit --vervose -v
phpunit --testdox
phpunit --help
phpunit --coverage-clover optional/path/to/file
phpunit --coverage-html optional/path
phpunit --no-globals-backup
phpunit --static-backup
phpunit --configuration /path/to/your/phpunit.xml
phpunit --process-isolation
phpunit --testsuite Foo
```

## private method

```
public function testPrivateMethod()
{
    $obj = new hoge();
    $reflectionMethod = new ReflectionMethod($obj, 'privateMethod');
    $reflectionMethod->setAccessible(true);
    $reflectionMethod->invoke($obj);
}
```
