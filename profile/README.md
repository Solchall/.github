# 뭐 찾으세요?: 온라인 가상 점원 서비스

## 👕 Service Flow
![Service Flow](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FXCSOD%2FbtsiOHaZXuD%2FJ2NNaPCC8urxb9AVehSeyK%2Fimg.png)

## 👗 Prototype

[Figma](https://www.figma.com/proto/yS1dxiMOGnS8T1DuY0D3aB/%EC%95%84%ED%82%A4%ED%85%8D%EC%B3%90?page-id=201%3A6&type=design&node-id=308-499&viewport=106%2C618%2C0.04&scaling=scale-down&starting-point-node-id=308%3A94)

![캡스톤_동적프로토](https://github.com/Solchall/.github/assets/71062967/540e803c-e885-4967-b428-3e9083b0f4d4)

<br>


## 👒 Prompt Engineering and LLMs with Langchain
### 1. 상품 DB 필터링 API
소스코드: [Solchall/filtering-prompt](https://github.com/Solchall/filtering-prompt) <br>

<img width="500" alt="image" src="https://github.com/Solchall/.github/assets/71062967/69c7ef0a-5243-4163-ad1b-365e327b5de6">
<br>

- apikey: [OpenAI API KEY](https://platform.openai.com/account/api-keys)
- prompt: 찾고싶은 상품(현재는 상의 한정)에 대한 설명

<br>

[FastAPI docs](https://hidden-anchorage-81661.herokuapp.com/docs)에서 이 API를 테스트 해볼 수 있습니다. <br>
1. `/lang/` > `Try it out`을 클릭 <br>
2. `apikey`에 해당하는 `string`에 본인의 [OpenAI API key](https://platform.openai.com/account/api-keys) 넣기 <br>
3. `prompt`에 해당하는 `string`에 찾고싶은 상품(현재는 상의 한정)에 대해 적기 <br>
   - 예시1) 40,000원 이하 스프라이트 블랙 니트를 찾아줘 
   - 예시2) 4만원대 브라운 맨투맨 추천해줘. 4개월 동안 판매가 많은순으로 정렬해줘 
   - 예시3) 10만원 이하로 베이지 린넨소재 셔츠 찾아줘. 3달내 리뷰순으로 정렬해줘 

![image](https://github.com/Solchall/.github/assets/71062967/9339ce58-73c9-4427-ac94-bd2035126ecd)




<br>

### 2. 컨텐츠 DB 선정 API
소스코드: [Solchall/filtering-magazine](https://github.com/Solchall/filtering-magazine) <br>

<img width="500" alt="image" src="https://github.com/Solchall/.github/assets/71062967/50ca84cf-28a3-4ff8-828f-736761ead0a3">
<br>

- apikey: [OpenAI API KEY](https://platform.openai.com/account/api-keys)
- prompt: 찾고싶은 매거진에 대한 설명

<br>

[FastAPI docs](https://gentle-sands-05392.herokuapp.com/docs)에서 이 API를 테스트 해볼 수 있습니다. <br>
1. `/magazine/` > `Try it out`을 클릭 <br>
2. `apikey`에 해당하는 `string`에 본인의 [OpenAI API key](https://platform.openai.com/account/api-keys) 넣기 <br>
3. `prompt`에 해당하는 `string`에 찾고싶은 매거진에 대해 적기 <br>
   - 예시1) 요즘 트렌디한 상의 찾아줘
   - 예시2) 뉴진스가 입을 것 같은 옷 알려줘
   - 예시3) 바캉스 갈 때 입을 옷 추천해봐

![image](https://github.com/Solchall/.github/assets/71062967/4effd7ce-ee19-4a2d-a92f-7a45e8240fe4)


## 👒 Chrome Extenstion Interacting with Web Site

### 1. 크롬 익스텐션 요소 기술 구현

**1-1. 서비스 플로우 명세**
* [x] UI 및 인터랙션 플로우  - [프로토 타입](https://www.figma.com/proto/yS1dxiMOGnS8T1DuY0D3aB/%EC%95%84%ED%82%A4%ED%85%8D%EC%B3%90?page-id=201%3A6&type=design&node-id=308-499&viewport=106%2C618%2C0.04&scaling=scale-down&starting-point-node-id=308%3A94)<br/>

**1-2. 다중 Tab 제어 및 Web Contents 접근**

[깃허브 소스 코드 레포](https://github.com/Solchall/chrome-extension/tree/main/Crawl%20Multi%20Tabs%20-%20React)
* [x] open된 다수의 탭의 정보 불러오기
* [x] open된 다수의 탭 중 host에 따른 서로 다른 web content 조작 구동
* [x] open된 다수의 탭의 web content (썸네일, 제목, 조회수/좋아요) 정보 가져와 팝업 창에 조회수 순 나열<br/>

**1-3. REST API 연결 및 Storage 활용**

[깃허브 소스 코드 레포](https://github.com/Solchall/chrome-extension/tree/main/API%20-%20Option%20Page)
* [x] 익스텐션 웹페이지 form 생성과 유저 입력값 핸들링
* [x] 익스텐션 웹페이지 내 http 기반 REST API 연결
* [X] chrome Storage 값 get/set

**1-4. Web Socket 기반 채팅 및 페이지 다이나믹 랜더링**
* [ ] 익스텐션 팝업 내 web socket 기반 채팅 통신
* [ ] 익스텐션 팝업 내 페이지 전환 기법에 대응하는 기술 

### 2. 크롬 익스텐션 실행 방법
다음의 [READ ME](https://github.com/Solchall/chrome-extension/blob/main/Crawl%20Multi%20Tabs%20-%20React/README.md)과정을 따라 직접 실행할 수 있습니다.

<table>
    <tr>
       <th>Web Content 접근 버튼 클릭 전</th>
       <th>지정한 탭에서만 Web Contents 끌어옴</th>
        <th>지정한 탭 아닌 곳에서는 텍스트 색상 변경함</th>
   </tr>
    <tr>
       <td><img width="1425" alt="image" src="https://github.com/Solchall/.github/assets/67853616/89da4c96-0882-4f55-83ea-03aef55b1098"></td>
       <td><img width="1391" alt="image" src="https://github.com/Solchall/.github/assets/67853616/3a0fdd05-eef1-4fc2-a427-751260374b7f"></td>
       <td><img width="1108" alt="image" src="https://github.com/Solchall/.github/assets/67853616/901c67f1-de38-4fcd-90d0-b6a1bcbb87aa"></td></tr>
</table>






### 3. 주요 구현 코드

**3-1. 다중 Tab 제어**
1. `async function getAllTabs()` : [열린 모든 Tab 정보를 받아오는 함수](https://github.com/Solchall/chrome-extension/blob/main/Crawl%20Multi%20Tabs%20-%20React/src/background/tabControl.tsx#L1)

**3-2. Web Content 접근**

[활용 아키텍쳐 설명](https://hixsch-kixsch59.tistory.com/105)
![아키텍처](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FcrJALl%2FbtshjudYldv%2FhrYjWjCi6W3117lyVlDWu0%2Fimg.png)
* `crawlMultiTabsHandler` : [유저의 이벤트에 따른 메세지 API 송신/수신 발생](https://github.com/Solchall/chrome-extension/blob/main/Crawl%20Multi%20Tabs%20-%20React/src/popup/popup.tsx#L26)
* `function checkUrlFromTab(url: string)` : [특정 Tab URL에 따라 실행되는 js 파일 지정하는 함수](https://github.com/Solchall/chrome-extension/blob/main/Crawl%20Multi%20Tabs%20-%20React/src/background/tabControl.tsx#L1)

### 4. 시연 및 테스팅 영상
* [깃허브 소스 코드 레포](https://github.com/Solchall/chrome-extension/tree/main/Crawl%20Multi%20Tabs%20-%20React)
* [시연 및 테스팅 영상](https://drive.google.com/file/d/176k4IrIkyV97IYE2huRrtBUHC6b9FOly/view)
