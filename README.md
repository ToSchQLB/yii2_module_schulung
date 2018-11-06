<h1 align="center">Workshop: Yii 2 - Module</h1>

### aktueller Schritt:
- Update extensions.php
```php
'toschqlb/yii2-mdl-bsp' =>
    array(
        'name' => 'toschqlb/yii2-mdl-bsp',
        'version' => '0',
        'alias'=>array(
            '@toschqlb/beispiel' => $vendorDir . '/../modules/beispiel/yii2-mdl-bsp',
        )
    )
``` 
- Gii Model-Generator öffnen
![Model Generator](https://github.com/ToSchQLB/yii2_module_schulung/raw/master/images/05_mdl_gen.jpg)
- Gii CRUD-Generator öffnen

![Model Generator](https://github.com/ToSchQLB/yii2_module_schulung/raw/master/images/06_crud_gen.jpg)

### 1. Schritt:
```
composer create-project --prefer-dist yiisoft/yii2-app-basic module
```
### 2. Schritt:
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
- Default Route und ersten Controller definieren
### 3. Schritt
- Ordnerstruktur anlegen
    - models
    - views
    - (controlers)
    - migrations
    
- migration anlegen
```cmd
yii migrate/create  --migrationPath=@app/modules/beispiel/yii2-mdl-bsp/migrations create_user_table --fields="name:string,passwort:string,mail:string"
```
- migration ausführen
```cmd
yii migrate/up  --migrationPath=@app/modules/beispiel/yii2-mdl-bsp/migrations
```
Weiter lesen: [Namespaced Migrations](https://www.yiiframework.com/doc/guide/2.0/en/db-migrations#namespaced-migrations)
