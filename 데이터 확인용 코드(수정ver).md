```python
import numpy as np
import pandas as pd
```

## col_df : 컬럼정의서 / df: 데이터


```python
df = pd.read_csv ('데이터마케팅코리아/블로그행사콘텐츠.csv')
col_df = pd.read_excel('데이터마케팅코리아/컬럼정의서/블로그 행사 콘텐츠(Buzz)_컬럼정의서.xls')
```

# 1. 데이터 확인


```python
col_df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>순서</th>
      <th>컬럼영문명</th>
      <th>컬럼한글명</th>
      <th>데이터타입</th>
      <th>길이</th>
      <th>PK여부</th>
      <th>NOT NULL여부</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>SEQ</td>
      <td>일련</td>
      <td>BIGINT</td>
      <td>8</td>
      <td>Y</td>
      <td>N</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>CNTNTS_ID</td>
      <td>콘텐츠 ID</td>
      <td>TEXT</td>
      <td>100</td>
      <td>NaN</td>
      <td>N</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>CH_TY</td>
      <td>채널 타입</td>
      <td>TEXT</td>
      <td>100</td>
      <td>NaN</td>
      <td>N</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>CH_NM</td>
      <td>채널명</td>
      <td>TEXT</td>
      <td>100</td>
      <td>NaN</td>
      <td>N</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>SJ</td>
      <td>제목</td>
      <td>TEXT</td>
      <td>1000</td>
      <td>NaN</td>
      <td>N</td>
    </tr>
    <tr>
      <th>5</th>
      <td>6</td>
      <td>POST_DE</td>
      <td>게시일자</td>
      <td>DATE</td>
      <td>4</td>
      <td>NaN</td>
      <td>N</td>
    </tr>
    <tr>
      <th>6</th>
      <td>7</td>
      <td>CNTNTS_DPI</td>
      <td>콘텐츠 DPI</td>
      <td>DOUBLE PRECISION</td>
      <td>8</td>
      <td>NaN</td>
      <td>N</td>
    </tr>
    <tr>
      <th>7</th>
      <td>8</td>
      <td>LIKE_CNT</td>
      <td>좋아요수</td>
      <td>INT</td>
      <td>4</td>
      <td>NaN</td>
      <td>N</td>
    </tr>
    <tr>
      <th>8</th>
      <td>9</td>
      <td>ANSWER_CNT</td>
      <td>댓글수</td>
      <td>INT</td>
      <td>4</td>
      <td>NaN</td>
      <td>N</td>
    </tr>
    <tr>
      <th>9</th>
      <td>10</td>
      <td>CNTNTS_URL</td>
      <td>콘텐츠 URL</td>
      <td>TEXT</td>
      <td>100</td>
      <td>NaN</td>
      <td>N</td>
    </tr>
    <tr>
      <th>10</th>
      <td>11</td>
      <td>CTGRY_1_NM</td>
      <td>분류체계1</td>
      <td>TEXT</td>
      <td>100</td>
      <td>NaN</td>
      <td>N</td>
    </tr>
    <tr>
      <th>11</th>
      <td>12</td>
      <td>CTGRY_2_NM</td>
      <td>분류체계2</td>
      <td>TEXT</td>
      <td>100</td>
      <td>NaN</td>
      <td>N</td>
    </tr>
  </tbody>
</table>
</div>




```python
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>SEQ</th>
      <th>CNTNTS_ID</th>
      <th>CH_TY</th>
      <th>CH_NM</th>
      <th>SJ</th>
      <th>POST_DE</th>
      <th>CNTNTS_DPI</th>
      <th>LIKE_CNT</th>
      <th>ANSWER_CNT</th>
      <th>CNTNTS_URL</th>
      <th>CTGRY_1_NM</th>
      <th>CTGRY_2_NM</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1261673</td>
      <td>85020016fc1111ebb533002b67f7b0e1</td>
      <td>blog</td>
      <td>모모와이_MOMOY</td>
      <td>세븐틴은 KBS 가요대축제 대축제의 대기조였다 방역 기준 무시</td>
      <td>2021-01-01</td>
      <td>1.0</td>
      <td>5</td>
      <td>0</td>
      <td>https://blog.naver.com/PostView.nhn?blogId=gom...</td>
      <td>문화</td>
      <td>미술</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1261755</td>
      <td>9496dc41fc1111eb9166002b67f7b0e1</td>
      <td>blog</td>
      <td>추천하는남자</td>
      <td>법카로 최애 콘서트 열어준 덕후 김태호pd</td>
      <td>2021-01-02</td>
      <td>1.8</td>
      <td>9</td>
      <td>0</td>
      <td>https://blog.naver.com/PostView.nhn?blogId=beg...</td>
      <td>문화</td>
      <td>미술</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1261684</td>
      <td>8879616afc1111ebbd05002b67f7b0e1</td>
      <td>blog</td>
      <td>호론 HO LOAN</td>
      <td>고창 청보리밭 축제 45월축제 고창여행 전북여행 국내여행 데이트하기좋은곳 산책 힐링</td>
      <td>2021-01-02</td>
      <td>0.2</td>
      <td>1</td>
      <td>0</td>
      <td>https://blog.naver.com/PostView.nhn?blogId=pas...</td>
      <td>문화</td>
      <td>미술</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1261752</td>
      <td>940b0ecefc1111ebabd0002b67f7b0e1</td>
      <td>blog</td>
      <td>덕질 깔롱맘</td>
      <td>지민 레이블콘서트</td>
      <td>2021-01-02</td>
      <td>5.8</td>
      <td>29</td>
      <td>0</td>
      <td>https://blog.naver.com/PostView.nhn?blogId=ozo...</td>
      <td>문화</td>
      <td>미술</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1261708</td>
      <td>8ce331a6fc1111eba5ea002b67f7b0e1</td>
      <td>blog</td>
      <td>냥 일기는 너무 식상해</td>
      <td>2020 열정 연말결산 ep32020 서울지식이음축제포럼 자원활동가 도돌이</td>
      <td>2021-01-02</td>
      <td>0.8</td>
      <td>4</td>
      <td>0</td>
      <td>https://blog.naver.com/PostView.nhn?blogId=2jj...</td>
      <td>문화</td>
      <td>미술</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>95</th>
      <td>1263789</td>
      <td>1693414afc1311eb9a12002b67f7b0e1</td>
      <td>blog</td>
      <td>유타임즈 &amp; 필라이트스튜디오</td>
      <td>유타임즈 신한대학교 주 정미작소 상호 협력 협약 체결 공연예술학과 K POP 와 공...</td>
      <td>2021-01-30</td>
      <td>5.6</td>
      <td>28</td>
      <td>0</td>
      <td>https://blog.naver.com/PostView.nhn?blogId=fee...</td>
      <td>문화</td>
      <td>미술</td>
    </tr>
    <tr>
      <th>96</th>
      <td>1263786</td>
      <td>160782e9fc1311ebbd0d002b67f7b0e1</td>
      <td>blog</td>
      <td>추천하는남자</td>
      <td>라스 서현철 지방공연 에피소드</td>
      <td>2021-01-30</td>
      <td>0.4</td>
      <td>2</td>
      <td>0</td>
      <td>https://blog.naver.com/PostView.nhn?blogId=beg...</td>
      <td>문화</td>
      <td>미술</td>
    </tr>
    <tr>
      <th>97</th>
      <td>1263852</td>
      <td>22d25f22fc1311eb9e6d002b67f7b0e1</td>
      <td>blog</td>
      <td>한국교회이야기</td>
      <td>제물포 문화 선교 축제</td>
      <td>2021-01-31</td>
      <td>0.0</td>
      <td>0</td>
      <td>0</td>
      <td>https://blog.naver.com/PostView.nhn?blogId=kal...</td>
      <td>문화</td>
      <td>미술</td>
    </tr>
    <tr>
      <th>98</th>
      <td>1263826</td>
      <td>1e247c25fc1311ebbbb6002b67f7b0e1</td>
      <td>blog</td>
      <td>imagekim님의</td>
      <td>뉴욕 브로드웨이 뜻과 반대되는 판데믹현상 6660만명이 찾던 브로드웨이 타임스퀘어는...</td>
      <td>2021-01-31</td>
      <td>2.0</td>
      <td>10</td>
      <td>0</td>
      <td>https://blog.naver.com/PostView.nhn?blogId=vis...</td>
      <td>문화</td>
      <td>미술</td>
    </tr>
    <tr>
      <th>99</th>
      <td>1263805</td>
      <td>1a3d96d7fc1311eb872d002b67f7b0e1</td>
      <td>blog</td>
      <td>풍경사진or일상이야기</td>
      <td>3년 전 오늘 스페인 세비야에서 플라밍고 공연에서 춤의 고수를 보다</td>
      <td>2021-01-31</td>
      <td>8.2</td>
      <td>41</td>
      <td>0</td>
      <td>https://blog.naver.com/PostView.nhn?blogId=sjh...</td>
      <td>문화</td>
      <td>미술</td>
    </tr>
  </tbody>
