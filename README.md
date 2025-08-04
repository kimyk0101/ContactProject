# ContactProject

> 풀스택 웹 개발 국비지원 과정에서 처음으로 진행한 콘솔 기반 전화번호부 관리 프로젝트입니다.  
> Java와 MySQL을 사용하여 연락처 관리, 통화/문자 기록 등의 기능을 구현했습니다.

---

## 프로젝트 기간
- 2024.11.27 ~ 2024.12.03 (7일)

---

## 사용 기술

- Java (Eclipse IDE)
- JDBC (MySQL Connector 9.1.0)
- MySQL 8.x

---

## 주요 기능

|     기능    |     설명     |
|-------------|------|
| 연락처 등록 | 새 연락처를 DB에 저장 |
| 연락처 조회 | 전체 연락처 목록을 조회 |
| 연락처 수정 | 이름, 번호, 부서 등 정보 수정 |
| 연락처 삭제 | 특정 연락처 삭제 |
| 연락처 검색 | 이름, 부서 등으로 검색 가능 |
| 통화 기능 | Java Socket 통신 기반의 시뮬레이션 시도. 간단한 연결 후 "통화 중..." 메시지를 출력하고, 종료 시 통화 기록 저장. 다만, 소켓 연결 시 예외 처리 및 쓰레드 관리에서 오류가 발생하여 완전한 기능 구현에는 실패함. |
| 문자 기능 | 특정 사원에게 문자 전송 및 메시지함 기능 (읽음 여부 포함) |

> *통화 기능은 실제 통신이 아닌 콘솔 출력 기반 시뮬레이션이며,  
> 문자 기능은 DB에 메시지를 저장하고, 각 사원의 메시지함을 통해 읽을 수 있도록 구현되었습니다.*

---

## ▶ 실행 방법

1. Eclipse로 프로젝트 import
2. `libs/mysql-connector-j-9.1.0.jar` 외부 라이브러리로 추가
3. MySQL DB 연결 정보 (`DBConnection.java` 또는 DAO 내부)에 본인 환경에 맞게 설정
4. 테이블 생성 (VO 클래스명 참고):
   - `CallRecord`, `MessageRecord`, `Employment`, `Rank`, `Regions`, `DepartmentList` 등
5. `ContactApp.java` 실행

---

## 폴더 구조

ContactProject/
├── libs/
│   └── mysql-connector-j-9.1.0.jar
├── src/com/java/
│   ├── app/
│   │   └── ContactApp.java
│   ├── dao/
│   │   └── impl/
│   │       ├── CallRecordDao.java
│   │       ├── EmploymentDao.java
│   │       └── MessageRecordDao.java
│   └── vo/
│       ├── CallRecordVo.java
│       ├── DepartmentListVo.java
│       ├── EmploymentVo.java
│       ├── MessageRecordVo.java
│       ├── RankVo.java
│       └── RegionsVo.java
├── 프로젝트_연관문서/
├── .classpath
├── .gitignore
└── .project

---

## 느낀 점

> 처음으로 진행한 미니 프로젝트였고, Java와 MySQL을 JDBC로 연결해서 데이터를 다뤄보는 경험이 새로웠습니다.  
> 콘솔 기반의 UI였지만, 사용자 흐름에 맞게 메뉴를 구성하고 예외 처리를 하면서 실제 서비스 흐름을 고민하게 되었습니다.  
> 특히 문자기능에서 메시지 읽음 여부를 구분해주는 로직을 짜는 과정에서 조건문과 DB 상태 관리의 중요성을 배웠고,  
> 통화 기능처럼 실시간 개념을 적용하려 했던 시도도 인상 깊었습니다.  
> 전체적으로 팀원들과 역할을 나누고 협업하면서 객체지향적인 구조와 패키지 분리를 처음 경험해볼 수 있었던 의미 있는 프로젝트였습니다.

---

## 개선 및 회고

- 다음에는 GUI 기반으로 확장하거나 REST API 연동까지 도전해보고 싶음
- 통화 기능을 Java의 Socket 통신으로 구현하려고 했으나, 쓰레드 충돌 및 연결 해제 처리 등에서 예외가 발생하여 안정적인 구현이 어려웠습니다.  
  비록 완성되진 않았지만, 네트워크 프로그래밍의 구조와 어려움을 경험해본 소중한 기회였습니다.
