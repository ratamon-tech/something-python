# something-python
Pyhonでなんか作る

## 仮想環境構築

- (初回)venv仮想環境モジュールを実行し仮想環境を作成する

`python -m venv v_env`

- 仮想環境の有効化

`source v_env/bin/activate`

- 仮想環境の無効化

`deactivate`

## Django導入

- Djangoフレームワークをインストール

`pip install django`

- プロジェクトを作成

`django-admin startproject learning_log .`

- データベース作成

`python manage.py migrate`

- プロジェクトの状態確認

`python manage.py runserver`

- アプリケーションの作成

`python manage.py startapp lerning_logs`

- データベースの変更

`python manage.py makemigrations learning_logs`

```
(v_env) ~/workspace/something-python $python manage.py makemigrations learning_logs 
Migrations for 'learning_logs':
  learning_logs/migrations/0001_initial.py
    - Create model Topic
```


- マイグレーションファイルを適用

`python manage.py migrate`

```
(v_env) ~/workspace/something-python $python manage.py migrate
Operations to perform:
  Apply all migrations: admin, auth, contenttypes, learning_logs, sessions
Running migrations:
  Applying learning_logs.0001_initial... OK
```

- スーパーユーザーを設定

`python manage.py createsuperuser`


## Djangoシェルの利用

- シェル起動

`python manage.py shell`

 - 使用例

 ```sh
 (InteractiveConsole)
>>> from learning_logs.models import Topic
>>> Topic.objects.all()
<QuerySet [<Topic: チェス>, <Topic: ロッククライミング>]>
 ```

 ## DBのマイグレーション実行

 - マイグレーションファイル作成

 `python manage.py makemigrations learning_logs`

<details><summary>実行例</summary>
<pre>
(v_env) ~/workspace/something-python $python manage.py makemigrations learning_logs
It is impossible to add a non-nullable field 'owner' to topic without specifying a default. This is because the database needs something to populate existing rows.
Please select a fix:
 1) Provide a one-off default now (will be set on all existing rows with a null value for this column)
 2) Quit and manually define a default value in models.py.
Select an option: 1
Please enter the default value as valid Python.
The datetime and django.utils.timezone modules are available, so it is possible to provide e.g. timezone.now as a value.
Type 'exit' to exit this prompt
>>> 1
Migrations for 'learning_logs':
  learning_logs/migrations/0003_topic_owner.py
    - Add field owner to topic
</pre>
</details>

- マイグレーション実行

`python manage.py migrate`

## django-bootstrap4のインストール

`pip install django-bootstrap4 `