</table>
<p>100 rows × 12 columns</p>
</div>




```python
df.columns
```




    Index(['SEQ', 'CNTNTS_ID', 'CH_TY', 'CH_NM', 'SJ', 'POST_DE', 'CNTNTS_DPI',
           'LIKE_CNT', 'ANSWER_CNT', 'CNTNTS_URL', 'CTGRY_1_NM', 'CTGRY_2_NM'],
          dtype='object')



# 2. 컬럼정의서 정합성


```python
##col_df_list: 컬럼정의서에 적힌 컬럼 리스트
col_df_list = list(col_df['컬럼영문명'])
##df_list: 데이터에 있는 컬럼 리스트
df_list = list(df.columns)
```

### 1차: 컬럼정의서 길이 비교


```python
len(col_df_list) == len(df_list)

##False가 나오면 어떤 부분이 다른지 직접 확인
```




    True




```python
col_df_list == df_list

##False가 나오면 어떤 컬럼명이 다른지 직접 확인
```




    True



### 2차: 컬럼명 일치 확인 (+컬럼명 한글화)


```python
count=0
try:
    for i in range(len(df.columns)):
        for j in range(len(col_df)):
            if df.columns[i]==col_df['컬럼영문명'][j]:
                count+=1
                print(df.columns[i],col_df['컬럼한글명'][j])
                df.rename(columns={df.columns[i]:col_df['컬럼한글명'][j]},inplace=True)
    print('\n>> 컬럼명 한글화 정상완료')
    if count==len(df.columns):
        print('\n>>',count,'개의 컬럼이 일치')
    else:
        print('\n!!컬럼정의서 상의 컬럼과 실제 컬럼이 일치하지 않음!!')
except:
    print('예외발생')
```

    SEQ 일련
    CNTNTS_ID 콘텐츠 ID
    CH_TY 채널 타입
    CH_NM 채널명
    SJ 제목
    POST_DE 게시일자
    CNTNTS_DPI 콘텐츠 DPI
    LIKE_CNT 좋아요수
    ANSWER_CNT 댓글수
    CNTNTS_URL 콘텐츠 URL
    CTGRY_1_NM 분류체계1
    CTGRY_2_NM 분류체계2
    
    >> 컬럼명 한글화 정상완료
    
    >> 12 개의 컬럼이 일치
    

