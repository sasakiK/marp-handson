---
marp: true
theme: base
description: Dash Hands-onのIntroduction用スライドです
paginate: true
footer: Python Dash hands-on
---

<style>
section {
    background: #2A2B25;
    color:#FFFF;
    font-family: 'Noto Sans CJK JP';
    justify-content: flex-start;
}
h1{
    color:#D5EBDC;
}
p{
    color:#D5EBDC;
}
/* ul {
    list-style-image: url('assets/images/substract.png');
    list-style-type: dot;
} */
li {
	list-style-type: none;
}
li:before {
    content: '';
    width: 6px;
    height: 6px;
    display: inline-block;
    border-radius: 100%;
    background: grey;
    position: relative;
    left: -15px;
    top: -5px;
}
</style>
<!-- size: 4:3 -->

<style scoped>
section {
    justify-content: center;
}
p{
    text-align: center;
    margin-top: 10%;
    font-size: 18px;
}
</style>

# Dash Hands-on

- Hands-onの目的
- Dashとは
- ひとこと

2019.11.06 佐々木 健佑

---

# Hands-onの目的

## その1

- アプリを作ったことがある状態にすること

---

# Hands-onの目的

## その2

- データ分析のアウトプットの選択肢を増やすこと
  - PowerPoint
  - レポート(wordとか)
  - application ← new

---

<style scoped>
h2{
    text-align: center;
}
h6{
    font-size: 18px;
    text-align: right;
}
</style>

# Dashとは

## ![height:150px](/assets/images/dash-logo-300.png)

- PythonのWebアプリケーションフレームワークの一つ
    - pythonだけで完結する
- 2015年に初めて公開された

###### ※ フレームワーク : 枠組み、骨組み、組織、体制

---

<style>
pre {
    background: #111111;
    font-size: 14px;
}
span {
    color: #91D6A7;
}
</style>

# Dashとは

- Dash appに必要なもの
    - 基本Pythonファイル一つだけ

app.py

```python
import dash

app = dash.Dash(__name__)

app.layout = html.Div(
    # アプリの見た目を記述する
)

# 入力と出力を指定する
@app.callback(
    Output(component_id='my-div', component_property='children'),
    [Input(component_id='my-id', component_property='value')]
)
# 処理を記述する
def update_output(input_value):
    return "inputに応じて返す内容"

if __name__ == '__main__':
    app.run_server(debug=True)
```