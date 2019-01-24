# GuzzleTool
多资源网络请求，Composer包
>composer require liaosp/guzzle-tool

使用方法：继承这个类。

配置资源地址：

比如在yaconf 中配置：
```
[resources]
goods='http://devzuul.haoxiaec.com/api/php/product'
order='http://devzuul.haoxiaec.com/api/php/order'
oauth='http://devoauth.haoxiaec.com'
personal='http://devzuul.haoxiaec.com/api/authorize'
```


```php
class Resources extends ResourcesTool
{
    private $resources;
    /*
     * 微服务url 资源。
     * eg：
     *
     *  goods='http://devzuul.22.com/api/php/product'
        order='http://devzuul.22.com/api/php/order'
        oauth='http://devoauth.22.com'
        personal='http://devzuul.22.com/api/authorize'
     *
     */
    public function __construct($resources = 'goods')
    {
        //配置服务信息。
        $this->ServicesUrl = yaconf('resources');
        parent::__construct($resources);
    }


}
```
使用方法：
(new Resources('personal'))->json()->get('/users/WARE/add');
