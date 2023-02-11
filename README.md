


<!---
- 👋 Hi, I’m @luna50lb
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

luna50lb/luna50lb is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.


# bashコマンドを使用
```
sp0=subprocess.Open(args=["rm", "-rf", "dirA"])
sp0.wait()
print(sp0.returncode)
```

# ディレクトリ配下の全てのフォルダとファイルを表示
```
for currentDirj, listSubDirj, listFilej in os.walk('dirA'):
    print(currentDirj, listFilej)
```

# DataFrame

## ストリング型のカラムのセルの値に検索したい文字列が含まれているかどうか
```
df['a0'].astype(str).str.contains('Today is ([0-9]{4})/(0[1-9]|1[0-2])/(0[1-9]|[12][0-9]|3[01])',regex=True)
```

## ストリング型のカラムのセルの文字数を表示する
```
df['a0'].astype(str).str.len()
```

## データフレームのセルの値を変更する
```
df.loc[ df['v0']<0, 'v0' ]=0
df.at[0, 'v0']=2.5
df['a0']=df['a0'].replace(to_replace=[np.nan],value=None)
```


# 時系列
## 日時に日数(整数)を加える
`pd.to_timedelta(np.arange(0,10), unit='D')`を使えます。

## 月曜日を週始めの日として用いる
```
df_x=pd.DataFrame({'date':pd.date_range(start='2021-12-26', end='2022-01-13', freq='D' )})
df_x['day_name']=df_x['date'].dt.day_name()
df_x['plus']=pd.to_timedelta(df_x['date'].dt.dayofweek, unit='D')
df_x['Monday']=df_x['date'] - df_x['plus']
```

# JupyterLab
## コードのフォールディング
Settings > Advanced Settings Editor より、 Text Editorタブを選択する。User Preferencesの部分で、editorConfig内部のcodeFoldingをtrueとする。
```
{
    "editorConfig": {
        "codeFolding": true
    }
}
```


# psycopg2
## MacOSへインストールする手順　
1. brewでpostresqlをインストール 
2. LDFLAGSとCPPFLAGSの２つを設定
3. pipでpsycopg2をインストール
```
brew install postgresql
export LDFLAGS="-L/usr/local/opt/openssl/lib"
export CPPFLAGS="-I/usr/local/opt/openssl/include"
pip3 install psycopg2
```
## DBへの接続とデータ取得
```
import psycopg2
import pandas as pd
pd.options.display.max_colwidth=110 

conn=psycopg2.connect(dbname='******', user='*****', password='*****', port=*****)
query_a=""" select * from pg_tables where schemaname='public';"""

with conn:
    with conn.cursor() as curs:
        curs.execute(query_a)
        rec_a = curs.fetchall()
        df_a=pd.DataFrame(rec_a)
        print(df_a)
conn.close()
```




# Others 
## OpenCV
インストール(MacOS)
`brew install opencv3` あるいは `pip3 isntall opencv-python`だけでも大丈夫かも。


# よく使うライブラリ
- pandas
- numpy
- scipy
- matplotlib 
- others, psycopg2 

--->
