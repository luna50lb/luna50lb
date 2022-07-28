


- 👋 Hi, I’m @luna50lb
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
luna50lb/luna50lb is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->


# よく使うライブラリ
- pandas
- numpy
- scipy
- matplotlib 
- others 

# DataFrame

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



# Others
## OpenCV
インストール(MacOS)
`brew install opencv3` あるいは `pip3 isntall opencv-python`だけでも大丈夫かも。

