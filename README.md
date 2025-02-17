# photoGallery

概要  
imgurのAPIを経由して、画像検索アプリを作成しました。  

現在は言葉を検索することで、その言葉に関する画像一覧が表示されます。  
時間は厳しかったので、画像のuploadはまだ出来ていません。  
また、検索条件（ソート、範囲など）も導入する時間ありませんでした。  

ユーザーの課題や要求は：画像を検索できることに加えて、電波がなくても過去検索した画像がまた検索できます。  

ユーザーはオフラインでも過去検索した画像を検索することができるのは  
android jetpackのRoom永続ライブラリのおかげです。  

ユーザーは検索を実行すると下記流れとなっております。  

１．DB内に関連するデータの存在確認  
　　1. ある場合は、UIに連携した上でAPIを呼び出し、更新する必要あるかどうか確認する  
　　　a. 新しい情報がなければそのまま終わります。  
　　　b. 新しい情報があれば、DBに入れ込んで、UIに連携します。  
　　2. ない場合は、APIをフェッチして、DBに入れ込んで、UIに連携します。  

imgurAPIの仕様書は下記のとおりです。  
https://apidocs.imgur.com/?version=latest  

利用した技術：  

Kotlin  
Databinding  
MVVM+LiveData  
Room Persistence Library  
Retrofit2.0  
AndroidX  
