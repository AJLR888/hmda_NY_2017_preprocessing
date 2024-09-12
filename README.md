This code include the first steps done on the data preprocessing process of the data set hmda_NY_2017 FROM:
(https://www.consumerfinance.gov/data-research/hmda/historic-data/?geo=ny&records=all-records&field_descriptions=labels)

In this code we have:
A) Selected "no co-applicant" records from the column "co_applicant_ethnicity_name"
B) Filter columns:
  action_taken_name
  denial_reason_name_1
C) Created the column "action_taken":
    df['action_taken'] = df['action_taken_name'].replace({ 'Loan originated': 'approved', 'Application approved but not accepted': 'approved', 'Application denied by financial institution': 'denied' })

D) First feature selection:
    df = df[
    
    ['loan_type_name', 'property_type_name', 'loan_purpose_name', 'loan_amount_000s', 'action_taken', 'msamd_name', 'applicant_ethnicity_name', 'applicant_race_name_1', 'applicant_sex_name', 'applicant_income_000s', 'denial_reason_name_1', 'denial_reason_name_2', 'denial_reason_name_3', 'rate_spread', 'lien_status_name', 'minority_population', 'hud_median_family_income', 'tract_to_msamd_income']
    
    ]

E) Excluded "Credit application incomplete" records from the column "denial_reason_name_1"
