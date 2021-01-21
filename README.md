### 简介
* Project base on https://github.com/haruncpi/laravel-log-reader
* 由于原项目不支持多行日志的读取，做了简单的修改让其可以显示日志中的换行。

### 安装
* composer require klib/laravel-log-reader

### 使用
* 访问 `/admin/log-reader` 即可

#### JSON API [OPTIONAL]

* If you want to make your won UI then this package also provides the JSON API for log files. You will get the API link here /admin/api/log-reader

* Get JSON data by date
```
use Haruncpi\LaravelLogReader\LaravelLogReader;

return (new LaravelLogReader(['date' => '2020-01-27']))->get();

```

#### Config file [OPTIONAL]

* If you want to change the route URL for viewing the logs then run the command for publishing laravel log reader configuration file.
```
php artisan vendor:publish --provider="Haruncpi\LaravelLogReader\ServiceProvider" --tag="config"Copy
```

#### Custom Middleware [OPTIONAL]

* Laravel log reader >= v1.0.6 support custom middleware. So you can easily add more restriction to view your application logs. To use custom middleware, add middleware key into laravel-log-reader.php config file.
```
'middleware' => ['web','auth','your_middleware']
```
### 版本

#### v1.0.8
* 修复日志文件没有倒序显示的BUG。

#### v1.0.7
* 基础版本上新增读取多行日志信息
