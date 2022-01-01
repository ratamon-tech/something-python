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