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
