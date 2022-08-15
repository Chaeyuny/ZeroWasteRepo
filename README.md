# 🌱 ECO:BACK ( 팀명 : 여따담아조 )



## ✅ 서비스 소개
### ✏ 서비스명 
###       : 지도 라이브러리 기반 제로웨이스트 실천 안내 서비스
<br>

### ✏ 서비스 설명
 : 평소 제로웨이스트 운동에 참여하고 싶었지만 제로웨이스트를 시행하는 매장 위치와 정보가 부족해
   불편함을 겪었던 사람들을 위한 서비스
 
 : 제로웨이스트 의미, 매장 위치와 정보, 연계 쿠폰 제공 등 선순환되는 서비스 제공을 통해 
   다회용기 활용을 유도하여 환경운동에 보다 쉽게 접근하도록 돕는다.

<br>

## ✅ 프로젝트 기간
2022.06.03 ~ 2022.06.18 (2주)

<br>

## ✅ 주요 기능
* 지도에서 주변 제로웨이스트 매장들의 위치를 표시
* 위치 마커 클릭 시 제로웨이스트 매장 정보 안내 페이지로 이동
* 음식 종류별 카테고리 선택 또는 매장명 검색 기능을 통해 제로웨이스트 시행 매장 확인 가능
* 영수증 인증과 매장 리뷰를 등록시킬 수 있는 사용자 커뮤니티 게시판
* 제로웨이스트 실천 횟수에 따라 사용자의 에코등급 시각화
* 에코 등급에 따른 제로웨이스트 생필품 샵과의 연계 쿠폰 구현
* 지도에 표시될 신규 제로웨이스트 매장등록 시 매장 위치 경도, 위도 자동 매핑 기능
* 웹과 앱화면 모두 구동 가능하도록 반응형 웹사이트로 구현

<br>


 ## ✅ 담당 역할
    : KAKAO Map API를 활용한 제로웨이스트 매장 안내 서비스 구현

<br>
<h4>✔ 사용기술</h4>
<table>
    <tr>
        <th>구분</th>
        <th>내용</th>
    </tr>
    <tr>
        <td>사용언어</td>
        <td>
            <img src="https://img.shields.io/badge/Java-007396?style=for-the-badge&logo=java&logoColor=white"/>
            <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=JavaScript&logoColor=white"/>
        </td>
    </tr>
    <tr>
        <td>라이브러리</td>
        <td>
            <img src="https://img.shields.io/badge/KakaoMap-FFCD00?style=for-the-badge&logo=Kakao&logoColor=white"/>
        </td>
    </tr>
    <tr>
        <td>개발도구</td>
        <td>
            <img src="https://img.shields.io/badge/Eclipse-2C2255?style=for-the-badge&logo=Eclipse&logoColor=white"/>
        </td>
    </tr>
    <tr>
        <td>서버환경</td>
        <td>
            <img src="https://img.shields.io/badge/Apache Tomcat-D22128?style=for-the-badge&logo=Apache Tomcat&logoColor=white"/>
        </td>
    </tr>
    <tr>
        <td>데이터베이스</td>
        <td>
            <img src="https://img.shields.io/badge/Oracle 11g-F80000?style=for-the-badge&logo=Oracle&logoColor=white"/>
        </td>
    </tr>
</table><br>



* 매장정보, 회원정보 DB 설계 및 구현 참여

* KAKAO Map API를 활용해 DB에 입력된 제로웨이스트 매장 위치 마커 표시 기능 구현

* Javascript를 이용한 음식 종류 별 카테고리 선택 기능 구현 
   - 카테고리를 선택하면 DB값과 비교하여 해당하는 매장들의 위치를 표시하는 기능
   - API가 제공하는 카테고리는 약국, 편의점 등의 시설로 정해져 있어서 사용 불가 -> 자체적으로 DB 값을 필터링하여 마커로 표시하도록 재구현
   
* 지도에서 곧바로 매장 위치를 확인할 수 있는 매장명 검색 기능 구현
   - 전국 단위 검색이 가능하도록 짜여진 API코드를 구현 당시 원하는 지역에서만 검색할 수 있도록 변형
   
* Kakao MAP API 마커 클릭 시 매장정보를 즉시 확인할 수 있는 오버레이 구현
   - 오버레이 내에는 매장 관련 간단한 정보와 상세보기 페이지 URL 첨부
   
<br><br>



## ✅ 트러블슈팅
  
📌 문제1 : 지도 페이지로의 이동<br>
   - Mybatis MVC 패턴을 기반으로 메인페이지에서 지도 페이지로의 이동단을 구현할 당시 발생했다.<br>
      이동할 때 필요한 요소를 모두 채웠다고 생각했으나 메인페이지에서 지도 페이지로 이동하는 버튼 설정을 하지 않아서 <br>
      사용자 요청 자체가 이루어지지 않아 생긴 간단한 문제였다.
 
     💡  간단한 서버 단 이동에서 발생한 오류였고, 어떤 식으로 흘러가는지 파악하는 게 중요했던 것 같다.<br> 
        알 수 없는 에러에 집착하다 보니 기본적인 것을 놓친 경우였다.
 
<br> 
<br>

