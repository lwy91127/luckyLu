title: Django静态文件配置
date: 2015-10-20 14:38:22
tags: python
---

### Djano 1.8以上：

- settings.py 中加入:
```python
STATICFILES_DIRS=(os.path.join(BASE_DIR,'static'),)
```

- 模板文件开始处加入:
```bash
{% load staticfiles %}
```

- 模板文件中使用:
```html
/static/...
或者 
{% static '...' %}
```