### 3차: PK 조건 체크


```python
#PK
pk=[]
for i in df.columns:
    if len(df[i].unique()) == len(df):
        pk.append(i)
```


```python
if len(col_df[col_df['PK여부']=='Y']) > 0:
    col_pk=list(col_df['컬럼한글명'][col_df['PK여부']=='Y'])
    print('\n컬럼정의서 상의 PK:',col_pk)
else: print('컬럼정의서 상의 PK: 없음')
print('> PK로 가능한 컬럼:',pk)

# PK여부는 유일성과 최소성을 함께 고려하나, 경우에 따라 두 개 이상이 결합되어야 할 수 있음
# ex. '응답자ID' 하나로 PK가 될 수 있지만 동일한 응답자가 주기적으로 다른 시기에 응답했을 경우 '응답자ID+조사년월'이 PK로 선정
```

    
    컬럼정의서 상의 PK: ['일련']
    > PK로 가능한 컬럼: ['일련', '콘텐츠 ID', '콘텐츠 URL']
    

### 4차: NULL값 확인


```python
count=0
print('<NOT NULL "N" 으로 수정이 필요한 컬럼>')
for i in range(len(df.columns)):
    for j in range(len(col_df)):
        if df.columns[i]==col_df['컬럼한글명'][j]:
            if (df.iloc[:,i].isnull().sum() > 0) & (col_df['NOT NULL여부'][j] == 'Y'):
                count+=1
                print(df.columns[i], ':',df.iloc[:,i].isnull().sum(),'개')
if count==0:
    print('없음')
            
        
count=0
print('\n\n\n<NOT NULL "Y" 으로 수정이 필요한 컬럼>')
for i in range(len(df.columns)):
    for j in range(len(col_df)):
        if df.columns[i]==col_df['컬럼한글명'][j]:
            if (df.iloc[:,i].isnull().sum() == 0) & (col_df['NOT NULL여부'][j] == 'N'):
                count+=1
                print(df.columns[i], '\t:',df.iloc[:,i].isnull().sum(),'개')
if count==0:
    print('없음')
```

    <NOT NULL "N" 으로 수정이 필요한 컬럼>
    없음
    
    
    
    <NOT NULL "Y" 으로 수정이 필요한 컬럼>
    일련 	: 0 개
    콘텐츠 ID 	: 0 개
    채널 타입 	: 0 개
    채널명 	: 0 개
    제목 	: 0 개
    게시일자 	: 0 개
    콘텐츠 DPI 	: 0 개
    좋아요수 	: 0 개
    댓글수 	: 0 개
    콘텐츠 URL 	: 0 개
    분류체계1 	: 0 개
    분류체계2 	: 0 개
    