📌 문제2 : 카테고리 검색 기능 문제<br>
   - KAKAO Map API에 카테고리 검색 코드가 정리되어 있어서 이를 적용하려고 했는데, 구현하고자 하는 기능이 아니었다.<br>
      병원, 편의점, 약국 등 실제 지도 사용자들이 편리하게 찾아볼 수 있는 것들만 정해져 있었고, 이에 따른 코드가 모두 지정되어 바꿀 수 없었다. <br>
      즉, 가져다 쓸 수 없는 코드였다.<br>
      
   - DB에 저장된 제로웨이스트 매장들을 한식, 중식, 양식 등으로 자체 필터링할 수 있는 코드를 구현해 해결했다. <br>
    
 
 

![image](https://user-images.githubusercontent.com/103619605/184651837-dcfa97ea-ede2-449d-b96d-4cea45a023b8.png)



<br>
  💡 API를 원하는 기능에 맞게 구현하는 작업이 쉬운 일이 아니라는 것을 느꼈다. <br>
 
  💡 무엇보다도 API를 사용할 때에는 코드 이해와 흐름 파악이 가장 중요하다는 것을 알았다. <br>
    코드를 알고 흐름을 파악해야 원하는 타이밍에 원하는 기능을 넣기가 수월했다.
   
   

<br>
<br>

 
📌 문제3 : 키워드 검색 문제<br>
   - 광주 동명동으로 지역을 한정해서 진행했는데, 매장명 검색을 통해 위치를 찾으려고 하면 전국 단위로 검색되어 기준점을 벗어나 전국 지도가 나오는 문제가 발생했다. 
   - API 검색 기능은 키워드 입력 시 일치하는 검색 결과를 상위 15개만 노출시킨다. 즉, 동명동 매장이 15개 결과에 포함되지 않으면 DB 에 있더라도 매장 위치가 표시되지 않는 문제가 함께 발생한 것이다.<br>
   - 상위 15개만 가져오는 코드는 API로 공개되지 않았기 때문에 해당 부분을 손댈 수 없었다.
 
   - 사용자 검색어 뒤에 코드 내부적으로 '광주'라고 범위를 지정하여 검색하도록 코드를 변형했다.
  ![image](https://user-images.githubusercontent.com/103619605/184654175-b48adb9b-ba85-44dc-aabb-0d94e9031336.png)
 <br>
 
   - 이렇게 1차 필터링 된 매장들 중에서 DB에 저장된 주소와 실제 매장 주소가 같은 값을 불러와 원하는 제로웨이스트 매장만 표시되도록 구현해 해결할 수 있었다.
 ![image](https://user-images.githubusercontent.com/103619605/184654064-15f81e6c-5708-406d-8300-37f5047d0522.png)

<br>
   💡 API 코드는 모두 Javascript로 이루어져 있었는데, 검색의 경우 값을 가지고 비교하고 로드하는 작업이 많았다. <br>
 
   💡 추측해서 무작정 실행하는 것보다는 콘솔에 찍어보는 작업을 하는 것이 많은 도움이 되었다.<br>
 
   💡 내가 생각하는 흐름이 맞는지, 값을 잘 가져오는지 등을 판단하기 수월했고, 있는 코드를 재구현 하다 보니 꼬이는 경우가 많아서<br>
       콘솔에 찍어보면 어디부터 잘못되었는지 비교적 쉽게 알 수 있었다.

 
<br><br>

<details>
<summary><h2>✅프로젝트 상세</h2></summary>


## 📌 시스템 아키텍처 구조
![image](https://user-images.githubusercontent.com/103619605/182366619-1c5ad67d-7b9d-4844-bcef-00ca75498f61.png)
<br>
<br>
<br>


## 📌 SW유스케이스
![스크린샷(27)](https://user-images.githubusercontent.com/103619605/182365968-09e3e196-5797-4fec-9eab-765e8925c9b8.png)
<br>
<br>
<br>


## 📌 서비스 흐름도
![image](https://user-images.githubusercontent.com/103620466/182580307-90a17461-0e29-4e41-9769-78865495a7a7.png)
<br>
<br>
<br>


## 📌 ER다이어그램
![image](https://user-images.githubusercontent.com/103619605/182579207-e5070ca5-2cde-43d1-94f7-5414a2d56a9f.png)

<br>
<br>
<br>



## ✅ 화면 구성

### 회원가입 / 메인화면 / 사용자 튜토리얼 화면
![image](https://user-images.githubusercontent.com/103620466/182588812-326be119-90cb-4264-b3f1-bb7eb059888f.png)
<br><br>

### 매장 보기 화면 (전체 매장 / 카테고리 선택 / 매장명 검색)
![image](https://user-images.githubusercontent.com/103620466/182589092-43fdf433-026b-47da-9d48-a5c5105ecdf3.png)
<br><br>

### 커뮤니티 게시판 화면 / 리뷰 등록 / 리뷰 수정
![image](https://user-images.githubusercontent.com/103620466/182589351-00081d31-ca43-4193-9fb2-23fa1b506990.png)
<br><br>

### 등급 시각화 / 리워드 화면 / 신규 매장등록 화면
![image](https://user-images.githubusercontent.com/103620466/182589764-d97e7c59-957b-47aa-a884-1e62ba9cd57d.png)
<br><br>
</details>



