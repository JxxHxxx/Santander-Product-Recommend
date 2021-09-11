
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