### 5차: 데이터 타입 확인

(실제 타입) ---> (컬럼정의서상 타입)


```python
print('<데이터 타입 표기 확인>\n')
for i in range(len(df.columns)):
    for j in range(len(col_df)):
        if df.columns[i]==col_df['컬럼한글명'][j]:
            print(col_df['컬럼한글명'][i],'\t',df[df.columns[i]].dtypes,'--->',col_df['데이터타입'][i])
```

    <데이터 타입 표기 확인>
    
    일련 	 int64 ---> BIGINT
    콘텐츠 ID 	 object ---> TEXT
    채널 타입 	 object ---> TEXT
    채널명 	 object ---> TEXT
    제목 	 object ---> TEXT
    게시일자 	 object ---> DATE
    콘텐츠 DPI 	 float64 ---> DOUBLE PRECISION
    좋아요수 	 int64 ---> INT
    댓글수 	 int64 ---> INT
    콘텐츠 URL 	 object ---> TEXT
    분류체계1 	 object ---> TEXT
    분류체계2 	 object ---> TEXT
    

### 6차: 데이터 길이 확인

(실제 길이) ---> (컬럼정의서상 길이)


```python
df_len=[]
len_error=[]
count=0

print('<데이터 길이 확인>')
for i in range(len(df.columns)):
    for j in range(len(col_df)):
        if df.columns[i]==col_df['컬럼한글명'][j]:
            max_check=[]
            
            for x in range(len(df)):
                max_check.append(len(str(df.iloc[x,i])))
                m=max(max_check)
            
            df_len.append(m)
            print(col_df['컬럼한글명'][j],'\t',df_len[i],'--->',col_df['길이'][j])

            if ',' in str(col_df['길이'][j]):
                temp=col_df['길이'][j].split(',')
                clen=int(temp[0])
            else:
                clen=int(col_df['길이'][j])
            
            if df_len[i] > clen:
                count+=1
                len_error.append(col_df['컬럼한글명'][j])


print('\n<정의된 길이를 초과하는 컬럼>')
if count > 0:
    print(len_error)
else:
    print('없음')
```

    <데이터 길이 확인>
    일련 	 7 ---> 8
    콘텐츠 ID 	 32 ---> 100
    채널 타입 	 4 ---> 100
    채널명 	 39 ---> 100
    제목 	 98 ---> 1000
    게시일자 	 10 ---> 4
    콘텐츠 DPI 	 4 ---> 8
    좋아요수 	 3 ---> 4
    댓글수 	 1 ---> 4
    콘텐츠 URL 	 79 ---> 100
    분류체계1 	 2 ---> 100
    분류체계2 	 2 ---> 100
    
    <정의된 길이를 초과하는 컬럼>
    ['게시일자']
    


