# bootcamp
Bootcamp EDSA
Data reduction
#Drop variables with unary values

#Categorical variables
#hr_ds.drop('Over18', axis = 1, inplace = True)

#Numerical variables
#hr_ds.drop('StandardHours', axis = 1, inplace = True)
#hr_ds.drop('EmployeeCount', axis = 1, inplace = True)

#Drop variables with high correlation? 
As variáveis'YearsAtCompany', 'YearsInCurrentRole', 'YearsSinceLastPromotion', 'YearsWithCurrManager', têm correlação positiva > 0,7. Poderá indicar multicolinearidade.

#Data reduction com CPA?

#Variável sexo: transformar em numérica.
#criar bins nas 

*#Outliers: contar quais são e quantos são. Definir IQR para as duas colunas: 'YearsAtCompany' e 'YearsSinceLastPromotion'. trabalhadores têm *
**#Identify outliers 'YearsAtCompany**'
q25_Y = (hr_ds['YearsAtCompany'].quantile(q=0.25))
q75_Y = (hr_ds['YearsAtCompany'].quantile(q=0.75))
iqr_Y = q75_Y - q25_Y
print('q25 Years@Company =', q25_Y, 'q75 Years@Company =', q75_Y, 'iqr Years@Company =', iqr_Y)
# calculate the outlier cutoff
cut_off_Y = iqr_Y * 1.5
lower_Y, upper_Y = q25_Y - cut_off_Y, q75_Y + cut_off_Y
print('lower Years@Company', lower_Y)
print('upper Years@Company', upper_Y)
#hr_ds_outlier_Y =    hr_ds [(hr_ds ['YearsAtCompany'] > 18)  & (hr_ds['Attrition'] == 'Yes')]
hr_ds_outlier_Y =    hr_ds [(hr_ds ['YearsAtCompany'] > 18)]
#len(hr_ds_outlier_Y)

**#Identify outliers 'YearsSinceLastPromotion'**
q25 = (hr_ds['YearsSinceLastPromotion'].quantile(q=0.25))
q75 = (hr_ds['YearsSinceLastPromotion'].quantile(q=0.75))
iqr = q75 - q25
print('q25 =', q25, 'q75 =', q75, 'iqr =', iqr)
# calculate the outlier cutoff
cut_off = iqr * 1.5
lower, upper = q25 - cut_off, q75 + cut_off
print('lower', lower)
print('upper', upper)
hr_ds_outlier =    hr_ds [(hr_ds ['YearsSinceLastPromotion'] > 8) ]
#hr_ds_outlier =    hr_ds [(hr_ds ['YearsSinceLastPromotion'] > 18)  & (hr_ds['YearsSinceLastPromotion'] == 'Yes')]
len(hr_ds_outlier)


#job level vs monthly income estão super correlacionados

#transformar as variáveis, qualitativas em quantitativas.
Department
EducationField
OverTime
MaritalStatus
JobRole
