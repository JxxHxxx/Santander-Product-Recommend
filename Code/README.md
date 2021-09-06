# 대규모 데이터 처리를 진행하겠습니다.

검색 결과 대규모 데이터를 다룰 때 사용할 수 있는 방법은 아래와 같다.

1. 고성능 컴퓨팅 파워 CPU, RAM 등
2. 아마존의 AWS, 마이크로소프트의 AZURE 등을 사용해 가상환경 구축
3. 코랩 등 이용
4. DataBase 이용
- 학습을 통해 배운 내용 DataBase는 Csv 에 비해 메모리를 굉장히 적게 사용한다고 합니다. (확인해야함)  

나는 내가 가진 환경속에서 전처리를 해보겠다. 참고로 컴퓨터 스펙은 CPU i5 10세대 / RAM 16G
# PreProcessing Strategy

----------------------------------- 01_Preprocessing_Memory_Saving.ipynb ---------------------------------------
1. fecha_dato type change datetime (D)
2. ncodpers : 특징 id-data 모델링 전까진 드랍 (D)
3. ind_empleado : 고객 분류 A active, B ex employed F filial N not employee P passive  고대로 이용 (D)
4. pais_residencia : 메모리 효율을 위해 숫자로 변경 (D)
5. sexo : V, H 로 구분 pass (D)
6. age : int8 pass (D)
7. fecha_alta : type change datetime (D)
8. ind_nuevo : 신규 고객 여부 (첫 가입 6개월까지 6개월로 판단) 기존 고객 0 신규 고객 1 pass (D)


----------------------------------- 02_Preprocessing_Memory_Saving.ipynb ---------------------------------------

9. antiguedad : 고객의 연령서열? age와 유사 Drop 하겠다. 
10. indrel :
11. ult_fec_cli_1t : 충성 고객으로 본 마지막 날
12. 
