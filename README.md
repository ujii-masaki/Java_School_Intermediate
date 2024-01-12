# TechPit_Javaスクール_総合問題
1, 概要  
本アプリケーションはユーザー情報の一覧と新規登録ができるシステムです。  
  
・ユーザー情報一覧画面では、登録した情報を確認できます。  
http://localhost:8080/user/list  
![sample_01](https://github.com/ujii-masaki/Java_School_Intermediate/assets/156159427/ccf1a2df-ec32-40d3-9b93-8abfcf90b83a)  

・「新規登録はこちら」をクリックすると、ユーザーの新規登録ができます。  
http://localhost:8080/user/add
![sample_02](https://github.com/ujii-masaki/Java_School_Intermediate/assets/156159427/89b84881-4669-4752-b544-5c06bde021af)  

主要機能  
ユーザー情報一覧画面：すべてのユーザー情報を一覧表示します。  
ユーザー新規登録画面：ユーザー名、パスワード、メールアドレスを入力して登録します。パスワードは暗号化されて保存されます。  
  
2, 使用技術  
- java ver21
- springframework.boot version 3.2.1
- Gradle
- Spring Web
- Thymeleaf
- Lomback
- PostgreSQL Driver	
- MySQL
- Mybatis
- Docker/Docker-compose
- A5:SQL Mk-2  SQL Client/ER Diagram tool
- VScode
  
3, 構成図  
ユーザー新規登録の流れ
```mermaid
graph LR

  classDef default fill: #fff,stroke: #333,stroke-width: 1px;
  style funcA fill: #fff,stroke: #333,stroke-width: 5px;
  style funcB fill: #fff,stroke: #333,stroke-width: 5px;
  style funcC fill: #fff,stroke: #333,stroke-width: 5px;
  style funcD fill: #fff,stroke: #333,stroke-width: 5px;
  style funcE fill: #fff,stroke: #333,stroke-width: 5px;
  style funcF fill: #fff,stroke: #333,stroke-width: 5px;

  funcA-->UserController-->UserServise-->UserRepository-->UserMapper-->Docker-->UserMapper-->UserRepository-->UserServise-->UserController-->funcF

  subgraph funcA [ユーザー新規登録画面]
    add
    UserRequest
  end

  subgraph funcB [内部処理 コントロール]
    UserController
  end

  subgraph funcC [内部処理 業務ロジック]
    UserServise
  end

  subgraph funcD [内部処理 DBアクセス]
    UserRepository
    UserMapper
  end

  subgraph funcE [DB]
    Docker
  end

  subgraph funcF [ユーザー情報一覧画面]
    list    
  end  
```

  
Javaの中級研修で学んだことを、実務で使用するような開発環境で実際に実装～動作確認を行いました。
