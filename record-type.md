# Record< Keys, Type>
#typescript
Khởi tạo instace của Type bằng cách sử dụng để map properties của type tới 1 type khác
```javascript
interface PageInfo {
  title: string;
}

type Page = "home" | "about" | "contact";

const nav: Record<Page, PageInfo> = {
  about: { title: "about" },
  contact: { title: "contact" },
  home: { title: "home" },
};

nav.about;
// ^ = const nav: Record

```