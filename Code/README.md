# PreProcessing Strategy

1. fecha_dato type change datetime (D)
2. ncodpers : 특징 id-data 모델링 전까진 드랍 (D)
3. ind_empleado : 고객 분류 A active, B ex employed F filial N not employee P passive  고대로 이용 (D)
4. pais_residencia : 메모리 효율을 위해 숫자로 변경 (D)
5. sexo : V, H 로 구분 pass (D)
6. age : int8 pass (D)
7. fecha_alta : type change datetime (D)
8. ind_nuevo : 신규 고객 여부 (첫 가입 6개월까지 6개월로 판단) 기존 고객 0 신규 고객 1 pass (D)
9. antiguedad : 고객의 연령서열? age와 유사 Drop 하겠다. 
10. indrel :
11. ult_fec_cli_1t : 충성 고객으로 본 마지막 날
12. 
