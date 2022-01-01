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