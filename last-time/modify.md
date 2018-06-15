## 수정할 부분

### 스크립트

```js
// ..
window.onload = function(){
    // 5번 추첨하도록
    var html_lotto = "";
    for (var loop=0; loop<5; loop++) {
        var lottoNumbers = genNumbers();
        // 23,24,25 과 간이 연속으로 3개의 숫자가 나오지 않게 하자!
        while( checkLogic1(lottoNumbers) ) lottoNumbers=genNumbers();
        // 11,15,17 과 같이 같은 10의 자리수에 3개가 나오지 않게 하자!
        while( checkLogic2(lottoNumbers) ) lottoNumbers=genNumbers();

        for(var i=0; i<lottoNumbers.length; i++){
          html_lotto += '<b>'+ lottoNumbers[i] +'</b> ';
        }
        html_lotto += '<br>'
    }
    document.getElementById("NUMBERS").innerHTML = html_lotto;
}
```

### 스타일시트
```html
<style>
#NUMBERS { margin-top: 5vh; font-size: 2em; color: #fff; text-align: center; }
b{ display: inline-block; width: 64px; height: 64px; line-height: 64px; border-radius: 32px; margin: 16px 4px; background: #999; }
</style>
```
