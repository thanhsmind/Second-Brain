# PHP Composer Version Settings
#phplanguage, #composer #tildeversion

- [[composer-exactly-version]]: Đánh chính xác 1 version phụ thuộc
- [[composer-specify-upper-lower-bounds-version]]: Sử dụng toán tử  ` >, <, >=, <=` để đánh dấu version phụ thuộc 
- [[composer-wildcard-version]]: Sử dụng toán tử `*` widlcard
- [[tilde-version-range]]: Sử dụng `~` trong cấu hình version Tilde Version Range `~`
- [[caret-version-range]]: Sử dụng dấu `^` trong cấu hình version Caret Version Range `^`


### Tổng quát các loại cấu hình version
```
"require": {
    "vendor/package": "1.3.2", // exactly 1.3.2

    // >, <, >=, <= | specify upper / lower bounds
    "vendor/package": ">=1.3.2", // anything above or equal to 1.3.2
    "vendor/package": "<1.3.2", // anything below 1.3.2

    // * | wildcard
    "vendor/package": "1.3.*", // >=1.3.0 <1.4.0

    // ~ | allows last digit specified to go up
    "vendor/package": "~1.3.2", // >=1.3.2 <1.4.0
    "vendor/package": "~1.3", // >=1.3.0 <2.0.0

    // ^ | doesn't allow breaking changes (major version fixed - following semver)
    "vendor/package": "^1.3.2", // >=1.3.2 <2.0.0
    "vendor/package": "^0.3.2", // >=0.3.2 <0.4.0 // except if major version is 0
}
```
ref: https://getcomposer.org/doc/articles/versions.md