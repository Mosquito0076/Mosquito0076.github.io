### 1. 카테고리 추가

1. `_data/navigation.yml`

```markdown
sidebar-category:
  - title: "Category"
    children:
      - title: "TIL"
        url: "/TIL"
```

여기서 아래와 같이 작성하면 됨

```markdown
	  - title: "{{ 보여줄 제목 }}"
	    url: "{{ 추가로 나오게 할 sub url }}"
```

<br>

2. `_pages`

`category-{{ 보여줄 제목 }}.md` 파일 생성 후 아래와 같이 작성

```markdown
---
title: "{{ 보여줄 제목 }}"
layout: archive
permalink: {{ 추가로 나오게 할 sub url }}
---


{% assign posts = site.categories.{{ 추가로 나오게 할 sub url }} %}
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} {% endfor %}
```

<br>

---

### 2. 글 작성

- `_posts/{{ YYYY-MM-DD-제목 }}.md`
  - ex: `2023-06-28-나는-기계다.md`
  - 띄어쓰기 또한 `-`로 입력해야함

아래와 같이 본문 작성하기

```markdown
---
title: "{{ 제목 }}"
date: {{ YYYY-MM-DD HH:MM:SS }} +0900
categories: 
	- {{ 카테고리 이름 }}
	- {{ 카테고리 이름 }}
---

{{ 본문 내용 }}
```

