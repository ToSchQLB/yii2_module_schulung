<h1 align="center">Workshop: Yii 2 - Module</h1>

#### aktueller Schritt:
- Gii Module Generator oder Extension Generator öffnen
![gii](https://github.com/ToSchQLB/yii2_module_schulung/raw/master/images/01_gii.jpg)
- Module erstellen

![Extension Generator](https://github.com/ToSchQLB/yii2_module_schulung/raw/master/images/02_ext_gen.jpg)
![Module Generator](https://github.com/ToSchQLB/yii2_module_schulung/raw/master/images/03_mdl_gen.jpg)


![Extension Generator](https://github.com/ToSchQLB/yii2_module_schulung/raw/master/images/04_mdl_gen_result.jpg)

- Klasse toschqlb\beispiel\Module anlegen
- Module in web.php konfigurieren

```php
    'modules' => [
        'bsp' => 'toschqlb\beispiel\Module'
    ]
```
- Namespace in composer.json definieren
```
    "autoload": {    
        "psr-4": {
            "toschqlb\\beispiel\\" :"components/beispiel"
        }    
    }
```
- composer dumpautoload
```cmd
composer dumpautoload
```
#### 1. Schritt:
```
composer create-project --prefer-dist yiisoft/yii2-app-basic module
```
