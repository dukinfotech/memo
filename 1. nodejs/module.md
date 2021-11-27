## Module
  - Return của hàm `require` trả về object `module.exports`
  - Khi trong 1 file js chỉ expose duy nhất 1 object thì sử dụng `module.exports`
  ```js
    module.exports = { name: 'Duc', birth: 1995 }
    const person = require('./person')
  ```
  - Khi trong 1 file js expose nhiều object thì sử dụng `module.exports.person` hoặc `exports.person`
   ```js
    exports.person = { name: 'Duc', birth: 1995 }
    const { person } = require('./car')
  ```