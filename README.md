# BDA
한국어 소개 글이 아래에 나와있습니다.

The Korean introduction is above, and the English introduction follows below.

# 프로젝트 소개
### 프로젝트 제목 
도서관의 규모와 지역 수준의 상관관계

### 프로젝트 요약 
 최근 도시의 역할이 중요해지면서 도시를 구성하는 다양한 요소들에 대한 중요성도 높아지고 있다. 특히 공공 도서관과 같은 문화시설은 도시 생활의 질을 높이는 데 중요한 역할을 한다. 이러한 맥락에서 도서관의 경제적 요인 들이 도서관 이용에 어떤 영향을 미치는지, 그리고 공공 도서관 공급이 우리사회에서 어떤 긍정정 변화를 가져오는지에 대한 연구들이 주목받고 있다. 
 특히 도서관은 단순히 책을 빌려주는 곳을 넘어서, 모든 연령층에게 적절한 쉼터를 제공하고, 다양한 문화 프로그램을 통해 사회적 화합을 촉진하는 중요한 공간이다. 이러한 배경을 바탕으로 도서관의 규모가 그 지역에 어떠한 영향을 미치는가에 대한 프로젝트를 진행하였다.

### 사용한 데이터
사용한 데이터는 '공공 데이터 포탈'(https://www.data.go.kr/) 과 '서울 열린데이터광장'(https://data.seoul.go.kr/) 에서 데이터를 찾아서 사용하였다.

1. 서울특별시_공공도서관(구별)통계
   서울시 공공 도서관 통계자료이다. 서울시 자치구별 공공 도서관 수, 좌석수, 자료수, 도서관 방문자수, 자료실 이용자수, 연간대출책수, 직원수 및 예산 데이터를 활용하였다. 2018년부터 2022년까지 5개년 자료를 사용하여 총 25개구에 대한 데이터를 분석하였다.
3. 서울특별시_부동산 실거래가 정보
   서울시 부동산 실거래가 정보자료이다. 자치구별 물건 금액 데이터를 활용하였다. 대용량의 데이터이기 때문에 년도별로 각 구별 20개의 데이터를 랜덤으로 뽑아 사용하였다. 각 구별 100개의 데이터를 뽑아 총 2500개의 데이터를 사용하였다.
5. 서울시 사설학원 통계
   서울시 내 사설학원 및 독서실 현황자료이다. 2018년부터 2022년까지 5개년의 자료를 활용하였다. 각 구별 사설 학원 및 독서실의 수가 나와있다.

# 프로젝트 진행
### 데이터 전처리
 첫 번째 데이터는 자치구별 도서관 수, 좌석 수, 자료 수, 도서관 방문자 수, 자료실 이용자 수, 연간 대출 책 수, 직원 수, 예산 등의 도서관 운영 데이터를 포함하였다. 두 번째 데이터는 자치구별 부동산 실거래가 정보를 정리하여 지역별 부동산 시장 동향을 파악하고, 세 번째 데이터는 자치구별 사설학원 및 독서실 수를 정리하여 교육 및 학습 관련 인프라 현황을 분석하였다.
 
![image](https://github.com/user-attachments/assets/c7a70e5d-5437-4d7a-b442-39d9c154f92e)'

![image](https://github.com/user-attachments/assets/b84a52d3-575a-4f3e-9555-75f30b80e18b)


### 전처리 완료 데이터
데이터 분석을 위해 필요한 라이브러리와 파일을 전부 불러온다.

import pandas as pd
import matplotlib.pyplot as plt
import numpy as np

#각 구별로 2018년부터 2022년까지의 도서관 수

library_count=pd.read_csv('library_count.csv')

#각 구별로 2018년부터 2022년까지의 도서관 이용자 수

library_people=pd.read_csv('library_people.csv')

#각 구별로 2018년부터 2022년까지의 도서관 자료 수

library_books=pd.read_csv('library_books.csv')

#각 구별로 2018년부터 2022년까지의 도서관 좌석 수

library_seat=pd.read_csv('library_seat.csv')

#각 구별로 2018년부터 2022년까지의 학원 및 독서실 수

academy=pd.read_csv('academy.csv')

#각 구별로 2018년부터 2022년까지의 부동산 거래 정보

home=pd.read_csv('home.csv')

### 데이터 분석 방법

상관관계 분석을 통해 각 자료들어 서로 어떠한 상관관계가 있는지 알아보았다

#도서관 수 & 도서관 이용자 수

#도서관 수 & 도서관 좌석수

#도서관 수 & 부동산 거래가

#도서관 자료 수 & 도서관 이용자 수

#도서관 자료 수 & 근처 학원 수 

#도서관 좌석수 & 도서관 이용자 수

#도서관 자료수 & 근처 학원 수

#도서관 이용자 수 & 도서관 좌석 수 

#도서관 이용자 수 & 근처 학원 수 

#도서관 이용자 수 & 부동산 거래가


### 데이터 분석 결과
![image](https://github.com/user-attachments/assets/df4cd2d5-67bc-4457-babb-6f6115c29a42)

상관관계 분석 결과, 도서관 수와 도서관 이용자 수, 도서관의 좌석 수와 이용자 수는 비례하고, 도서관 수와 도서관 이용자 수는 부동산 거래가와 반비례한다는 것을 알 수 있었다.

# 결과 분석
 프로젝트를 진행하면서 도서관의 규모가 큰 지역의 경제적 수준은 높을 것이라고 생각하였다. 지역의 경제적 수준이 높은만큼 도서관 및 다양한 문화시설을 이용하는 이용자 수가 비례할 것이라고 생각했기 때문이다. 하지만 도서관의 규모와 지역의 경제적 수준은 관련이 없었다.
 
![image](https://github.com/user-attachments/assets/3875433e-707a-469e-a2c2-df6c1955bbe9)

추가적인 논문을 찾아보았다. 경제요인이 도서관 이용에 어떤 영향을 미치는지 알 수 있었다. "소비자들은 소득이 증가할수록 대출보다 책을 구입하는 선택을 더 선호한다고 할 수 있다." 따라서 책을 구입함으로서 도서관의 이용자 수를 늘리는 정책은 바르지 못할 수 있다는 것이 이 프로젝트의 결론이다.

# Reference
[1] 전계형, & 권선영. (2018). 경제요인이 도서관 이용에 미치는 영향에 관한 연구. 한국융합학회지, 9(11), 299-306. https://doi.org/10.15207/JKCS.2018.9.11.299

***

# Project Introduction
### Project Title
Correlation between Library Size and Regional Economic Level

### Project Summary
As cities play an increasingly important role, the significance of various elements that constitute a city has also grown. Public cultural facilities, such as libraries, play a crucial role in enhancing the quality of urban life. In this context, studies focusing on how economic factors affect library usage and how the supply of public libraries brings positive social changes have been gaining attention. Libraries are not just places where books are lent out but serve as important spaces that provide shelters for people of all ages and promote social cohesion through various cultural programs. Based on this background, the project examines the impact of library size on the surrounding area.

### Data Used
The data used in this project was sourced from the 'Public Data Portal' (https://www.data.go.kr/) and 'Seoul Open Data Plaza' (https://data.seoul.go.kr/).

1. Seoul Public Library (District-wise) Statistics
   This data includes statistics on public libraries in Seoul, such as the number of libraries, seats, books, visitors, reading room users, annual book loans, staff, and budget by district. Data from 2018 to 2022, covering 25 districts, was analyzed.
2. Seoul Real Estate Transaction Data
   This dataset provides real estate transaction prices by district in Seoul. Due to the large volume of data, 20 randomly selected transactions per district for each year were used, totaling 2,500 data points.
3. Seoul Private Academy Statistics
   This dataset includes information on the number of private academies and study rooms in Seoul from 2018 to 2022, by district.
   
# Project Progress
### Data Preprocessing
The first dataset includes data on the number of libraries, seats, books, library visitors, reading room users, annual book loans, staff, and budgets by district. The second dataset focuses on real estate transaction prices by district, and the third dataset includes the number of private academies and study rooms, which allows for the analysis of educational infrastructure.

![image](https://github.com/user-attachments/assets/c7a70e5d-5437-4d7a-b442-39d9c154f92e)

![image](https://github.com/user-attachments/assets/b84a52d3-575a-4f3e-9555-75f30b80e18b)

### Preprocessed Data
The necessary libraries and files for data analysis were loaded.

import pandas as pd
import matplotlib.pyplot as plt
import numpy as np

#Data for the number of libraries by district from 2018 to 2022

library_count=pd.read_csv('library_count.csv')

#Data for library visitors by district from 2018 to 2022

library_people=pd.read_csv('library_people.csv')

#Data for library book collection by district from 2018 to 2022

library_books=pd.read_csv('library_books.csv')

#Data for library seats by district from 2018 to 2022

library_seat=pd.read_csv('library_seat.csv')

#Data for private academies and study rooms by district from 2018 to 2022

academy=pd.read_csv('academy.csv')

#Real estate transaction data by district

home=pd.read_csv('home.csv')


### Data Analysis Method
We conducted a correlation analysis to examine the relationships between various data points.

#Number of libraries & Library visitors

#Number of libraries & Library seats

#Number of libraries & Real estate transaction prices

#Library books & Library visitors

#Library books & Nearby academy numbers

#Library seats & Library visitors

#Library books & Nearby academy numbers

#Library visitors & Library seats

#Library visitors & Nearby academy numbers

#Library visitors & Real estate transaction prices


### Data Analysis Results
![image](https://github.com/user-attachments/assets/2a98201a-8e5c-480b-b3e7-62311bebb385)

The correlation analysis revealed that the number of libraries and library visitors, as well as library seats and visitors, are positively correlated. However, the number of libraries and library visitors is negatively correlated with real estate transaction prices.

# Result Analysis
During the project, I assumed that areas with larger libraries would have higher economic levels, as a higher economic level would likely lead to more people using libraries and cultural facilities. However, the analysis showed that there was no correlation between library size and the area's economic level.

![image](https://github.com/user-attachments/assets/3875433e-707a-469e-a2c2-df6c1955bbe9)

Further research into related literature suggested that economic factors influence library use in specific ways. "As consumers' incomes increase, they tend to prefer purchasing books rather than borrowing them." Therefore, policies aimed at increasing library visitor numbers by promoting book purchases may not be effective. This project concludes that such policies might not be ideal.

# Reference
[1] Jeon, G., & Kwon, S. (2018). A study on the influence of economic factors on library use. Journal of the Korea Convergence Society, 9(11), 299-306. https://doi.org/10.15207/JKCS.2018.9.11.299
