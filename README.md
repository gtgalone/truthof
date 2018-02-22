<a id="-"></a>
# 랜드북 API

* <a href="#details">필지 및 건축물 정보 검색</a>
* <a href="#deals_households">전유부 매매사례 검색</a>
* <a href="#deals_buildings">건축물 매매사례 검색</a>
* <a href="#populations">시도, 시군구, 읍면동 인구 검색</a>
---
<a id="details"></a>
### 필지 및 건축물 정보 검색


#### HTTP 요청
`GET https://www.landbook.cc/details`

#### 매개변수
<table>
	<thead>
    <tr>
      <th>매개변수 이름</th>
      <th>기본 값</th>
      <th>설명</th>
      <th>형식</th>
    </tr>
  </thead>
	<tbody>
    <tr>
      <td>address</td>
      <td>(필수입력)</td>
      <td>주소</td>
      <td>서울특별시 성동구 성수동2가 269-204번지</td>
    </tr>
  </tbody>
</table>

#### 응답
```
[
  {
    "land": {
      "address": "서울특별시 성동구 성수동2가 269-204번지",
      "area_lot": 1914,
      "ratio_floorarea": 129,
      "jimok": "장",
      "landuse": "미지정",
      "regulation": "대공방어협조구역|도시지역"
    },
    "buildings": [
      {
        "id": 79163,
        "pnu": "1120011500102690204",
        "building_pk": "11200-20321",
        "type_building": "일반",
        "name_building": "1동",
        "dong_building": "1동",
        "use_main": "공장",
        "use_detail": "일반공장",
        "area_building": 658.3,
        "area_grossfloor": 1974.9,
        "household": "0",
        "family": "0",
        "floor": 3,
        "floor_under": 1,
        "date_permit": null,
        "date_construction": null,
        "date_approval": "1981-07-31",
        "created_at": "2018-01-10T14:56:38.000+09:00",
        "updated_at": "2018-01-10T14:56:38.000+09:00"
      },
      {
        "id": 79162,
        "pnu": "1120011500102690204",
        "building_pk": "11200-20322",
        "type_building": "일반",
        "name_building": "2동",
        "dong_building": "2동",
        "use_main": "공장",
        "use_detail": "일반공장",
        "area_building": 470.04,
        "area_grossfloor": 940.08,
        "household": "0",
        "family": "0",
        "floor": 2,
        "floor_under": 0,
        "date_permit": "2007-05-31",
        "date_construction": "2007-06-29",
        "date_approval": "2007-10-16",
        "created_at": "2018-01-10T14:56:38.000+09:00",
        "updated_at": "2018-01-10T14:56:38.000+09:00"
      }
    ]
  }
]
```
<a href="#-">맨 위로</a>

---
<a id="deals_households"></a>
### 전유부 매매사례 검색

#### HTTP 요청
`GET https://www.landbook.cc/deals/households`

#### 매개변수
<table>
	<thead>
    <tr>
      <th>매개변수 이름</th>
      <th>기본 값</th>
      <th>설명</th>
      <th>형식</th>
    </tr>
  </thead>
	<tbody>
    <tr>
      <td>address</td>
      <td>(필수입력)</td>
      <td>주소</td>
      <td>서울특별시 송파구 석촌동 120-1번지</td>
    </tr>
    <tr>
      <td>start_date_contract</td>
      <td>2008-01-01</td>
      <td>거래기간 시작일</td>
      <td>2017-01-01</td>
    </tr>
    <tr>
      <td>end_date_contract</td>
      <td>2017-01-01</td>
      <td>거래기간 종료일</td>
      <td>2017-12-31</td>
    </tr>
    <tr>
      <td>start_year_approval</td>
      <td>1960-01-01</td>
      <td>건축년도 시작일</td>
      <td>2017-01-01</td>
    </tr>
    <tr>
      <td>end_year_approval</td>
      <td>2017-01-01</td>
      <td>건축년도 종료일</td>
      <td>2017-12-31</td>
    </tr>
    <tr>
      <td>min_area_exclusive</td>
      <td>0</td>
      <td>최소 전용면적 범위</td>
      <td>12.99</td>
    </tr>
    <tr>
      <td>max_area_exclusive</td>
      <td>1000000</td>
      <td>최대 전용면적 범위</td>
      <td>359.99</td>
    </tr>
  </tbody>
</table>
<i>area_exclusive의 경우 min 또는 max 값만 입력할 수 없으며, min 값 입력 시 max 값은 필수입력이며, max 값 입력 시 min 값은 필수입력입니다.</i>

#### 응답
```
[
  {
    "id": 56147,
    "pnu": "1171010500102100023",
    "date_contract": "2016-10-01",
    "year_approval": "2003-01-01",
    "price": 6000000000,
    "area_grossfloor": 1038.22,
    "area_lot": 357.4,
    "address": "서울특별시 송파구 석촌동 210-23번지"
  }
]
```
<a href="#-">맨 위로</a>

