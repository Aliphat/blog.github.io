# 基础学习

## 笔记

[基础笔记](php/base.md)

[Composer教程](php/composer.md)



## 教程

1.PHP基础小白，https://www.bilibili.com/video/BV1A4411M7iA?p=6，从P10开始看
2.学框架，thinkphp6，https://space.bilibili.com/14978379/search/video?keyword=thinkphp
3.laravel 高级教程，找群主要。

4.Mysql，https://www.bilibili.com/video/BV1Vy4y1z7EX?p=148
5.Redis，https://www.bilibili.com/video/BV1CJ411m7Gc?p=36 ，看p1-p38

6.thinkphp实战，
https://www.bilibili.com/video/BV1C44y1x7ip?from=search&seid=3862886655798130840&spm_id_from=333.337.0.0
https://www.bilibili.com/video/BV1HA411M7ZW?from=search&seid=3862886655798130840&spm_id_from=333.337.0.0
https://www.bilibili.com/video/BV19p4y1D7S9?from=search&seid=3862886655798130840&spm_id_from=333.337.0.0
https://www.bilibili.com/video/BV1kf4y1877w?from=search&seid=7513740192011812637&spm_id_from=333.337.0.0



## PHP框架

https://codeigniter.org.cn/

可以聊天的PHP框架

http://wiki.linyiyuan.top/#/

https://learnku.com/articles/65044

tp

laveral

1. 小型项目:Codelngiter
2. 中型项目:CakePHP、Zend Framework、Laravel、Thinkphp
3. 大型重量级项目:Yii、Symfony、Laravel



## Laytp

生成curd的时候，浏览器点开禁用缓存。





## PHP技术博客

```php
TP6框架导出text文本，数组转文本，分批分量导出。
public function download(){
        $text = "";
        $data = array();

        $nums = 15000; //每次导出数量
        $step = V2::count() / $nums; //循环次数
        $url = "http://" . $_SERVER['SERVER_NAME'] . "/ver2?voucherCode=";
        if (!is_int($step)) {
            $step = intval($step) + 1;
        }
        for ($i = 0; $i < $step; $i++) {
            $start = $i * $nums;
            $result =  V2::field(['productcode','code'])
                ->limit($start, $nums)->select();
            foreach ($result as $item) {
                array_push($data,$url . $item['productcode'] . "    " . $item['code'] . PHP_EOL);
            }

        }
        $text=implode($data);
        return download($text,"123.txt", true);
    }
```

