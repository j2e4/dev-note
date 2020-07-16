# lodash
See the [lodash Official](https://lodash.com/) for more details

### ForEach
File 타입의 List와 같은 Collection 타입을 Array.prototype.forEach()처럼 사용할 수 있게 해준다.
```javascript
import { forEach } from 'lodash-es';

/** @param {Array.<File>} files */
function printFileNms(files) {
    forEach(files, (file, i) => {
        console.log(`${i + 1}번째 파일 이름: ${file.name}`);
    });
}
```