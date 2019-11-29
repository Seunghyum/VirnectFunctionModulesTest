# Function_Modules

## 기능리스트

- gateway : Gateway path 모음
- v-validate : User Form Validation

## 사용법

#### 기본전제

1. 작업중인 로컬의 package.json안에 ```private: true``` 가 없어야 함.
2. ```$ verdaccio```
3. ```npm set registry http://localhost:4873/```

그 다음은 npm i을 이용하면 됨.
만약 registry setting을 전역으로 하지않고 부분만 하고 싶으면 
```bash
$ NPM_CONFIG_REGISTRY=http://localhost:4873 npm i
```
하면 된다.

> Now you can navigate to http://localhost:4873/ where your local packages will be listed and can be searched.
> Warning: Verdaccio does not currently support PM2's cluster mode, running it with cluster mode may cause unknown behavior.

#### 패키지 다운로드

```bash
$ npm install --global verdaccio
```


#### 패키지 수정 후 배포

해당 패키지 수정 후 패키지 폴더로 진입

```bash
// ex)
$ cd v-validate
```

#### 1. create an user and log in

```bash
$ npm adduser --registry http://localhost:4873
```

#### 2. publish your package

```bash
$ npm publish --registry http://<내부 Verdaccio IP>:<내부 Verdaccio 포트>

// ex)
$ npm publish --registry http://localhost:4873
```