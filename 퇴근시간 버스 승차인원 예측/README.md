# 퇴근시간 버스 승차인원 예측

목표 : 퇴근시간 버스 승차인원을 예측하는 모델을 만들어 교통 체증 문제를 해결하는 것

평가척도 : RMSE

주의할 점 : 오전시간에 해당하는 데이터만 활용해서 퇴근 시간의 버스 승차 인원을 예측해야한다. 정해진 기간의 데이터만 활용해서 그 이후의 퇴근시간 승차인원을 예측해야한다.



- train.csv 변수

| 변수명          | 상세 설명                   |
| --------------- | --------------------------- |
| id              | 해당 데이터에서의 고유한 ID |
| date            | 날짜                        |
| bus_route_id    | 노선 ID                     |
| in_out          | 시내벗, 시외버스 구분       |
| station_code    | 해당 승하차 정류소의 ID     |
| station_name    | 해당 승하차 정류소의 이름   |
| latitude        | 해당 버스 정류장의 위도     |
| longitude       | 해당 버스 정류장의 경도     |
| [X]~[Y]_ride    | 시간대별 승차 인원수        |
| [X]~[Y]_takeoff | 시간대별 하차 인원수        |



- bus_bts.csv 변수

| 변수명              | 상세 설명                                                    |
| ------------------- | ------------------------------------------------------------ |
| user_card_id        | 해당 승객의 버스 카드 ID                                     |
| bus_route_id        | 노선 ID                                                      |
| vhc_id              | 차량 ID                                                      |
| geton_date          | 해당 승객이 탑승한 날짜                                      |
| geton_time          | 해당 승객이 탑승한 시간                                      |
| geton_station_code  | 승차 정류소의 ID                                             |
| geton_station_name  | 승차 정류소의 이름                                           |
| getoff_date         | 해당 승객이 하차한 날짜 (하차 태그 없는 경우는 NaN)          |
| getoff_time         | 해당 승객이 하차한 시간 (하차 태그 없는 경우는 NaN)          |
| getoff_station_code | 하차 정류소의 ID (하차 태그 없는 경우는 NaN)                 |
| getoff_station_name | 하차 정류소의 이름 (하차 태그 없는 경우는 NaN)               |
| user_category       | 승객 구분 (01-일반, 02-어린이, 04-청소년, 06-경로, 27-장애 일반, 28-장애 동반, 29-유공 일반, 30- 유공 동반) |
| user_count          | 해당 버스 카드로 계산한 인원수                               |



- jeju_financial_life_data.csv 변수

| 변수명          | 상세 설명                                            |
| --------------- | ---------------------------------------------------- |
| x_axis          | 경도                                                 |
| y_axis          | 위도                                                 |
| job_majorc      | 직업군별 비율 - 대기업 종사자의 비율                 |
| job_smallc      | 직업군별 비율 - 중소기업 종사자의 비율               |
| job_public      | 직업군별 비율 - 공무원 종사자의 비율                 |
| job_profession  | 직업군별 비율 - 전문직 종사자의 비율                 |
| job_self        | 직업군별 비율 - 자영업 종사자의 비율                 |
| avg_income      | 평균연소득 - 고객군별 평균 KCB 결정연소득의 평균값   |
| med_income      | 중위연소득 - 고객군별 KCB 결정연소득의 중앙값        |
| avg_spend       | 평균 소비액 - 고객군별 3개월 평균 KCB 총카드이용금액 |
| vehicle_own_rat | 중대형 차량소유비율 - 고객군별 중대형 차량 소유비율  |

