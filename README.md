# IngredientsProject
화장품의 영문 전성분 라벨을 촬영하면 성분의 안전 등급을 보여준다.

## 프로젝트 설명
본 프로젝트는 클린 뷰티 및 비건 등이 화장품 업계 트랜드로 떠오르는 등 화장품 성분에 대한 소비자의 관심이 높아지는 상황속에서<br/>
업계 근무 경험을 통해 성분의 안전성 정보에 보다 더 간단하고 화장품에 대한 사전 정보 없이 접근할 수 있게 하고자 하는 의도로 기획되었다.<br/>
화장품 명을 알아야 하거나 국문 성분명만 인식 가능한 타 서비스와 달리 본 프로젝트는 화장품에 대한 정보 없이<br/>
특히 해외 제조 화장품에 대하여 영문 성분명만 가지고 성분에 대한 간단한 정보를 제공한다.<br/>
앱에서 제공되는 성분 안전 등급은 미국의 비영리 환경 단체인 EWG(Environment Working Group)에서 제공하는 Skin Deep 성분 안전 등급을 따른다.

## 주요 기술 요소
- 촬영한 사진의 텍스트 인식을 위한 OCR API는 CocoaPods을 통해 설치한 Google에서 제공하는 MLKit을 사용하였다.
- HomeViewController 에서 Show Result 버튼을 터치하면 OCR이 시행된다.
- 메인 화면은 TabBar로 이동한다.
- 튜토리얼 뷰는 ScrollView로 만들어졌다.
- 사용 기술: swift(5.7.2), python, SQLite
- 지원 버전: iOS 16.0 이상

## Database
- <b/>Skin Deep Data</b>
  - API 제공을 하지 않아 홈페이지에서 전성분 데이터를 python으로 크롤링한 뒤 SQLite 타입으로 저장하였다.
  - 사용 데이터: 영문성분명, 성분안전등급
- <b/>식품의약품안전처 제공 API</b>
  - API 구조상 인식된 영문 성분명으로 국문 성분명을 검색하기 어렵고 매 번 매칭을 진행하면 시간 복잡도가 올라가므로 식품의약품안전처 API를 SQlite 타입으로 저장하였다.
  - 사용 데이터: 영문성분명, 국문성분명
- <b/>최종 사용 Database</b>
  - Skin Deep Data와 식품의약품안전처 API Data의 영문성분명 교집합에 대해서 SQLite 테이블 병합을 진행
  - 사용 데이터: 영문성분명, 국문성분명, 성분안전등급

## 스크린샷
### 튜토리얼
|제목|이미지|이미지2|이미지3|이미지4|
|:-:|:-:|:-:|:-:|:-:|
|실행 영상|<img width="210" alt="튜토리얼 영상" src="https://github.com/Eunice0927/IngredientsProject/assets/106911494/27222f5f-3832-4fc8-b3e7-3a5b388f1321">|||||
|스크린샷|<img width="210" alt="tutorial1" src="https://github.com/Eunice0927/IngredientsProject/assets/106911494/0b1427a9-249a-4dab-aae2-0d6d881ae443">|<img width="210" alt="tutorial2" src="https://github.com/Eunice0927/IngredientsProject/assets/106911494/60721277-b86e-425a-bb01-99f66b75a07b">|<img width="210" alt="tutorial3" src="https://github.com/Eunice0927/IngredientsProject/assets/106911494/d1d42c8e-059a-4cd7-8396-0ddfb150a788">|<img width="210" alt="tutorial4" src="https://github.com/Eunice0927/IngredientsProject/assets/106911494/d00216b7-4f14-4840-bbcd-425269b79345">|

### 기본 홈 화면
|<img width="210" alt="기본 홈 화면" src="https://github.com/Eunice0927/IngredientsProject/assets/106911494/f52de975-4b85-4029-a5f3-77971cd64883">|
|:-:|

### 카메라 사용
|제목|이미지|
|:-:|:-:|
|실행 영상|<img width="210" alt="실행 영상" src="https://github.com/Eunice0927/IngredientsProject/assets/106911494/e0925da0-d8b1-40c1-8ecb-5852fba75af8">|
|카메라 권한 요청|<img width="210" alt="카메라 권한 요청" src="https://github.com/Eunice0927/IngredientsProject/assets/106911494/43682ff6-3a40-43e6-bc31-cae708db9cc9">|
|카메라 사용|<img width="210" alt="카메라 사용" src="https://github.com/Eunice0927/IngredientsProject/assets/106911494/5e1dc111-a878-4841-9f19-ad8a085e9a29">|
|사진 선택 완료|<img width="210" alt="사진 선택 완료" src="https://github.com/Eunice0927/IngredientsProject/assets/106911494/4254da11-34fe-455d-9b20-e237769a7330">|

### 갤러리 사용
|제목|이미지|이미지2|이미지3|
|:-:|:-:|:-:|:-:|
|실행 영상|<img width="210" alt="실행 영상1" src="https://github.com/Eunice0927/IngredientsProject/assets/106911494/8bad76cf-1aac-41cc-824e-0964f5f3a79b">|<img width="210" alt="실행 영상2" src="https://github.com/Eunice0927/IngredientsProject/assets/106911494/60dced90-8de5-4a22-8c67-359f6813f261">|<img width="210" alt="실행 영상3" src="https://github.com/Eunice0927/IngredientsProject/assets/106911494/9b70be66-a60d-422c-bf93-89f824c47f93">|
|갤러리 사진 선택|<img width="210" alt="갤러리 사진 선택" src="https://github.com/Eunice0927/IngredientsProject/assets/106911494/4254da11-34fe-455d-9b20-e237769a7330">|||

### OCR 결과 리스트
|제목|이미지|
|:-:|:-:|
|결과 화면|<img width="210" alt="결과 화면" src="https://github.com/Eunice0927/IngredientsProject/assets/106911494/f6a287e1-80a8-4069-a6cb-87837aca776c">|
<!--|실행 영상|<img width="210" alt="실행 영상" src="">|-->

## 추가 개발 필요한 내용
- [ ] DB에서 검색되지 않은 상품은 결과 화면에 보여지지 않는 이슈
- [ ] 성분을 구분하는 구분자를 브랜드마다 다른 기호로 표기한 점 보완 방안
- [ ] 동일한 성분명을 브랜드마다 조금씩 다른 단어로 작성한 점 보완 방안
- [ ] 곡면에 부착된 전성분 사진 인식률 개선을 위한 촬영된 사진 개선 기능 추가
- [ ] 인식된 텍스트의 오타 검사 기능

