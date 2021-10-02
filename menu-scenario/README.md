# 小連小吃部

## 關於
最近剛結束一個case，這裡做成一個小專案來記錄自己的思路。
情境 1 是已經存在的規則或邏輯，我主要處理的部分為情境 2。

## 情境 1
小連小吃部有一個菜單系統，客戶從菜單上點菜，必須選擇「料理」跟「料理選項」，才能順利點餐。

## 菜單規則
- 選了「料理」後：
  - 如果「料理」有選項可以選，就顯示「料理選項」。
  - 如果「料理」沒有選項可以選，「料理選項」就呈現灰色。
- 因為必須選擇「料理」跟「料理選項」，沒有料理選項的話，「料理」跟「料理選項」的資料都會是一樣的。

## 菜單資料
```javascript
const menuData = [
  {food: '牛肉湯', price: 100, options: ['牛肉湯']},
  {food: '牛肉料理', price: 120, options: ['牛肉飯', '牛丼飯']},
  {food: '蛋炒飯', price: 60, options: ['蛋炒飯']},
  {food: '培根炒飯', price: 80, options: ['培根炒飯']},
  {food: '炒時蔬', price: 100, options: ['炒時蔬']},
]

```
[Code](https://github.com/BolasLien/my-example/menu-scenario/blob/master/version1.html)
[Demo](https://bolaslien.github.io/my-example/menu-scenario/version1)

---

## 情境 2
小連收到客人的建議：牛肉湯就該放在牛肉料理才合理。小連想想也對，於是向前端工程師提出了需求。

### 需求
1. 牛肉湯要顯示在牛肉料理的料理選項裡面。
2. 選到牛肉湯的時候還是原本的價格。
3. ~~因為後端工程師跑路了，~~ 原本的菜單的資料結構不能動。

### 修改思路
- 原本的資料不動，而是把原本的資料當作基礎，用來做成新的菜單
  - 效果：把牛肉湯放到牛肉料理的選項裡面，並且把牛肉湯從料理移除
- 在牛肉料理的資料擴充一個 function
  - 效果：選擇牛肉料理選項的時候，用來切換牛肉湯的價格


[Code](https://github.com/BolasLien/my-example/menu-scenario/blob/master/version1.html)
[Demo](https://bolaslien.github.io/my-example/menu-scenario/version2)
