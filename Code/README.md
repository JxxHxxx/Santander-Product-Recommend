<br>
<br>

# 대규모 데이터 처리를 진행하겠습니다.

검색 결과 대규모 데이터를 다룰 때는 아래와 같은 방법을 활용할 수 있습니다.

1. 고성능 컴퓨팅 파워 CPU, RAM 등
2. 아마존의 AWS, 마이크로소프트의 AZURE 등을 사용해 가상환경 구축
3. 코랩 등 이용
4. DataBase 이용
- DataBase는 csv 에 비해 메모리를 굉장히 적게 사용한다고 들었습니다. (확인해야함)  

제가 가진 환경속에서 전처리를 해보겠습니다.  컴퓨터 스펙은 CPU i5 10세대 / RAM 16G 입니다.
<br>

# PreProcessing Strategy

----------------------------------- 01_Preprocessing_Memory_Saving.ipynb ---------------------------------------
1. fecha_dato type change datetime (D)
2. ncodpers : 고객의 id 값입니다. 모델링 전까진 드랍 (D)
3. ind_empleado : 고객 분류에 대한 정보입니다. A active, B ex employed F filial N not employee P passive  고대로 이용 (D)
4. pais_residencia : 거주 지역입니다. 메모리 효율을 위해 숫자로 변경 (D)
5. sexo : 성별입니다. V, H 로 구분 pass (D)
6. age : 나이입니다. int8 pass (D)
7. fecha_alta : type change datetime (D)
8. ind_nuevo : 신규 고객 여부 (첫 가입 6개월까지 6개월로 판단) 기존 고객 0 신규 고객 1 pass (D)


----------------------------------- 02_Preprocessing_Memory_Saving.ipynb ---------------------------------------

9. antiguedad : 고객에 대한 royalty 같은 개념, 기간에 따른 로얄티 부여  

----------------------------------- 03_Preprocessing_Memory_Saving.ipynb ---------------------------------------

10. indrel : 고객 유형에 대한 정보, 직접 보고 판단
11. ult_fec_cli_1t : 충성 고객으로 본 마지막 날

----------------------------------- 04_Preprocessing_Memory_Saving.ipynb ---------------------------------------

12. inderl_1mes : 고객 유형에 대한 정보, 직접 보고 판단
13. tiprel_1mes : 고객 유형에 대한 정보, 직접 보고 판단
14. indesi : 스페인 국민 S(Yes)/N(No)
15. indext : 외국인 S(Yes)/N(No)   indext는 열 13의 indesi의 부정입니다. Drop 하겠습니다.
16. conyuemp : 고객이 은행 직원의 배우자인가
17. canal_entrade : 
18. indfall : 0(dead), 1(live) 사망한 고객은 은행의 상품을 구매할 수 없으니 일단은 indfall = 0인 Row를 Drop 하겠습니다. 하지만 훈련에는 필요할지 모르니 고려해두고 있겠습니다.
19. tipodom : 주소 타입
20. cod_prov : 지방 코드 
21. nomprov : 지방 이름
22. ind_actividad_cliente_Activity : 고객 활성 여부 1(active), 0(inactive) 
23. renta : 가구원 소득
24. segmento : 01(VIP), 02(Individuals), 03(College Graduated) Memory 절약을 위해 value를 01 >1, 02 > 2, 03 > 3 으로 변경하겠습니다.

# 정리

거주지에 대한 정보 4, 18, 19, 20
