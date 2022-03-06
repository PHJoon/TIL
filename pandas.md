## 판다스 기본
---
### 시리즈
**pandas.Series(데이터)**

- **sr.index**
- **sr.values**

- **sr['인덱스 이름'] or sr[정수형 위치]**


- **sr[['a', 'b']] or sr[[1, 2]]**
	- 인덱스 다중 지정 시 괄호 두 개

- **sr['a' : 'a']**
  - 범위는 다중 지정이 아님

- 시리즈 연산 가능
  - **sr1 + 연산자 + 숫자**
  - **sr1 + 연산자 + sr2**

- **sr.add(sr2, fill_value=0)**
  - add 대신 sub, mul, div 가능
    


---
---
### 데이터프레임
- **df = pd.DataFrame(데이터, index = [], columns = [])**
  - index와 columns 설정 안하면 자동으로 설정

- **df.index**
- **df.columns**

- 인덱스와 열 개수 맞춰서 지정해주면 이름 변경됨
  - **df.index = [' ', ' ']**
  - **df.columns = [' ', ' ']**

- 이름 바꾸기 a -> b
  - **f.rename(columns={'a' : 'b'}, inplace= )**
  - **df.rename(index={'a' : 'b'}, inplace= )**

- **inplace=True 저장함**
- **inplace=False 저장 안 함**

- **df.drop('행 이름', axis=0 or 'index')**
- **df.drop('열 이름', axis=1 or 'columns')**
- **df.drop(index=' ')**
- **df.drop(columns= ' ')**
  - 다중 지정은 [ ]

---
- 행 선택
  - **df.loc['a']**
  - **df.loc[['a', 'b']]**
  - **df.iloc[정수형 위치]**
  - **df.iloc[[1, 3]]**

- 열 선택
  - **df['a']**
  - **df.a**
  - **df[['a', 'b']]**

- 원소 선택
  - **df.loc[행 이름, 열 이름]**
  - **f.iloc[행 위치, 열 위치]**

- **df.loc[행 이름, [열 이름1, 열 이름2]]**
  - 해당 행의 열 이름1, 열 이름2 선택

- **df.loc[[행 이름1, 행 이름2], [열 이름1, 열 이름2]]**
  - 행 이름1, 행 이름2의 열 이름1, 열 이름2 선택

---
- 행 추가하기
  - **df.loc['새로운 행 이름'] = ['a', 'b', 'c']**
- 기존 행 복사하여 추가
  - **f.loc['새로운 행 이름'] = df.loc['기존 행']**

- 열 추가하기
  - **f['추가할 열 이름'] = ['a', 'b', 'c']**

- 중간에 열 추가하기
  - **df.insert(추가할 위치(정수형), 'a', ['b', 'c', 'd'])**

---
- 원소 값 변경
  - **df.iloc[행 위치, 열 위치] = 'a'**
  - **f.iloc[행 위치][열 위치] = 'a'**
  - **df.loc['행 이름', '열 이름'] = 'a'**
  - **df.loc['행 이름']['열 이름'] = 'a'**
  - **f.loc[행 이름, [열 이름1, 열 이름2]] = 'a', 'b'**
  - **df.loc[[행 이름1, 행 이름2], [열 이름1, 열 이름2]] = 배열 형태**

---
- 열을 새로운 인덱스로 지정(2개 가능)
  - **df.set_index('a', inplace= )**



- 행 인덱스 이름 설정
  - **df.index.name = 'a'**

- 행 인덱스 이름 바꾸기
  - **df.index.rename('a', inplace= )**

- 정수형 위치 인덱스로 초기화
  - **df.reset_index('a', inplace= )**

- 행 인덱스 재배열
  - **df.reindex(new_index)**
  - new_index = [5, 4, 3]

---
- 행 인덱스 기준으로 정렬
  - **f.sort_index(ascending= )**

- 특정 열의 데이터 값 기준으로 정렬
  - **f.sort_values(by='열 이름', ascending= )  **

- 행 열 위치 바꾸기(전치)
  - **df.transpose()**
  - **df.T**


---
- csv파일
  - **pandas.read_csv('파일 경로(이름).csv')**

- excel파일
  - **pandas.read_excel('파일경로(이름).xlsx')**
    - 파일 못 읽어올 경우 engine='openpyxl' 옵션 사용

- JSON파일
  - **pandas.read_json('파일경로(이름).json')**

- 여러 옵션 확인

---
- **df.head()**

- **df.tail()**

- **df.shape**

- **df.info()**

- **.dtypes**

- **df.describe()**
  - **df.describe(include='all') 고유값, 최빈값, 빈도수 추가 출력**

- **df.mean()**
  - **df['열 이름'].mean()**

- **df.median()**
  - **df['열 이름'].median()**
  - 데이터 개수 짝수일 경우 중간값 2개 사이의 값 출력

- **df.max()**
  - **df['열 이름'].max()**

- **df.min()**
  - **df['열 이름'].min()**

- **df.std()**
  - **df['열 이름'].std()**

- 상관계수
  - **df.corr()**
  - **df[열 이름 리스트].corr()**
    - r > 0 : 양의 상관관계(기울기 양수)
    - r < 0 : 음의 상관관계(기울기 음수)