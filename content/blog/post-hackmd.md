# HackMDから投稿してみた

## 文字

あいうえお
**あいうえお**
*あいうえお*
~~あいうえお~~

## 図

![](https://i.imgur.com/grSAWUc.png)


## 表とリンク
| あいうえお | からはじまるもの |
| -- | :- |
| あ | - |
| い | - |
| う | [うどん](https://ja.wikipedia.org/wiki/うどん) |
| え | - |
| お | - |

## リスト
* あ
* い
* うどん
* え
* お

1. うどん
2. ラーメン
3. そば
4. そういうこと

- [ ] うどんチェック
- [ ] 朝食うどん
- [ ] 昼食うどん
- [ ] 夕食うどん

## 絵文字
🍔

## コードブロック
`main.py`
```python=
from fastapi import Depends, FastAPI
from starlette.templating import Jinja2Templates
from starlette.requests import Request
from starlette.responses import RedirectResponse
from database import SessionLocal
import crud
import schemas

app = FastAPI()

def get_db():
    db = SessionLocal()
    try:
        yield db
    finally:
        db.close()      
︙
@app.get("/", response_model=List[schemas.Place])
def read_places(request: Request, db: Session = Depends(get_db)):
    db_places = crud.get_places(db)
    return templates.TemplateResponse('index.html', {'request': request, 'place':db_places})

@app.delete("/delete/{p_id}", response_model=schemas.Place)
def delete_place(p_id: int, db: Session = Depends(get_db)):
    place = schemas.Place
    place.id = p_id
    crud.delete_place(db=db, place=place)
    return RedirectResponse("/")
︙
```

## 引用

> きょうのあしたもあさってもうどん


## 線


---


---

## コメント
> [TOC]

> [name=大浦翼]

> あ
> [color=#279b15]

> [time=Tue, Sep 14, 2021 7:59 AM]

