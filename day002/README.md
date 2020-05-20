Vue.js 기본 기능
Vue.js 기능은 디렉티브와 템플릿을 연동하는 형태로 사용합니다.

텍스트 바인딩
템플릿에 다음과 같이 속성 이름을 작성하면, 해당 위치에 값이 렌더링됩니다.
vue 2.x
``` javascript
<p>{{ message }}</p>
var app = new Vue({
    el: '#app',
    data: {
        message:'Hello Vue.js'
    }
});
```
vue 3.x typescript
``` javascript
<p>{{ message }}</p>
import Vue from 'vue';
import Component from 'vue-class-component';

@Component({})
export default class App extends Vue {
  public message: string = 'Hello Vue.js';
}
```

반복 렌더링
기사 목록 또는 상품 목록과 같은 리스트는 data 옵션에 등록한 배열 또는 
객체에 v-for 디렉티브를 적용해서 반복 렌더링 할 수 있습니다.
vue 2.x
``` javascript
<ol>
    <li v-for="item in list">{{ item }}</li>
</ol>
var app = new Vue({
    el: '#app',
    data: {
        list: ['사과','배','감']
    }
});
```
vue 3.x typescript
``` javascript
<ol>
    <li v-for="item in list">{{ item }}</li>
</ol>
import Vue from 'vue';
import Component from 'vue-class-component';

@Component({})
export default class App extends Vue {
  public list: string[] = ['사과','배','감'];
}
```

이벤트 사용하기
'클릭했을 때'.'선택한 요소가 변경되었을 때'처럼 DOM 이벤트 바인딩 할 때는
v-on 디렉티브를 사용합니다.
다음 예는 버튼을 클릭 했을 때 handleClick 메서드가 호출 됩니다.
``` javascript
<button v-on:click="handleClick">Click</button>
var app = new Vue({
    el: '#app',
    methods: {
        handleClick: function() { }
    }
});
```

``` javascript
<button v-on:click="handleClick">Click</button>
import Vue from 'vue';
import Component from 'vue-class-component';

@Component
export default class App extends Vue {
  public handleClick(): void => { }
  // public handleClick = () => { }
}
```

입력 양식과 동기화 하기
데이터와 입력 양식 입력 항목을 바인딩 할 때는 v-model 디렉티브를 사용합니다.
입력 또는 선택을 하면, 곧바로 데이터와 DOM에 반영됩니다.
``` javascript
<p>{{ message }}</p>
<input v-model="message" />
var app = new Vue({
    el: '#app',
    data: {
        message: '초기화 메시지'
    }
});
```
``` javascript
<p>{{ message }}</p>
<input v-model="message" />
import Vue from 'vue';
import Component from 'vue-class-component';

@Component
export default class App extends Vue {
  public message: string = '초기화 메시지';
}
```

조건 분기
2장에서 설명하는 v-if 디렉티브를 사용하면, 템플릿 기반의 조건 분기를 실시할 수 있습니다.
다음 예는 show 속성이 true 일 때만 <p> 요소를 렌더링합니다.
```javascript
<p v-if="show">Hello</p>
var app = new Vue({
    el: '#app',
    data: {
        show: true
    }
});
```
```javascript
<p v-if="show">Hello</p>
import Vue from 'vue';
import Component from 'vue-class-component';

@Component
export default class App extends Vue {
  public show: boolean = true;
}
```

트랜지션과 애니매이션
```<transition>```태크를 사용하면, 템플릿 내부 요소들에 css 트랜지션과 
애니메이션을 손쉽게 적용 할 수 있다.

