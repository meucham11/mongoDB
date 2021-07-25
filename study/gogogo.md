### DB 생성 : use aaa
#### 첫번째 방법
```MONGODB
> use SALES
> db.createCollections("employees",{capped:true, size:100000})     capped : 저장 공간의 재사용이 가능한 타입   size : collections의 최초 익스텐트 크기
> show collections
> db.employees.stats()
```
#### 두번째 방법




### Collections 이름 변경
```mongodb
> db.employees.renameCollections("emp")
```

### Collections 삭제
```mongodb
> db.emp.drop()
```

### update
```
2가지 방법이 있다.

기존에 있는 데이터를 수정할 때.
> db.collection명.update({기존키:기존값},{$set{추가키:추가값, ...}})
- 특정 필드만 업데이트 하기 위해서...
- $set, $inc, $addToSet, $push, $pop, $pull 등

맨 마지막 행에 추가 할때.
> db.collection명.save({키:값, ...})

```

### 삭제
```
매칭 되는것 삭제
> db.collection명.remove({키:값})

내용물 삭제
> db.collection명.remove({})

컬렉션 삭제
> db.collection명.drop()
```

### UUID
```
특징:
 MongoDB 3.6 이상부터 지원되는 New Feature이다.
 각 컬렉션에게 할당된 고유 값이다.
 필수 > db.adminCommand({setFeatureCompatibilityVersion : "3.6이상"})


확인
> use db명
> db.getCollectionInfos({키:값})

설정 후 도큐먼트 생성(키는 무조건 "_id" 고정)
> use db명
> p={"_id":ObjectId("1506516516515612"),
     "ename":"jaewon", ...}
> db명.collections명.save(p)
```


### 검색
```
- 키:값이 매칭되는 가장 처음 도큐먼트 검색
 > db.collection명.findOne({키:값})

```


### 날짜
```
ISOdate 형식으로 선언
> x = new Date()
 혹은
> y = ISODate()

string 형식으로 선언
> z = Date()
 혹은
> z = now Date()
> z.toString()



> x.getYear
> x.getMonth    현재월의 -1을 반환한다.
> x.get
```



# findAndModify
참조 : https://coding-start.tistory.com/288
