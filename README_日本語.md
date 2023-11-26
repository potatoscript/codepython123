# codepython123 ライブラリ

`codepython123` ライブラリは、データベース接続、メール通知、ファイル操作などの一般的なタスクに関連するユーティリティ関数のセットを提供します。この README.md ファイルは、ライブラリの使用方法に関するガイドとなります。

## インストール

`codepython123` ライブラリを使用するためには、以下の手順に従ってください。

1. **依存関係のインストール:**
   - システムに Python がインストールされていることを確認してください。
   - 次のコマンドを使用して必要な依存関係をインストールします。
     ```bash
     pip install psycopg2-binary python-dotenv mysql-connector colorama
     ```

2. **ライブラリのダウンロード:**
   - `codepython123.py` ファイルをダウンロードしてください。
     ```python
     pip install codepython123
     ```
3. **ライブラリのインポート:**
   - Python スクリプトまたはプロジェクトの冒頭に、以下の行を含めて `codepython123` ライブラリをインポートしてください。
     ```python
     from codepython123 import DatabaseConnector, EmailNotifier, Template
     ```

## 使用法

### データベース接続

#### PostgreSQL 接続

```python
# 使用例
postgres_params = {
    "host": "your_host",
    "database": "your_database",
    "user": "your_user",
    "password": "your_password",
    "port": "your_port",
    "query": "your_query",
}

db_connector = DatabaseConnector()
connection = db_connector.connect_postgresql(**postgres_params)
result = connection.fetchall()
```

#### MySQL 接続

```python
# 使用例
mysql_params = {
    "host": "your_host",
    "database": "your_database",
    "user": "your_user",
    "password": "your_password",
    "port": "your_port",
    "query": "your_query",
}

db_connector = DatabaseConnector()
connection = db_connector.connect_mysql(**mysql_params)
result = connection.fetchall()
```

### メール通知

```python
# 使用例
email_params = {
    "sender": "your_email@gmail.com",
    "recipient": "recipient1@gmail.com;recipient2@gmail.com",
    "recipient_cc": "cc1@gmail.com;cc2@gmail.com",
    "subject": "Your Email Subject",
    "body": "<p>Your email body in HTML format</p>",
    "footer": "Additional email footer",
    "smtp_server": "your_smtp_server",
    "smtp_port": 587,
}

email_notifier = EmailNotifier()
result = email_notifier.send_email(**email_params)
```

### ファイル操作

```python
# 使用例
template = Template()

# フォルダ内のファイル一覧取得
folder_path = "path/to/your/folder"
files = template.list_files_in_folder(folder_path)

# CSV ファイルのデータ読み込み
csv_file_path = "path/to/your/file.csv"
data = template.read_csv_file(csv_file_path)

# ディレクトリの移動
source_path = "path/to/your/source"
destination_path = "path/to/your/destination"
directory_name = "your_directory_name"
template.move_directory(source_path, destination_path, directory_name)

# ディレクトリの削除
folder_to_delete = "path/to/your/folder"
template.delete_directory(folder_to_delete)

# データを CSV ファイルにエクスポート
data_table = your_data_table_widget  # 実際のデータテーブルに置き換えてください
export_path = "path/to/your/export/file.csv"
message = "Export successful!"
template.export_to_csv(data_table, export_path, message)
```

### ロギングとエラー処理

```python
# 使用例
template = Template()

# ロギングの初期化
log_file = "path/to/your/log/file.log"
template.logging_init(log_file)

# 日付を含むメッセージをログ
template.logging_date("Your log message with date")

# 日付を含まないメッセージをログ
template.logging_message("Your log message without date")

# エラーの処理
try:
    # 例外を発生させる可能性のあるコード
except Exception as e:
    template.handle_error(e)
```

### GUI ウィンドウ操作

```python
# 使用例
template = Template()

# ウィンドウの位置設定
root = your_root_window  # 実際のルートウィンドウに置き換えてください
window = your_child_window  # 実際の子ウィンドウに置き換えてください
width, height = 800, 600  # ウィンドウの寸法を設定
template.set_window_position(root, window, width, height)

# ウィンドウの位置を修正
template.fix_window_position(window, root)
```

### データベース操作

```python
# 使用例
template = Template()

# PostgreSQL 操作
postgres_params = {
    "host": "your_host",
    "database": "your_database",
    "user": "your_user",
    "password": "your_password",
    "port": "your_port",
    "query": "your_query",
}

result = template.db_fetchall(postgres_params)
result = template.db_commit(postgres_params)
result = template.db_commit_values(postgres_params)
result = template.db_commit_many(postgres_params)

# MySQL 操作
mysql_params = {
    "host": "your_host",
    "database": "your_database",
    "user": "your_user",
    "password": "your_password",
    "port": "your_port",
    "query": "your_query",
}

result = template.mysql_fetchall(mysql_params)
result = template.mysql_commit(mysql_params)
result = template.mysql_commit_values(mysql_params)
result = template.mysql_commit_many(mysql_params)
```

### その他

```python
# 使用例
template = Template()

# 一定間隔で関数を実行
template.run_interval()

# フォーマットされたメッセージの表示
template.print_message("OK", "Your information message")
template.print_message("NG", "Your