---
<a id="deals_buildings"></a>
### 건축물 매매사례 검색

#### HTTP 요청
`GET https://www.landbook.cc/deals/buildings`

#### 매개변수
<table>
	<thead>
    <tr>
      <th>매개변수 이름</th>
      <th>기본 값</th>
      <th>설명</th>
      <th>형식</th>
    </tr>
  </thead>
	<tbody>
    <tr>
      <td>address</td>
      <td>(필수입력)</td>
      <td>주소</td>
      <td>서울특별시 강남구 논현동 120-3번지</td>
    </tr>
    <tr>
      <td>start_date_contract</td>
      <td>2008-01-01</td>
      <td>거래기간 시작일</td>
      <td>2017-01-01</td>
    </tr>
    <tr>
      <td>end_date_contract</td>
      <td>2017-01-01</td>
      <td>거래기간 종료일</td>
      <td>2017-12-31</td>
    </tr>
    <tr>
      <td>start_year_approval</td>
      <td>1960-01-01</td>
      <td>건축년도 시작일</td>
      <td>2017-01-01</td>
    </tr>
    <tr>
      <td>end_year_approval</td>
      <td>2017-01-01</td>
      <td>건축년도 종료일</td>
      <td>2017-12-31</td>
    </tr>
    <tr>
      <td>min_area_grossfloor</td>
      <td>0</td>
      <td>최소 필지면적 범위</td>
      <td>12.99</td>
    </tr>
    <tr>
      <td>max_area_grossfloor</td>
      <td>1000000</td>
      <td>최대 필지면적 범위</td>
      <td>359.99</td>
    </tr>
    <tr>
      <td>min_area_lot</td>
      <td>0</td>
      <td>최소 연면적 범위</td>
      <td>12.99</td>
    </tr>
    <tr>
      <td>max_area_lot</td>
      <td>1000000</td>
      <td>최대 연면적 범위</td>
      <td>359.99</td>
    </tr>
  </tbody>
</table>
<i>area_lot, area_grossfloor의 경우 min 또는 max 값만 입력할 수 없으며, min 값 입력 시 max 값은 필수입력이며, max 값 입력 시 min 값은 필수입력입니다.</i>

#### 응답
```
[
  {
    "id": 266726,
    "pnu": "1168010800102050008",
    "date_contract": "2017-08-01",
    "year_approval": "2003-01-01",
    "price": 1800000000,
    "floor": "-",
    "area_exclusive": 453.44,
    "address": "서울특별시 강남구 논현동 205-8번지"
  },
]
```
<a href="#-">맨 위로</a>

---
<a id="populations"></a>
### 시도, 시군구, 읍면동 인구 검색

#### HTTP 요청
`GET https://www.landbook.cc/populations`

#### 매개변수
<table>
	<thead>
    <tr>
      <th>매개변수 이름</th>
      <th>기본 값</th>
      <th>설명</th>
      <th>형식</th>
    </tr>
  </thead>
	<tbody>
    <tr>
      <td>address</td>
      <td>(필수입력)</td>
      <td>주소</td>
      <td>서울특별시/</br>서울특별시 광진구/</br>서울특별시 광진구 중곡1동</td>
    </tr>
    <tr>
      <td>gender</td>
      <td>total,male,female</td>
      <td>성별 또는 총인구</td>
      <td>total/</br>total,male/</br>male,female</td>
    </tr>
    <tr>
      <td>age</td>
      <td>0, 5, 10, 15, 20, 25, 30, 35, 40, 45, 50, 55,</br> 60, 65, 70, 75, 80, 85, 90, 95, 100, 105</td>
      <td>5세 단위로 0세부터 105세 까지의 나이</td>
      <td>0/</br>0, 5</td>
    </tr>
    <tr>
      <td>min_year</td>
      <td>2012</td>
      <td>시작년도</td>
      <td>2012</td>
    </tr>
    <tr>
      <td>max_year</td>
      <td>2018</td>
      <td>종료년도</td>
      <td>2018</td>
    </tr>
  </tbody>
</table><i>year의 경우 min 또는 max 값만 입력할 수 없으며, min 값 입력 시 max 값은 필수입력이며, max 값 입력 시 min 값은 필수입력입니다.</i>

#### 응답
```
[
    {
        "id": 33734,
        "code": "1121574000",
        "age": 0,
        "gender": "male",
        "year": "2012-01-01",
        "pop": 8319,
        "pop_chg": -0.6
    },
    {
        "id": 33755,
        "code": "1121574000",
        "age": 5,
        "gender": "male",
        "year": "2012-01-01",
        "pop": 327,
        "pop_chg": 10.1
    },
    {
        "id": 34154,
        "code": "1121574000",
        "age": 100,
        "gender": "male",
        "year": "2012-01-01",
        "pop": 1,
        "pop_chg": -66.7
    }
]
```
<a href="#-">맨 위로</a>

---
