## 테스트 요구 사항

### 개요

성별에 따라 프로필을 볼수 있는 페이지를 구현해주세요.

### 구현 요구 시항

1. 화면 제작
   - [figma 디자인 시안 확인하기](https://www.figma.com/file/5GzxXLiLljst6IO2W38iJO/Front-assignment?type=design&node-id=1-141&mode=design&t=ATxXcYe1BaaMZQCA-0)
    - 화면 너비가 `960px 이상`의 화면에서는 프로필이 row 당 5개가 노출되어야 합니다.
    - `960px 미만`의 화면에서는 프로필이 row당 2개가 노출되어야 합니다.

2. API 통신
    - 제공하는 **https://randomuser.me/api** 를 사용해주세요.
        - 필요한 검색 쿼리 파라미터로 `results(=응답 갯수)`, `gender(=성별)`가 있습니다.
        - api 관련하여 [api 문서](https://randomuser.me/documentation)에서 확인해주세요.
        - `src/types.ts`에 아래와 같이 api 요청 응답 관련 타입이 정의되어 있습니다.
            
            ```jsx
            // api response type
            export interface Response {
              results: Result[];
              info: Info;
            }
            
            export interface Result {
              gender: string;
              name: Name;
              location: Location;
              email: string;
              login: Login;
              dob: Dob;
              registered: Registered;
              phone: string;
              cell: string;
              id: Id;
              picture: Picture;
              nat: string;
            }
            
            export interface Name {
              title: string;
              first: string;
              last: string;
            }
            
            export interface Location {
              street: Street;
              city: string;
              state: string;
              country: string;
              coordinates: Coordinates;
              timezone: Timezone;
            }
            
            export interface Street {
              number: number;
              name: string;
            }
            
            export interface Coordinates {
              latitude: string;
              longitude: string;
            }
            
            export interface Timezone {
              offset: string;
              description: string;
            }
            
            export interface Login {
              uuid: string;
              username: string;
              password: string;
              salt: string;
              md5: string;
              sha1: string;
              sha256: string;
            }
            
            export interface Dob {
              date: string;
              age: number;
            }
            
            export interface Registered {
              date: string;
              age: number;
            }
            
            export interface Id {
              name: string;
              value?: string;
            }
            
            export interface Picture {
              large: string;
              medium: string;
              thumbnail: string;
            }
            
            export interface Info {
              seed: string;
              results: number;
              page: number;
              version: string;
            }
            ```
3. 구현 사항
   1. 50개의 results (= 50명의 유저 정보)를 요청해주세요.
   2. 초기 gender 선택값으로 male 버튼이 선택 되어있습니다. 
   3. female ****버튼을 클릭시, 여성에 대한 데이터만을 받아올 수 있게 api 요청해주세요. (반대로 male ****버튼 클릭시, 남성에 대한 데이터만 받아옵니다.)
   4. 최초 데이터를 받아올때, 로딩중 텍스트를 화면에 표시해주세요.
   5. 만약 데이터가 없다면, 없음 텍스트를 화면에 표시해주세요.
   6. 데이터를 받아오는 중에 에러가 발생한다면 alert를 이용하여 response의 에러메시지를 노출시켜주세요

