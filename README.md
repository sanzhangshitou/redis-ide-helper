# redis-ide-helper

## 查看 php redis 扩展版本

```bash
php --ri redis
```

```txt
Redis Support => enabled
Redis Version => 6.1.0
Redis Sentinel Version => 1.0
Available serializers => php, json
```

## 安装对应版本的 redis-ide-helper 扩展

`Redis Version => 6.1.0`

```bash
composer require --dev sanzhangshitou/redis-ide-helper:~6.1.0
```

`Redis Version => 6.2.0`

```bash
composer require --dev sanzhangshitou/redis-ide-helper:~6.2.0
```

`Redis Version => 6.3.0`

```bash
composer require --dev sanzhangshitou/redis-ide-helper:~6.3.0
```

```php
/** @var \Redis $redis */
$redis = new \Redis();
$redis->connect(host: 'localhost', port: 6699);
$auth = $redis->auth('redis123456');
if (!$auth) {
    exit('Redis 密码认证失败');
}
$redis->select(1);
$redis->set('key', mt_rand(100000, 999999));
$res = $redis->get('key');
var_dump($res);
```
