Yii2 Advanced view
===============
The extension adds the ability to post styles anywhere in the body.

Installation
------------

The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

Either run

```
php composer.phar require --prefer-dist lan143/yii2-advanced-view "*"
```

or add

```
"lan143/yii2-advanced-view": "*"
```

to the require section of your `composer.json` file.

Update config file config/web.php
```php
return [
    'components' => [
        'view' => [
            'class' => 'lan143\advanced_view\View',
        ],
    ],
]
```


Usage
-----
assets/AppAsset.php
```php
class BlogAsset extends AssetBundle
{
    public $css = [
        'css/site.css'
    ];

    public $js = [
        'js/site.js'
    ];

    public $depends = [
        'yii\web\YiiAsset',
        'yii\bootstrap\BootstrapAsset',
    ];

    public $cssOptions = [
        'position' => \yii\web\View::POS_END
    ];
}
```

or config/web.php
```php
$config = [
    'components' => [
        'assetManager' => [
            'bundles' => [
                'yii\bootstrap\BootstrapAsset' => [
                    'cssOptions' => [
                        'position' => \yii\web\View::POS_END
                    ],
                ],
            ],
        ],
    ],
];
```