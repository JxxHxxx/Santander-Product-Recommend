
![](SantanderLogo.png)
<br>
<br>
#

# Santander Product Recommend 
스페인 은행 Santander 고객들이 어떤 금융 상품을 구매할 지 분류하는 데이터 분석 과제입니다.<br><br>

# Data
[Kaggle - Santander Product Recommendation](https://www.kaggle.com/c/santander-product-recommendation/data) <br><br>

train 셋의 경우 용량이 굉장히 큰 편입니다. parquet 확장자로 저장해도 100mb가 넘어 일반적인 방법으로는 레포지터리에 올릴 수가 없습니다. <br>
git-lfs를 이용하면 올릴 수 있다는 정보를 얻었습니다. 추후 올리도록 하겠습니다.

# Data Description

해당 Competition 에서는 Santander 은행 고객들의 18개월 분량의 데이터를 사용하게 됩니다. 참여하시는 여러분은 제공 받은 데이터를 통해 고객이 구매할 신제품을 어떤것일지 예측하는 미션을 수행하시게 됩니다
<br>
<br>
trainset의 Feature는 크게 2 가지 섹터로 분류할 수 있습니다. 첫 째, 고객에 대한 정보로 Column 0 부터 23 이 이에 해당합니다. 예를 들면 고객의 거주 지역(pais_residencia), 신규 고객(ind_nuevo), 가구의 소득(Renta) 등이 담겨져 있습니다.
<br>
<br>
둘 째, 고객의 상품 보유에 대한 유무 정보로 Column 24 부터가 이에 해당합니다. 예를 들면 급여 계좌(ind_cno_fin_ult1), 펀드(ind_fond_fin_ult1), 장기 예금(ind_dela_fin_ult1), 부동산 담보 대출(ind_hip_fin_unt1) 등이 담겨져 있습니다.





# Data Field

|Column Name|	Description|
|---|---|
|fecha_dato |The table is partitioned for this column|
ncodpers	|Customer code
ind_empleado	|Employee index: A active, B ex employed, F filial, N not employee, P pasive
pais_residencia	|Customer's Country residence
sexo|	Customer's sex
age	|Age
fecha_alta	|The date in which the customer became as the first holder of a contract in the bank
ind_nuevo	|New customer Index. 1 if the customer registered in the last 6 months.
antiguedad	|Customer seniority (in months)
indrel	|1 (First/Primary), 99 (Primary customer during the month but not at the end of the month)
ult_fec_cli_1t	|Last date as primary customer (if he isn't at the end of the month)
indrel_1mes	|Customer type at the beginning of the month ,1 (First/Primary customer), 2 (co-owner ),P (Potential),3 (former primary), 4(former co-owner)
tiprel_1mes	|Customer relation type at the beginning of the month, A (active), I (inactive), P (former customer),R (Potential)
indresi	|Residence index (S (Yes) or N (No) if the residence country is the same than the bank country)
indext	|Foreigner index (S (Yes) or N (No) if the customer's birth country is different than the bank country)
conyuemp	|Spouse index. 1 if the customer is spouse of an employee
canal_entrada	|channel used by the customer to join
indfall	|Deceased index. N/S
tipodom	|Addres type. 1, primary address
cod_prov	|Province code (customer's address)
nomprov	|Province name
ind_actividad_cliente	Activity |index (1, active customer; 0, inactive customer)
renta	|Gross income of the household
segmento	|segmentation: 01 - VIP, 02 - Individuals 03 - college graduated
ind_ahor_fin_ult1	|Saving Account
ind_aval_fin_ult1	|Guarantees
ind_cco_fin_ult1	|Current Accounts
ind_cder_fin_ult1	|Derivada Account
ind_cno_fin_ult1	|Payroll Account
ind_ctju_fin_ult1	|Junior Account
ind_ctma_fin_ult1	|Más particular Account
ind_ctop_fin_ult1	|particular Account
ind_ctpp_fin_ult1	|particular Plus Account
ind_deco_fin_ult1	|Short-term deposits
ind_deme_fin_ult1	|Medium-term deposits
ind_dela_fin_ult1	|Long-term deposits
ind_ecue_fin_ult1	|e-account
ind_fond_fin_ult1	|Funds
ind_hip_fin_ult1	|Mortgage
ind_plan_fin_ult1	|Pensions
ind_pres_fin_ult1	|Loans
ind_reca_fin_ult1	|Taxes
ind_tjcr_fin_ult1	|Credit Card
ind_valo_fin_ult1	|Securities
ind_viv_fin_ult1	|Home Account
ind_nomina_ult1	|Payroll
ind_nom_pens_ult1	|Pensions
ind_recibo_ult1	|Direct Debit

# 난관들

1. 데이터 규모와 전처리
2. Feature selection
3. [추천시스템](https://lsjsj92.tistory.com/563) 이곳을 참고하자. 찾아보니 케글의 경우 [영화추천시스템](https://www.kaggle.com/rounakbanik/the-movies-dataset) 이게 있더라
4. 추천시스템은 분류 문제중에서도 굉장히 난이도 있는 알고리즘이다. 그걸 여기에 좀 빠지고 나서 알았다.
5. 분류 문제는 몇 가지로 나뉜다. 스팸문자, 생존자 분류 같은 Binary Classification / Mnist 같은 Multi Classification
6. 이 두 가지의 경우에는 Label 이 하나이다. 그러니까 이게 스팸 문자인지, 생존자인지, 숫자중에 몇인지 분류해야되는 label이 하나라는 것이다.
7. 다음으로 가면 Multi Label 이 등장한다. multi label 은 분류한 적이 없지만 핸즈온 머신러닝에 따르면 이렇다.
8. 철수, 영희, 찰리 세 명의 얼굴을 인식하도록 훈련된 모델이 있다. 철수, 찰리가 있고 영희가 없는 사진을 본다면 이 모델은 [철수 있음, 영희 없음, 찰리 있음] 같이 다중 레이블로 분류해야 한다.
9. 핸즈온 머신러닝에서는 다중 출력 분류(multioutput-multiclass classification)라는 것도 다룬다. 쉽게 말하면 다중 레이블 + 다중 클래스이다.
10. 여기서부턴 내 뇌피셜이다. 그렇다면 추천시스템은 어디에 속하는가? 일단 다중 클래스인건 누가봐도 분명하다. 아주 여러가지 상품 중에서 한 가지를 추천하는 것이니까
11. 근데 이게 막상 처음 접하면 아주 어렵다. 협업필터링에 대해 알고가
