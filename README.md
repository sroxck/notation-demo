
# 文本标记-注释效果demo

1. 引入rough-notation库
``` ts
// pnpm install rough-notation
import { annotate } from 'rough-notation';
```

2. 获取要标记的元素

``` ts
  const e = document.querySelector<HTMLElement>('#myElement')!
```
3. 配置标记
``` ts
   const annotation = annotate(e, { type: 'underline',color:'green' });
```
4. 调用动画
``` ts
annotation.show()
```
5. 清除标记
``` ts
annotation.hide()
```

## 官网
https://roughnotation.com/