```python
df['수집일자']
```


    ---------------------------------------------------------------------------

    KeyError                                  Traceback (most recent call last)

    ~\anaconda3\lib\site-packages\pandas\core\indexes\base.py in get_loc(self, key, method, tolerance)
       2894             try:
    -> 2895                 return self._engine.get_loc(casted_key)
       2896             except KeyError as err:
    

    pandas\_libs\index.pyx in pandas._libs.index.IndexEngine.get_loc()
    

    pandas\_libs\index.pyx in pandas._libs.index.IndexEngine.get_loc()
    

    pandas\_libs\hashtable_class_helper.pxi in pandas._libs.hashtable.PyObjectHashTable.get_item()
    

    pandas\_libs\hashtable_class_helper.pxi in pandas._libs.hashtable.PyObjectHashTable.get_item()
    

    KeyError: '수집일자'

    
    The above exception was the direct cause of the following exception:
    

    KeyError                                  Traceback (most recent call last)

    <ipython-input-15-6b5df2709598> in <module>
    ----> 1 df['수집일자']
    

    ~\anaconda3\lib\site-packages\pandas\core\frame.py in __getitem__(self, key)
       2900             if self.columns.nlevels > 1:
       2901                 return self._getitem_multilevel(key)
    -> 2902             indexer = self.columns.get_loc(key)
       2903             if is_integer(indexer):
       2904                 indexer = [indexer]
    

    ~\anaconda3\lib\site-packages\pandas\core\indexes\base.py in get_loc(self, key, method, tolerance)
       2895                 return self._engine.get_loc(casted_key)
       2896             except KeyError as err:
    -> 2897                 raise KeyError(key) from err
       2898 
       2899         if tolerance is not None:
    

    KeyError: '수집일자'


# 3. 데이터 무결성

### 1차: 데이터 타입 확인

특성 상 데이터 타입이 올바르지 않은 컬럼 확인하기
>(ex) text가 들어가야하는데 수치가 들어가 있는 경우


```python
df.info(null_counts=False)
```

### 2차: NULL값 확인

특성 상 NULL이 되면 안되는 컬럼 확인하기
>(ex) 시군구명 등 null이 될 수 없는 컬럼 (세종특별자치시..?)


```python
print('<NULL값 개수>\n')
for i in range(len(df.columns)):
    print(df.columns[i],':',df.iloc[:,i].isnull().sum(),'개')

print('')
print('데이터 전체 길이 :',len(df))
```


```python
col_df
```


```python

```
