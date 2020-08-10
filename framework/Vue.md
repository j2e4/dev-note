# Vue JS

### 단축어
* `#` (v-slot)
    ```html
    <BDropdown
        size="sm"
        no-caret
    >
        <template #button-content> <!-- v-slot: -->
            <FontAwesomeIcon icon="bars" />
        </template>
        <BDropdownItem .../>
    </BDropdown>
    ```
* `:` (v-bind)
    ```html
    <Component :is="activeMenu" /> <!-- v-bind -->
    ```
* `@` (v-on)
    ```html
    <BButton
        size="sm"
        variant="info"
        @click="clickAction()"
    >
        <FontAwesomeIcon icon="search" /> <!-- v-on -->
    </BButton>
    ```

### const 변수로 선언하기
싱글 파일 컴포넌트에서 상수  
[3 different ways to access constants in a Vue template](https://coderethinked.com/3-different-ways-to-access-constants-in-a-vue-template/)
1. data() 선언
```javascript
data() {
    return {
        COUNTRY: {
            KOREA: '한국',
            US: '미국',
            UK: '영국'
        }
    }
}
```
2. export const 변수로 선언
```javascript
export const COUNTRY = {
    KOREA: '한국',
    US: '미국',
    UK: '영국'
};
```
3. created() 선언
```javascript
created() {
    this.COUNTRY =  {
        KOREA: '한국',
        US: '미국',
        UK: '영국'
    }
}
```

### Computed 변수 getter/setter 할당

computed로 선언한 변수를 v-model 등 set할 수 있는 애트리뷰트에 사용했을 때  
`Computed property was assigned to but it has no setter.`  
변수가 assigned 됐지만 setter가 없다는 webstorm 힌트가 떴다.  
computed 변수는 `기본적으로 getter-only`지만,  
필요에 따라 `setter 지정이 가능`하다고 한다.  

```javascript
<template>
    <div class="ex-computed-setter">
        <div>
            <BFormCheckbox
                size="sm"
                v-model="checked"
                :options="season"
            >
                4계절 선택 여부
            </BFormCheckbox>
        </div>
        <div>
            <BFormCheckboxGroup
                size="sm"
                v-model="selection"
                :options="season"
            />
        </div>
    </div>
</template>
<script>
    export default: {
        data() {
            return {
                season: ['봄', '여름', '가을', '겨울'],
                selection: ['봄', '가을']
            }
        },
        computed: {
            checked: {
                get() {
                    return this.season.every(ss => {
                        return this.selection.includes(ss);
                    })
                },
                set(checked) {
                    if (checked) {
                        this.season.forEach(ss => {
                            this.selection.push(ss);
                        })
                    } else {
                        this.selection = [];
                    }
                }
            }
            // 체크박스는 setter 선언을 이렇게 한다는 걸 정리하기 위한 예시일 뿐.. 좋은 예제는 아닌 것 같다.
        }
    }
</script>
```

[For more details about Computed-Setter](https://vuejs.org/v2/guide/computed.html#Computed-Setter)

### mixins
좀 더 공부를 해야겠지만, Interface Class같은 느낌이다.

```javascript
// WarningUtil.js
export const WARNING_MIXINS = {
    methods: {
        getWarningString(e) {
            return `DEFAULT ERROR => ${e.message}`;
        }
    }
};
```

```javascript
<template>
    <div>
        <div>
            {{ warningMsg1 }}
        </div>
        <div>
            {{ warningMsg2 }}
        </div>
    </div>
</template>
<script>
    import * as WarningUtil from 'WarningUtil.js'

    export default {
        mixins: [WarningUtil.WARNING_MIXINS],
        data() {
            return {
                error1: { code: 404, message: 'NOT FOUND' },
                error2: { code: 500, message: 'Internal Server Error' }
            };
        },
        computed: {
            warningMsg1() {
                return this.getWarningMsg(this.error1);
            },
            warningMsg2() {
                return this.getWarningMsg(this.error2);
            }
        },
        methods: {
            getWarningMsg(err) {
                if (err.code === 404)
                    return `CUSTOM ERROR => ${err.message}`;

                // mixins에서 불러오기.
                return this.getWarningString(err);
            }
        }
    }
</script>
```
[For more details about Mixins](https://vuejs.org/v2/guide/mixins.html#Basics)

