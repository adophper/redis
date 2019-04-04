Yii2 使用 php_redis扩展
====================================================

与yii-redis区别在于链接redis方法，

yii-redis使用socket或者tcp，此组件使用php编写的redis扩展

目前所知php_redis性能要比socket好一点。

根据yii2-redis改编而成,配置方法与yii2-redis相同，

大部分函数兼容yii2-redis的写法，

非常用函数根据php_redis参数进行使用。

将下载文件放置于components\redis目录下

配置
-------------

```php
return [
    //....
    'components' => [
        'redis' => [
            'class' => 'components\redis\Connection',
            'hostname' => 'localhost',
            'port' => 6379,
            'database' => 0,
        ],
        'session' => [
            'class' => 'components\redis\Session',
            'hostname' => '127.0.0.1',
            'port' => 6379,
            'database' => 1,
        ],
         'cache' => [
             'class' => 'components\redis\Cache',
             'hostname' => '127.0.0.1',
             'port' => 6379,
             'database' => 2,
         ]
    ]
];
```

后续将增加支持集群的功能
