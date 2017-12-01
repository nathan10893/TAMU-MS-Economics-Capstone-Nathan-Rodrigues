libname econ "C:\Users\User\Documents\TexasA&M Courses\Fall2017\ECON 675\Data\SAS";

*Import HMDA and Census data for the years 2012 - 2016. Use single quotes (') instead of double ("). 
	SAS will then interpret the quoted path as a literal string without trying to resolve apparent macro variables 
 	(which always start with &) that it contains;
proc import datafile = 'C:\Users\User\Documents\TexasA&M Courses\Fall2017\ECON 675\Data\HMDA\hmda_2016.csv'
	out = Econ.hmda2016 (rename = (state_abbr = state))
 	dbms = CSV replace;
run;
proc import datafile = 'C:\Users\User\Documents\TexasA&M Courses\Fall2017\ECON 675\Data\HMDA\hmda_2015.csv'
	out = Econ.hmda2015 (rename = (state_abbr = state))
 	dbms = CSV replace;
run;
proc import datafile = 'C:\Users\User\Documents\TexasA&M Courses\Fall2017\ECON 675\Data\HMDA\hmda_2014.csv'
	out = Econ.hmda2014 (rename = (state_abbr = state))
 	dbms = CSV replace;
run;
proc import datafile = 'C:\Users\User\Documents\TexasA&M Courses\Fall2017\ECON 675\Data\HMDA\hmda_2013.csv'
	out = Econ.hmda2013 (rename = (state_abbr = state))
 	dbms = CSV replace;
run;
proc import datafile = 'C:\Users\User\Documents\TexasA&M Courses\Fall2017\ECON 675\Data\HMDA\hmda_2012.csv'
	out = Econ.hmda2012 (rename = (state_abbr = state))
 	dbms = CSV replace;
run;

*Import 2012 - 2016 BLS Unemployment Data;
proc import datafile = 'C:\Users\User\Documents\TexasA&M Courses\Fall2017\ECON 675\Data\BLS Unemployment Data\CSV Files\laucnty16.csv'
	out = Econ.bls16
 	dbms = CSV replace;
	datarow = 3;
run;
proc import datafile = 'C:\Users\User\Documents\TexasA&M Courses\Fall2017\ECON 675\Data\BLS Unemployment Data\CSV Files\laucnty15.csv'
	out = Econ.bls15
 	dbms = CSV replace;
	datarow = 3;
run;
proc import datafile = 'C:\Users\User\Documents\TexasA&M Courses\Fall2017\ECON 675\Data\BLS Unemployment Data\CSV Files\laucnty14.csv'
	out = Econ.bls14
 	dbms = CSV replace;
	datarow = 3;
run;
proc import datafile = 'C:\Users\User\Documents\TexasA&M Courses\Fall2017\ECON 675\Data\BLS Unemployment Data\CSV Files\laucnty13.csv'
	out = Econ.bls13
 	dbms = CSV replace;
	datarow = 3;
run;
proc import datafile = 'C:\Users\User\Documents\TexasA&M Courses\Fall2017\ECON 675\Data\BLS Unemployment Data\CSV Files\laucnty12.csv'
	out = Econ.bls12
 	dbms = CSV replace;
	datarow = 3;
run;

*Import Veteran population data;
proc import datafile = 'C:\Users\User\Documents\TexasA&M Courses\Fall2017\ECON 675\Data\ACS Veteran Data\ACS_16.csv'
	out = Econ.acs16 (keep = geo_id2 HD01_VD08 HD01_VD11 HD01_VD14 HD01_VD17 HD01_VD20 HD01_VD23 HD01_VD27 HD01_VD30 HD01_VD33
	HD01_VD36 HD01_VD39 HD01_VD42 rename=(geo_id2 = fips HD01_VD08 = m_total_vet HD01_VD11 = m_18_34 HD01_VD14 = m_35_54
 	HD01_VD17 = m_55_64 HD01_VD20 = m_65_74 HD01_VD23 = m_75_over HD01_VD27 = f_total_vet HD01_VD30 = f_18_34 HD01_VD33 = f_35_54
	HD01_VD36 = f_55_64 HD01_VD39 = f_65_74 HD01_VD42 = f_75_over))
 	dbms = CSV replace;
	datarow = 3;
run;
proc import datafile = 'C:\Users\User\Documents\TexasA&M Courses\Fall2017\ECON 675\Data\ACS Veteran Data\ACS_15.csv'
	out = Econ.acs15 (keep = geo_id2 HD01_VD08 HD01_VD11 HD01_VD14 HD01_VD17 HD01_VD20 HD01_VD23 HD01_VD27 HD01_VD30 HD01_VD33
	HD01_VD36 HD01_VD39 HD01_VD42 rename=(geo_id2 = fips HD01_VD08 = m_total_vet HD01_VD11 = m_18_34 HD01_VD14 = m_35_54
 	HD01_VD17 = m_55_64 HD01_VD20 = m_65_74 HD01_VD23 = m_75_over HD01_VD27 = f_total_vet HD01_VD30 = f_18_34 HD01_VD33 = f_35_54
	HD01_VD36 = f_55_64 HD01_VD39 = f_65_74 HD01_VD42 = f_75_over))
 	dbms = CSV replace;
	datarow = 3;
run;
proc import datafile = 'C:\Users\User\Documents\TexasA&M Courses\Fall2017\ECON 675\Data\ACS Veteran Data\ACS_14.csv'
	out = Econ.acs14 (keep = geo_id2 HD01_VD08 HD01_VD11 HD01_VD14 HD01_VD17 HD01_VD20 HD01_VD23 HD01_VD27 HD01_VD30 HD01_VD33
	HD01_VD36 HD01_VD39 HD01_VD42 rename=(geo_id2 = fips HD01_VD08 = m_total_vet HD01_VD11 = m_18_34 HD01_VD14 = m_35_54
 	HD01_VD17 = m_55_64 HD01_VD20 = m_65_74 HD01_VD23 = m_75_over HD01_VD27 = f_total_vet HD01_VD30 = f_18_34 HD01_VD33 = f_35_54
	HD01_VD36 = f_55_64 HD01_VD39 = f_65_74 HD01_VD42 = f_75_over))
 	dbms = CSV replace;
	datarow = 3;
run;
proc import datafile = 'C:\Users\User\Documents\TexasA&M Courses\Fall2017\ECON 675\Data\ACS Veteran Data\ACS_13.csv'
	out = Econ.acs13 (keep = geo_id2 HD01_VD08 HD01_VD11 HD01_VD14 HD01_VD17 HD01_VD20 HD01_VD23 HD01_VD27 HD01_VD30 HD01_VD33
	HD01_VD36 HD01_VD39 HD01_VD42 rename=(geo_id2 = fips HD01_VD08 = m_total_vet HD01_VD11 = m_18_34 HD01_VD14 = m_35_54
 	HD01_VD17 = m_55_64 HD01_VD20 = m_65_74 HD01_VD23 = m_75_over HD01_VD27 = f_total_vet HD01_VD30 = f_18_34 HD01_VD33 = f_35_54
	HD01_VD36 = f_55_64 HD01_VD39 = f_65_74 HD01_VD42 = f_75_over))
 	dbms = CSV replace;
	datarow = 3;
run;
proc import datafile = 'C:\Users\User\Documents\TexasA&M Courses\Fall2017\ECON 675\Data\ACS Veteran Data\ACS_12.csv'
	out = Econ.acs12 (keep = geo_id2 HD01_VD08 HD01_VD11 HD01_VD14 HD01_VD17 HD01_VD20 HD01_VD23 HD01_VD27 HD01_VD30 HD01_VD33
	HD01_VD36 HD01_VD39 HD01_VD42 rename=(geo_id2 = fips HD01_VD08 = m_total_vet HD01_VD11 = m_18_34 HD01_VD14 = m_35_54
 	HD01_VD17 = m_55_64 HD01_VD20 = m_65_74 HD01_VD23 = m_75_over HD01_VD27 = f_total_vet HD01_VD30 = f_18_34 HD01_VD33 = f_35_54
	HD01_VD36 = f_55_64 HD01_VD39 = f_65_74 HD01_VD42 = f_75_over))
 	dbms = CSV replace;
	datarow = 3;
run;
*Import VA Loan Limit data;
proc import datafile = 'C:\Users\User\Documents\TexasA&M Courses\Fall2017\ECON 675\Data\VA Loan Limits\limit2016.csv'
	out = Econ.limit16 (keep = FIPS_State_Code FIPS_County_Code One_Unit_Limit)
 	dbms = CSV replace;
run;
proc import datafile = 'C:\Users\User\Documents\TexasA&M Courses\Fall2017\ECON 675\Data\VA Loan Limits\limit2015.csv'
	out = Econ.limit15 (keep = FIPS_State_Code FIPS_County_Code One_Unit_Limit)
 	dbms = CSV replace;
run;
proc import datafile = 'C:\Users\User\Documents\TexasA&M Courses\Fall2017\ECON 675\Data\VA Loan Limits\limit2014.csv'
	out = Econ.limit14 (keep = FIPS_State_Code FIPS_County_Code One_Unit_Limit)
 	dbms = CSV replace;
run;
proc import datafile = 'C:\Users\User\Documents\TexasA&M Courses\Fall2017\ECON 675\Data\VA Loan Limits\limit2013.csv'
	out = Econ.limit13 (keep = FIPS_State_Code FIPS_County_Code One_Unit_Limit)
 	dbms = CSV replace;
run;
proc import datafile = 'C:\Users\User\Documents\TexasA&M Courses\Fall2017\ECON 675\Data\VA Loan Limits\limit2012.csv'
	out = Econ.limit12 (keep = FIPS_State_Code FIPS_County_Code One_Unit_Limit)
 	dbms = CSV replace;
run;

*Import 2016 County Level Presidential Election Results;
proc import datafile = 'C:\Users\User\Documents\TexasA&M Courses\Fall2017\ECON 675\Data\Election Results\2016_US_County_Level_Presidential_Results.csv'
	out = Econ.elections16 (keep = combined_fips per_dem per_gop 
	rename = (combined_fips = fips))
 	dbms = CSV replace;
run;

*Import 2012 - 2016 Census data for population by race;
proc import datafile = 'C:\Users\User\Documents\TexasA&M Courses\Fall2017\ECON 675\Data\Census Race by Population Data\census data.csv'
	out = Econ.race_data (where = (agegrp = 0) keep = state agegrp tot_pop county year wa_male wa_female ba_male ba_female ia_male ia_female
			aa_male aa_female na_male na_female)
 	dbms = CSV replace;
run;
data econ.race (where = (year > 4) drop = combfips state county agegrp); *Cleans Race data;
	set econ.race_data;
	county = put(county, z3.); *adds leading zeros;
	format county z3.;
	combfips = cat(vvalue(state), vvalue(county)); *combines state and county fips;
	fips = input(combfips, best32.); *new numeric variable;
	if year = 5 then year = 2012; if year = 6 then year = 2013; if year = 7 then year = 2014; 
	if year = 8 then year = 2015; if year = 9 then year = 2016;
	wa_m = log(wa_male);         
	wa_f = log(wa_female);
	ba_m = log(ba_male);
	ba_f = log(ba_female);
	ia_m = log(ia_male); 
	ia_f = log(ia_female);
	aa_m = log(aa_male);
	aa_f = log(aa_female);
	na_m = log(na_male);
	na_f = log(na_female);
	if nmiss(of wa_m wa_f ba_m ba_f ia_m ia_f aa_m aa_f na_m na_f) > 0 then delete;
run;
proc sort data = econ.race; *Sorts Race data;
	by year fips;
run;
data econ.acs16; *Adds in year variable for veteran data;
set econ.acs16;
year = 2016;
m_vet = log(m_total_vet);
f_vet = log(f_total_vet);
run;
data econ.acs15; *Adds in year variable for veteran data;
set econ.acs15;
year = 2015;
m_vet = log(m_total_vet);
f_vet = log(f_total_vet);
run;
data econ.acs14; *Adds in year variable for veteran data;
set econ.acs14;
year = 2014;
m_vet = log(m_total_vet);
f_vet = log(f_total_vet);
run;
data econ.acs13; *Adds in year variable for veteran data;
set econ.acs13;
year = 2013;
m_vet = log(m_total_vet);
f_vet = log(f_total_vet);
run;
data econ.acs12; *Adds in year variable for veteran data;
set econ.acs12;
year = 2012;
m_vet = log(m_total_vet);
f_vet = log(f_total_vet);
run;

*We can merge Unemployment data with Election data by 'year' and by 'combined fips'. 
This section creates the combined fips field which I will call 'fips';

data econ.unemp16 (keep = Year Unemployment_Rate fips); *cleans unemployment data;
	set econ.bls16;
	if cmiss(of _all_) then delete; *deletes missing rows;
	County_FIPS_Code = put(County_FIPS_Code, z3.); *adds leading zeros;
	format County_FIPS_Code z3.;
	State_FIPS_Code = put(State_FIPS_Code, z2.); *adds leading zeros;
	format State_FIPS_Code z2.;
	comb_fips = cat(vvalue(State_FIPS_Code), vvalue(County_FIPS_Code)); *combines state and county fips;
	fips = input(comb_fips, best5.); *new numeric variable;
run;
data econ.unemp15 (keep = Year Unemployment_Rate fips); *cleans unemployment data;
	set econ.bls15;
	if cmiss(of _all_) then delete; 
	County_FIPS_Code = put(County_FIPS_Code, z3.);
	format County_FIPS_Code z3.;
	State_FIPS_Code = put(State_FIPS_Code, z2.);
	format State_FIPS_Code z2.;
	comb_fips = cat(vvalue(State_FIPS_Code), vvalue(County_FIPS_Code));
	fips = input(comb_fips, best5.); *new numeric variable;
run;
data econ.unemp14 (keep = Year Unemployment_Rate fips); *cleans unemployment data;
	set econ.bls14;
	if cmiss(of _all_) then delete; 
	County_FIPS_Code = put(County_FIPS_Code, z3.);
	format County_FIPS_Code z3.;
	State_FIPS_Code = put(State_FIPS_Code, z2.);
	format State_FIPS_Code z2.;
	comb_fips = cat(vvalue(State_FIPS_Code), vvalue(County_FIPS_Code));
	fips = input(comb_fips, best5.); *new numeric variable;
run;
data econ.unemp13 (keep = Year Unemployment_Rate fips); *cleans unemployment data;
	set econ.bls13;
	if cmiss(of _all_) then delete; 
	County_FIPS_Code = put(County_FIPS_Code, z3.);
	format County_FIPS_Code z3.;
	State_FIPS_Code = put(State_FIPS_Code, z2.);
	format State_FIPS_Code z2.;
	comb_fips = cat(vvalue(State_FIPS_Code), vvalue(County_FIPS_Code));
	fips = input(comb_fips, best5.); *new numeric variable;
run;
data econ.unemp12 (keep = Year Unemployment_Rate fips); *cleans unemployment data;
	set econ.bls12;
	if cmiss(of _all_) then delete; *deletes missing rows
	County_FIPS_Code = put(County_FIPS_Code, z3.);
	format County_FIPS_Code z3.;
	State_FIPS_Code = put(State_FIPS_Code, z2.);
	format State_FIPS_Code z2.;
	comb_fips = cat(vvalue(State_FIPS_Code), vvalue(County_FIPS_Code));
	fips = input(comb_fips, best5.); *new numeric variable;
run;
*This sections cleans up VA Loan Limit Data;
data econ.va16 (keep = Year loan_limit fips); *cleans va loan limit data;
	set econ.limit16;
	if cmiss(of _all_) then delete; *deletes missing rows;
	County_FIPS_Code = put(FIPS_County_Code, z3.); *adds leading zeros;
	format FIPS_County_Code z3.;
	State_FIPS_Code = put(FIPS_State_Code, z2.); *adds leading zeros;
	format FIPS_State_Code z2.;
	comb_fips = cat(vvalue(FIPS_State_Code), vvalue(FIPS_County_Code)); *combines state and county fips;
	fips = input(comb_fips, best5.); *new numeric variable;
	lm = input(one_unit_limit, dollar8.);
	loan_limit = log(lm);
	year = 2016;
run;
data econ.va15 (keep = Year loan_limit fips); *cleans va loan limit data;
	set econ.limit15;
	if cmiss(of _all_) then delete; *deletes missing rows;
	County_FIPS_Code = put(FIPS_County_Code, z3.); *adds leading zeros;
	format FIPS_County_Code z3.;
	State_FIPS_Code = put(FIPS_State_Code, z2.); *adds leading zeros;
	format FIPS_State_Code z2.;
	comb_fips = cat(vvalue(FIPS_State_Code), vvalue(FIPS_County_Code)); *combines state and county fips;
	fips = input(comb_fips, best5.); *new numeric variable;
	lm = input(one_unit_limit, dollar8.);
	loan_limit = log(lm);
	year = 2015;
run;
data econ.va14 (keep = Year loan_limit fips); *cleans va loan limit data;
	set econ.limit14;
	if cmiss(of _all_) then delete; *deletes missing rows;
	County_FIPS_Code = put(FIPS_County_Code, z3.); *adds leading zeros;
	format FIPS_County_Code z3.;
	State_FIPS_Code = put(FIPS_State_Code, z2.); *adds leading zeros;
	format FIPS_State_Code z2.;
	comb_fips = cat(vvalue(FIPS_State_Code), vvalue(FIPS_County_Code)); *combines state and county fips;
	fips = input(comb_fips, best5.); *new numeric variable;
	lm = input(one_unit_limit, dollar8.);
	loan_limit = log(lm);
	year = 2014;
run;
data econ.va13 (keep = Year loan_limit fips); *cleans va loan limit data;
	set econ.limit13;
	if cmiss(of _all_) then delete; *deletes missing rows;
	County_FIPS_Code = put(FIPS_County_Code, z3.); *adds leading zeros;
	format FIPS_County_Code z3.;
	State_FIPS_Code = put(FIPS_State_Code, z2.); *adds leading zeros;
	format FIPS_State_Code z2.;
	comb_fips = cat(vvalue(FIPS_State_Code), vvalue(FIPS_County_Code)); *combines state and county fips;
	fips = input(comb_fips, best5.); *new numeric variable;
	lm = input(one_unit_limit, dollar8.);
	loan_limit = log(lm);
	year = 2013;
run;
data econ.va12 (keep = Year loan_limit fips); *cleans va loan limit data;
	set econ.limit12;
	if cmiss(of _all_) then delete; *deletes missing rows;
	County_FIPS_Code = put(FIPS_County_Code, z3.); *adds leading zeros;
	format FIPS_County_Code z3.;
	State_FIPS_Code = put(FIPS_State_Code, z2.); *adds leading zeros;
	format FIPS_State_Code z2.;
	comb_fips = cat(vvalue(FIPS_State_Code), vvalue(FIPS_County_Code)); *combines state and county fips;
	fips = input(comb_fips, best5.); *new numeric variable;
	lm = input(one_unit_limit, dollar8.);
	loan_limit = log(lm);
	year = 2012;
run;

*This section cleans up the HMDA data and outputs it into a new dataset, "loan". The categorical data is already in the
hmda dataset and each column with categorical data preceeds a column depicting what each category stands for;
data econ.loan16 (where = (race < 6 and action = 1 and ethnicity < 3 or race < 6 and action = 3 and ethnicity < 3) 
		keep = year state action race app_income sex lien loan_prps preapp loan_amount min_pop fips 
		ethnicity);
	set econ.hmda2016;
	race = input(applicant_race_1, best1.); *converts to numeric;
		year = input(as_of_year, best4.); *converts to numeric;
		action = input(action_taken, best1.); *converts to numeric;
 		app_income = input(applicant_income_000s, best32.); *converts to numeric;
		sex = input(applicant_sex, best1.); *converts to numeric;
		denial = input(denial_reason_1, best1.); *converts to numeric;
		ethnicity = input(applicant_ethnicity, best1.); *converts to numeric;
		loan_amount = input(loan_amount_000s, best32.); *converts to numeric;
		min_pop = input(minority_population, best32.); *converts to numeric;
		lien = input(lien_status, best1.); *converts to numeric;
		loan_prps = input(loan_purpose, best1.); *converts to numeric;
		preapp = input(preapproval, best1.); *converts to numeric;
	county_code = put(input(cats(county_code),8.), z3.); *adds leading zeros;
	 	state_code = put(input(cats(state_code),8.), z2.); *adds leading zeros;
	comb_fips = catt(vvalue(state_code), vvalue(county_code)); *combines state and county fips;
		fips = input(comb_fips, best5.); *new numeric variable;
	app_income = 1000*(app_income); *initally rounded to nearest thousand;
		app_income = log(app_income); 
		loan_amount = 1000*(loan_amount); *initally rounded to nearest thousand;
		loan_amount = log(loan_amount);

	if cmiss(app_income) then delete; *deletes rows with missing data ...;
	*if cmiss(denial) then delete;
	if cmiss(min_pop) then delete;
	if cmiss(fips) then delete;
run;
data econ.loan15 (where = (race < 6 and action = 1 and ethnicity < 3 or race < 6 and action = 3 and ethnicity < 3) 
		keep = year state action race app_income sex lien loan_prps preapp loan_amount min_pop fips 
		ethnicity);
	set econ.hmda2015;
	race = input(applicant_race_1, best1.); *converts to numeric;
		year = input(as_of_year, best4.); *converts to numeric;
		action = input(action_taken, best1.); *converts to numeric;
 		app_income = input(applicant_income_000s, best32.); *converts to numeric;
		sex = input(applicant_sex, best1.); *converts to numeric;
		denial = input(denial_reason_1, best1.); *converts to numeric;
		ethnicity = input(applicant_ethnicity, best1.); *converts to numeric;
		loan_amount = input(loan_amount_000s, best32.); *converts to numeric;
		min_pop = input(minority_population, best32.); *converts to numeric;
		lien = input(lien_status, best1.); *converts to numeric;
		loan_prps = input(loan_purpose, best1.); *converts to numeric;
		preapp = input(preapproval, best1.); *converts to numeric;
	county_code = put(input(cats(county_code),8.), z3.); *adds leading zeros;
	 	state_code = put(input(cats(state_code),8.), z2.); *adds leading zeros;
	comb_fips = catt(vvalue(state_code), vvalue(county_code)); *combines state and county fips;
		fips = input(comb_fips, best5.); *new numeric variable;
	app_income = 1000*(app_income); *initally rounded to nearest thousand;
		app_income = log(app_income); 
		loan_amount = 1000*(loan_amount); *initally rounded to nearest thousand;
		loan_amount = log(loan_amount);

	if cmiss(app_income) then delete; *deletes rows with missing data ...;
	*if cmiss(denial) then delete;
	if cmiss(min_pop) then delete;
	if cmiss(fips) then delete;
run;
data econ.loan14 (where = (race < 6 and action = 1 and ethnicity < 3 or race < 6 and action = 3 and ethnicity < 3) 
		keep = year state action race app_income sex lien loan_prps preapp loan_amount min_pop fips 
		ethnicity);
	set econ.hmda2014;
	race = input(applicant_race_1, best1.); *converts to numeric;
		year = input(as_of_year, best4.); *converts to numeric;
		action = input(action_taken, best1.); *converts to numeric;
 		app_income = input(applicant_income_000s, best32.); *converts to numeric;
		sex = input(applicant_sex, best1.); *converts to numeric;
		denial = input(denial_reason_1, best1.); *converts to numeric;
		ethnicity = input(applicant_ethnicity, best1.); *converts to numeric;
		loan_amount = input(loan_amount_000s, best32.); *converts to numeric;
		min_pop = input(minority_population, best32.); *converts to numeric;
		lien = input(lien_status, best1.); *converts to numeric;
		loan_prps = input(loan_purpose, best1.); *converts to numeric;
		preapp = input(preapproval, best1.); *converts to numeric;
	county_code = put(input(cats(county_code),8.), z3.); *adds leading zeros;
	 	state_code = put(input(cats(state_code),8.), z2.); *adds leading zeros;
	comb_fips = catt(vvalue(state_code), vvalue(county_code)); *combines state and county fips;
		fips = input(comb_fips, best5.); *new numeric variable;
	app_income = 1000*(app_income); *initally rounded to nearest thousand;
		app_income = log(app_income); 
		loan_amount = 1000*(loan_amount); *initally rounded to nearest thousand;
		loan_amount = log(loan_amount);

	if cmiss(app_income) then delete; *deletes rows with missing data ...;
	*if cmiss(denial) then delete;
	if cmiss(min_pop) then delete;
	if cmiss(fips) then delete;
run;
data econ.loan13 (where = (race < 6 and action = 1 and ethnicity < 3 or race < 6 and action = 3 and ethnicity < 3) 
		keep = year state action race app_income sex lien loan_prps preapp loan_amount min_pop fips 
		ethnicity);
	set econ.hmda2013;
	race = input(applicant_race_1, best1.); *converts to numeric;
		year = input(as_of_year, best4.); *converts to numeric;
		action = input(action_taken, best1.); *converts to numeric;
 		app_income = input(applicant_income_000s, best32.); *converts to numeric;
		sex = input(applicant_sex, best1.); *converts to numeric;
		denial = input(denial_reason_1, best1.); *converts to numeric;
		ethnicity = input(applicant_ethnicity, best1.); *converts to numeric;
		loan_amount = input(loan_amount_000s, best32.); *converts to numeric;
		min_pop = input(minority_population, best32.); *converts to numeric;
		lien = input(lien_status, best1.); *converts to numeric;
		loan_prps = input(loan_purpose, best1.); *converts to numeric;
		preapp = input(preapproval, best1.); *converts to numeric;
	county_code = put(input(cats(county_code),8.), z3.); *adds leading zeros;
	 	state_code = put(input(cats(state_code),8.), z2.); *adds leading zeros;
	comb_fips = catt(vvalue(state_code), vvalue(county_code)); *combines state and county fips;
		fips = input(comb_fips, best5.); *new numeric variable;
	app_income = 1000*(app_income); *initally rounded to nearest thousand;
		app_income = log(app_income); 
		loan_amount = 1000*(loan_amount); *initally rounded to nearest thousand;
		loan_amount = log(loan_amount);

	if cmiss(app_income) then delete; *deletes rows with missing data ...;
	*if cmiss(denial) then delete;
	if cmiss(min_pop) then delete;
	if cmiss(fips) then delete;
run;

data econ.loan12 (where = (race < 6 and action = 1 and ethnicity < 3 or race < 6 and action = 3 and ethnicity < 3) 
		keep = year state action race app_income sex lien loan_prps preapp loan_amount min_pop fips 
		ethnicity);
	set econ.hmda2012;
	race = input(applicant_race_1, best1.); *converts to numeric;
		year = input(as_of_year, best4.); *converts to numeric;
		action = input(action_taken, best1.); *converts to numeric;
 		app_income = input(applicant_income_000s, best32.); *converts to numeric;
		sex = input(applicant_sex, best1.); *converts to numeric;
		denial = input(denial_reason_1, best1.); *converts to numeric;
		ethnicity = input(applicant_ethnicity, best1.); *converts to numeric;
		loan_amount = input(loan_amount_000s, best32.); *converts to numeric;
		min_pop = input(minority_population, best32.); *converts to numeric;
		lien = input(lien_status, best1.); *converts to numeric;
		loan_prps = input(loan_purpose, best1.); *converts to numeric;
		preapp = input(preapproval, best1.); *converts to numeric;
	county_code = put(input(cats(county_code),8.), z3.); *adds leading zeros;
	 	state_code = put(input(cats(state_code),8.), z2.); *adds leading zeros;
	comb_fips = catt(vvalue(state_code), vvalue(county_code)); *combines state and county fips;
		fips = input(comb_fips, best5.); *new numeric variable
	app_income = 1000*(app_income); *initally rounded to nearest thousand;
		app_income = log(app_income); 
		loan_amount = 1000*(loan_amount); *initally rounded to nearest thousand;
		loan_amount = log(loan_amount);

	if cmiss(app_income) then delete; *deletes rows with missing data ...;
	*if cmiss(denial) then delete;
	if cmiss(min_pop) then delete;
	if cmiss(fips) then delete;
run;
data econ.loan16_coapp (where = (race < 6 and action = 1 and ethnicity < 3 
							  or race < 6 and action = 3 and ethnicity < 3) 
	keep = year state action race app_income sex lien loan_prps preapp loan_amount min_pop fips 
		ethnicity coapp co_applicant_ethnicity coapp_eth co_applicant_race_1 coapp_race co_applicant_sex coapp_sex);
	set econ.hmda2016;
		race = input(applicant_race_1, best1.); *converts to numeric;
		year = input(as_of_year, best4.); *converts to numeric;
		action = input(action_taken, best1.); *converts to numeric;
 		app_income = input(applicant_income_000s, best32.); *converts to numeric;
		sex = input(applicant_sex, best1.); *converts to numeric;
		denial = input(denial_reason_1, best1.); *converts to numeric;
		ethnicity = input(applicant_ethnicity, best1.); *converts to numeric;
		coapp_eth = input(co_applicant_ethnicity, best32.);
		coapp_race = input(co_applicant_race_1, best32.);
		coapp_sex = input(co_applicant_sex, best32.);
		loan_amount = input(loan_amount_000s, best32.); *converts to numeric;
		min_pop = input(minority_population, best32.); *converts to numeric;
		lien = input(lien_status, best1.); *converts to numeric;
		loan_prps = input(loan_purpose, best1.); *converts to numeric;
		preapp = input(preapproval, best1.); *converts to numeric;
		county_code = put(input(cats(county_code),8.), z3.); *adds leading zeros;
	 	state_code = put(input(cats(state_code),8.), z2.); *adds leading zeros;
		comb_fips = catt(vvalue(state_code), vvalue(county_code)); *combines state and county fips;
		fips = input(comb_fips, best5.); *new numeric variable;
		app_income = 1000*(app_income); *initally rounded to nearest thousand;
		app_income = log(app_income); 
		loan_amount = 1000*(loan_amount); *initally rounded to nearest thousand;
		loan_amount = log(loan_amount);
	
	if co_applicant_ethnicity = 3 or co_applicant_ethnicity = 4 then delete;
	if co_applicant_race_1 = 6 or co_applicant_race_1 = 7 then delete;
	if co_applicant_sex = 3 or co_applicant_sex = 4 then delete;
	if co_applicant_ethnicity = 5 or co_applicant_race_1 = 8 then coapp = 0;
		else coapp = 1;

	if cmiss(app_income) then delete; *deletes rows with missing data ...;
	*if cmiss(denial) then delete;
	if cmiss(min_pop) then delete;
	if cmiss(fips) then delete;
run;
data econ.loan15_coapp (where = (race < 6 and action = 1 and ethnicity < 3 
							  or race < 6 and action = 3 and ethnicity < 3) 
	keep = year state action race app_income sex lien loan_prps preapp loan_amount min_pop fips 
		ethnicity coapp co_applicant_ethnicity coapp_eth co_applicant_race_1 coapp_race co_applicant_sex coapp_sex);
	set econ.hmda2015;
		race = input(applicant_race_1, best1.); *converts to numeric;
		year = input(as_of_year, best4.); *converts to numeric;
		action = input(action_taken, best1.); *converts to numeric;
 		app_income = input(applicant_income_000s, best32.); *converts to numeric;
		sex = input(applicant_sex, best1.); *converts to numeric;
		denial = input(denial_reason_1, best1.); *converts to numeric;
		ethnicity = input(applicant_ethnicity, best1.); *converts to numeric;
		coapp_eth = input(co_applicant_ethnicity, best32.);
		coapp_race = input(co_applicant_race_1, best32.);
		coapp_sex = input(co_applicant_sex, best32.);
		loan_amount = input(loan_amount_000s, best32.); *converts to numeric;
		min_pop = input(minority_population, best32.); *converts to numeric;
		lien = input(lien_status, best1.); *converts to numeric;
		loan_prps = input(loan_purpose, best1.); *converts to numeric;
		preapp = input(preapproval, best1.); *converts to numeric;
		county_code = put(input(cats(county_code),8.), z3.); *adds leading zeros;
	 	state_code = put(input(cats(state_code),8.), z2.); *adds leading zeros;
		comb_fips = catt(vvalue(state_code), vvalue(county_code)); *combines state and county fips;
		fips = input(comb_fips, best5.); *new numeric variable;
		app_income = 1000*(app_income); *initally rounded to nearest thousand;
		app_income = log(app_income); 
		loan_amount = 1000*(loan_amount); *initally rounded to nearest thousand;
		loan_amount = log(loan_amount);
	
	if co_applicant_ethnicity = 3 or co_applicant_ethnicity = 4 then delete;
	if co_applicant_race_1 = 6 or co_applicant_race_1 = 7 then delete;
	if co_applicant_sex = 3 or co_applicant_sex = 4 then delete;
	if co_applicant_ethnicity = 5 or co_applicant_race_1 = 8 then coapp = 0;
		else coapp = 1;

	if cmiss(app_income) then delete; *deletes rows with missing data ...;
	*if cmiss(denial) then delete;
	if cmiss(min_pop) then delete;
	if cmiss(fips) then delete;
run;
data econ.loan14_coapp (where = (race < 6 and action = 1 and ethnicity < 3 
							  or race < 6 and action = 3 and ethnicity < 3) 
	keep = year state action race app_income sex lien loan_prps preapp loan_amount min_pop fips 
		ethnicity coapp co_applicant_ethnicity coapp_eth co_applicant_race_1 coapp_race co_applicant_sex coapp_sex);
	set econ.hmda2014;
		race = input(applicant_race_1, best1.); *converts to numeric;
		year = input(as_of_year, best4.); *converts to numeric;
		action = input(action_taken, best1.); *converts to numeric;
 		app_income = input(applicant_income_000s, best32.); *converts to numeric;
		sex = input(applicant_sex, best1.); *converts to numeric;
		denial = input(denial_reason_1, best1.); *converts to numeric;
		ethnicity = input(applicant_ethnicity, best1.); *converts to numeric;
		coapp_eth = input(co_applicant_ethnicity, best32.);
		coapp_race = input(co_applicant_race_1, best32.);
		coapp_sex = input(co_applicant_sex, best32.);
		loan_amount = input(loan_amount_000s, best32.); *converts to numeric;
		min_pop = input(minority_population, best32.); *converts to numeric;
		lien = input(lien_status, best1.); *converts to numeric;
		loan_prps = input(loan_purpose, best1.); *converts to numeric;
		preapp = input(preapproval, best1.); *converts to numeric;
		county_code = put(input(cats(county_code),8.), z3.); *adds leading zeros;
	 	state_code = put(input(cats(state_code),8.), z2.); *adds leading zeros;
		comb_fips = catt(vvalue(state_code), vvalue(county_code)); *combines state and county fips;
		fips = input(comb_fips, best5.); *new numeric variable;
		app_income = 1000*(app_income); *initally rounded to nearest thousand;
		app_income = log(app_income); 
		loan_amount = 1000*(loan_amount); *initally rounded to nearest thousand;
		loan_amount = log(loan_amount);
	
	if co_applicant_ethnicity = 3 or co_applicant_ethnicity = 4 then delete;
	if co_applicant_race_1 = 6 or co_applicant_race_1 = 7 then delete;
	if co_applicant_sex = 3 or co_applicant_sex = 4 then delete;
	if co_applicant_ethnicity = 5 or co_applicant_race_1 = 8 then coapp = 0;
		else coapp = 1;

	if cmiss(app_income) then delete; *deletes rows with missing data ...;
	*if cmiss(denial) then delete;
	if cmiss(min_pop) then delete;
	if cmiss(fips) then delete;
run;
data econ.loan13_coapp (where = (race < 6 and action = 1 and ethnicity < 3 
							  or race < 6 and action = 3 and ethnicity < 3) 
	keep = year state action race app_income sex lien loan_prps preapp loan_amount min_pop fips 
		ethnicity coapp co_applicant_ethnicity coapp_eth co_applicant_race_1 coapp_race co_applicant_sex coapp_sex);
	set econ.hmda2013;
		race = input(applicant_race_1, best1.); *converts to numeric;
		year = input(as_of_year, best4.); *converts to numeric;
		action = input(action_taken, best1.); *converts to numeric;
 		app_income = input(applicant_income_000s, best32.); *converts to numeric;
		sex = input(applicant_sex, best1.); *converts to numeric;
		denial = input(denial_reason_1, best1.); *converts to numeric;
		ethnicity = input(applicant_ethnicity, best1.); *converts to numeric;
		coapp_eth = input(co_applicant_ethnicity, best32.);
		coapp_race = input(co_applicant_race_1, best32.);
		coapp_sex = input(co_applicant_sex, best32.);
		loan_amount = input(loan_amount_000s, best32.); *converts to numeric;
		min_pop = input(minority_population, best32.); *converts to numeric;
		lien = input(lien_status, best1.); *converts to numeric;
		loan_prps = input(loan_purpose, best1.); *converts to numeric;
		preapp = input(preapproval, best1.); *converts to numeric;
		county_code = put(input(cats(county_code),8.), z3.); *adds leading zeros;
	 	state_code = put(input(cats(state_code),8.), z2.); *adds leading zeros;
		comb_fips = catt(vvalue(state_code), vvalue(county_code)); *combines state and county fips;
		fips = input(comb_fips, best5.); *new numeric variable;
		app_income = 1000*(app_income); *initally rounded to nearest thousand;
		app_income = log(app_income); 
		loan_amount = 1000*(loan_amount); *initally rounded to nearest thousand;
		loan_amount = log(loan_amount);
	
	if co_applicant_ethnicity = 3 or co_applicant_ethnicity = 4 then delete;
	if co_applicant_race_1 = 6 or co_applicant_race_1 = 7 then delete;
	if co_applicant_sex = 3 or co_applicant_sex = 4 then delete;
	if co_applicant_ethnicity = 5 or co_applicant_race_1 = 8 then coapp = 0;
		else coapp = 1;

	if cmiss(app_income) then delete; *deletes rows with missing data ...;
	*if cmiss(denial) then delete;
	if cmiss(min_pop) then delete;
	if cmiss(fips) then delete;
run;
data econ.loan12_coapp (where = (race < 6 and action = 1 and ethnicity < 3 
							  or race < 6 and action = 3 and ethnicity < 3) 
	keep = year state action race app_income sex lien loan_prps preapp loan_amount min_pop fips 
		ethnicity coapp co_applicant_ethnicity coapp_eth co_applicant_race_1 coapp_race co_applicant_sex coapp_sex);
	set econ.hmda2012;
		race = input(applicant_race_1, best1.); *converts to numeric;
		year = input(as_of_year, best4.); *converts to numeric;
		action = input(action_taken, best1.); *converts to numeric;
 		app_income = input(applicant_income_000s, best32.); *converts to numeric;
		sex = input(applicant_sex, best1.); *converts to numeric;
		denial = input(denial_reason_1, best1.); *converts to numeric;
		ethnicity = input(applicant_ethnicity, best1.); *converts to numeric;
		coapp_eth = input(co_applicant_ethnicity, best32.);
		coapp_race = input(co_applicant_race_1, best32.);
		coapp_sex = input(co_applicant_sex, best32.);
		loan_amount = input(loan_amount_000s, best32.); *converts to numeric;
		min_pop = input(minority_population, best32.); *converts to numeric;
		lien = input(lien_status, best1.); *converts to numeric;
		loan_prps = input(loan_purpose, best1.); *converts to numeric;
		preapp = input(preapproval, best1.); *converts to numeric;
		county_code = put(input(cats(county_code),8.), z3.); *adds leading zeros;
	 	state_code = put(input(cats(state_code),8.), z2.); *adds leading zeros;
		comb_fips = catt(vvalue(state_code), vvalue(county_code)); *combines state and county fips;
		fips = input(comb_fips, best5.); *new numeric variable;
		app_income = 1000*(app_income); *initally rounded to nearest thousand;
		app_income = log(app_income); 
		loan_amount = 1000*(loan_amount); *initally rounded to nearest thousand;
		loan_amount = log(loan_amount);
	
	if co_applicant_ethnicity = 3 or co_applicant_ethnicity = 4 then delete;
	if co_applicant_race_1 = 6 or co_applicant_race_1 = 7 then delete;
	if co_applicant_sex = 3 or co_applicant_sex = 4 then delete;
	if co_applicant_ethnicity = 5 or co_applicant_race_1 = 8 then coapp = 0;
		else coapp = 1;

	if cmiss(app_income) then delete; *deletes rows with missing data ...;
	*if cmiss(denial) then delete;
	if cmiss(min_pop) then delete;
	if cmiss(fips) then delete;
run;
data econ.loan16_den_coapp (where = (race < 6 and action = 1 and ethnicity < 3 
							  or race < 6 and action = 3 and ethnicity < 3) 
	keep = year state action race app_income sex lien loan_prps preapp loan_amount min_pop fips 
			   ethnicity coapp_eth coapp coapp_race coapp_sex denial);
	set econ.hmda2016;
		race = input(applicant_race_1, best1.); *converts to numeric;
		year = input(as_of_year, best4.); *converts to numeric;
		action = input(action_taken, best1.); *converts to numeric;
 		app_income = input(applicant_income_000s, best32.); *converts to numeric;
		coapp_eth = input(co_applicant_ethnicity, best1.); *converts to numeric;
		coapp_race = input(co_applicant_race_1, best1.);
		coapp_sex = input(co_applicant_sex, best1.);
		sex = input(applicant_sex, best1.); *converts to numeric;
		denial = input(denial_reason_1, best1.); *converts to numeric;
		ethnicity = input(applicant_ethnicity, best1.); *converts to numeric;
		loan_amount = input(loan_amount_000s, best32.); *converts to numeric;
		min_pop = input(minority_population, best32.); *converts to numeric;
		lien = input(lien_status, best1.); *converts to numeric;
		loan_prps = input(loan_purpose, best1.); *converts to numeric;
		preapp = input(preapproval, best1.); *converts to numeric;
		county_code = put(input(cats(county_code),8.), z3.); *adds leading zeros;
	 	state_code = put(input(cats(state_code),8.), z2.); *adds leading zeros;
		comb_fips = catt(vvalue(state_code), vvalue(county_code)); *combines state and county fips;
		fips = input(comb_fips, best5.); *new numeric variable;
		app_income = 1000*(app_income); *initally rounded to nearest thousand;
		app_income = log(app_income); 
		loan_amount = 1000*(loan_amount); *initally rounded to nearest thousand;
		loan_amount = log(loan_amount);
	
	if coapp_eth = 3 or coapp_eth = 4 then delete;
	if coapp_race = 6 or coapp_race = 7 then delete;
	if coapp_sex = 3 or coapp_sex = 4 then delete;
	if coapp_eth = 5 or coapp_race = 8 then coapp = 0;
		else coapp = 1;
	if action = 1 then denial = 0;
	if cmiss(app_income) then delete; *deletes rows with missing data ...;
	if cmiss(denial) then delete;
	if cmiss(min_pop) then delete;
	if cmiss(fips) then delete;
run;
data econ.loan15_den_coapp (where = (race < 6 and action = 1 and ethnicity < 3 
							  or race < 6 and action = 3 and ethnicity < 3) 
	keep = year state action race app_income sex lien loan_prps preapp loan_amount min_pop fips 
			   ethnicity coapp_eth coapp coapp_race coapp_sex denial);
	set econ.hmda2015;
		race = input(applicant_race_1, best1.); *converts to numeric;
		year = input(as_of_year, best4.); *converts to numeric;
		action = input(action_taken, best1.); *converts to numeric;
 		app_income = input(applicant_income_000s, best32.); *converts to numeric;
		coapp_eth = input(co_applicant_ethnicity, best1.); *converts to numeric;
		coapp_race = input(co_applicant_race_1, best1.);
		coapp_sex = input(co_applicant_sex, best1.);
		sex = input(applicant_sex, best1.); *converts to numeric;
		denial = input(denial_reason_1, best1.); *converts to numeric;
		ethnicity = input(applicant_ethnicity, best1.); *converts to numeric;
		loan_amount = input(loan_amount_000s, best32.); *converts to numeric;
		min_pop = input(minority_population, best32.); *converts to numeric;
		lien = input(lien_status, best1.); *converts to numeric;
		loan_prps = input(loan_purpose, best1.); *converts to numeric;
		preapp = input(preapproval, best1.); *converts to numeric;
		county_code = put(input(cats(county_code),8.), z3.); *adds leading zeros;
	 	state_code = put(input(cats(state_code),8.), z2.); *adds leading zeros;
		comb_fips = catt(vvalue(state_code), vvalue(county_code)); *combines state and county fips;
		fips = input(comb_fips, best5.); *new numeric variable;
		app_income = 1000*(app_income); *initally rounded to nearest thousand;
		app_income = log(app_income); 
		loan_amount = 1000*(loan_amount); *initally rounded to nearest thousand;
		loan_amount = log(loan_amount);
	
	if coapp_eth = 3 or coapp_eth = 4 then delete;
	if coapp_race = 6 or coapp_race = 7 then delete;
	if coapp_sex = 3 or coapp_sex = 4 then delete;
	if coapp_eth = 5 or coapp_race = 8 then coapp = 0;
		else coapp = 1;
	if action = 1 then denial = 0;
	if cmiss(app_income) then delete; *deletes rows with missing data ...;
	if cmiss(denial) then delete;
	if cmiss(min_pop) then delete;
	if cmiss(fips) then delete;
run;
data econ.loan14_den_coapp (where = (race < 6 and action = 1 and ethnicity < 3 
							  or race < 6 and action = 3 and ethnicity < 3) 
	keep = year state action race app_income sex lien loan_prps preapp loan_amount min_pop fips 
			   ethnicity coapp_eth coapp coapp_race coapp_sex denial);
	set econ.hmda2014;
		race = input(applicant_race_1, best1.); *converts to numeric;
		year = input(as_of_year, best4.); *converts to numeric;
		action = input(action_taken, best1.); *converts to numeric;
 		app_income = input(applicant_income_000s, best32.); *converts to numeric;
		coapp_eth = input(co_applicant_ethnicity, best1.); *converts to numeric;
		coapp_race = input(co_applicant_race_1, best1.);
		coapp_sex = input(co_applicant_sex, best1.);
		sex = input(applicant_sex, best1.); *converts to numeric;
		denial = input(denial_reason_1, best1.); *converts to numeric;
		ethnicity = input(applicant_ethnicity, best1.); *converts to numeric;
		loan_amount = input(loan_amount_000s, best32.); *converts to numeric;
		min_pop = input(minority_population, best32.); *converts to numeric;
		lien = input(lien_status, best1.); *converts to numeric;
		loan_prps = input(loan_purpose, best1.); *converts to numeric;
		preapp = input(preapproval, best1.); *converts to numeric;
		county_code = put(input(cats(county_code),8.), z3.); *adds leading zeros;
	 	state_code = put(input(cats(state_code),8.), z2.); *adds leading zeros;
		comb_fips = catt(vvalue(state_code), vvalue(county_code)); *combines state and county fips;
		fips = input(comb_fips, best5.); *new numeric variable;
		app_income = 1000*(app_income); *initally rounded to nearest thousand;
		app_income = log(app_income); 
		loan_amount = 1000*(loan_amount); *initally rounded to nearest thousand;
		loan_amount = log(loan_amount);
	
	if coapp_eth = 3 or coapp_eth = 4 then delete;
	if coapp_race = 6 or coapp_race = 7 then delete;
	if coapp_sex = 3 or coapp_sex = 4 then delete;
	if coapp_eth = 5 or coapp_race = 8 then coapp = 0;
		else coapp = 1;
	if action = 1 then denial = 0;
	if cmiss(app_income) then delete; *deletes rows with missing data ...;
	if cmiss(denial) then delete;
	if cmiss(min_pop) then delete;
	if cmiss(fips) then delete;
run;
data econ.loan13_den_coapp (where = (race < 6 and action = 1 and ethnicity < 3 
							  or race < 6 and action = 3 and ethnicity < 3) 
	keep = year state action race app_income sex lien loan_prps preapp loan_amount min_pop fips 
			   ethnicity coapp_eth coapp coapp_race coapp_sex denial);
	set econ.hmda2013;
		race = input(applicant_race_1, best1.); *converts to numeric;
		year = input(as_of_year, best4.); *converts to numeric;
		action = input(action_taken, best1.); *converts to numeric;
 		app_income = input(applicant_income_000s, best32.); *converts to numeric;
		coapp_eth = input(co_applicant_ethnicity, best1.); *converts to numeric;
		coapp_race = input(co_applicant_race_1, best1.);
		coapp_sex = input(co_applicant_sex, best1.);
		sex = input(applicant_sex, best1.); *converts to numeric;
		denial = input(denial_reason_1, best1.); *converts to numeric;
		ethnicity = input(applicant_ethnicity, best1.); *converts to numeric;
		loan_amount = input(loan_amount_000s, best32.); *converts to numeric;
		min_pop = input(minority_population, best32.); *converts to numeric;
		lien = input(lien_status, best1.); *converts to numeric;
		loan_prps = input(loan_purpose, best1.); *converts to numeric;
		preapp = input(preapproval, best1.); *converts to numeric;
		county_code = put(input(cats(county_code),8.), z3.); *adds leading zeros;
	 	state_code = put(input(cats(state_code),8.), z2.); *adds leading zeros;
		comb_fips = catt(vvalue(state_code), vvalue(county_code)); *combines state and county fips;
		fips = input(comb_fips, best5.); *new numeric variable;
		app_income = 1000*(app_income); *initally rounded to nearest thousand;
		app_income = log(app_income); 
		loan_amount = 1000*(loan_amount); *initally rounded to nearest thousand;
		loan_amount = log(loan_amount);
	
	if coapp_eth = 3 or coapp_eth = 4 then delete;
	if coapp_race = 6 or coapp_race = 7 then delete;
	if coapp_sex = 3 or coapp_sex = 4 then delete;
	if coapp_eth = 5 or coapp_race = 8 then coapp = 0;
		else coapp = 1;
	if action = 1 then denial = 0;
	if cmiss(app_income) then delete; *deletes rows with missing data ...;
	if cmiss(denial) then delete;
	if cmiss(min_pop) then delete;
	if cmiss(fips) then delete;
run;
data econ.loan12_den_coapp (where = (race < 6 and action = 1 and ethnicity < 3 
							  or race < 6 and action = 3 and ethnicity < 3) 
	keep = year state action race app_income sex lien loan_prps preapp loan_amount min_pop fips 
			   ethnicity coapp_eth coapp coapp_race coapp_sex denial);
	set econ.hmda2012;
		race = input(applicant_race_1, best1.); *converts to numeric;
		year = input(as_of_year, best4.); *converts to numeric;
		action = input(action_taken, best1.); *converts to numeric;
 		app_income = input(applicant_income_000s, best32.); *converts to numeric;
		coapp_eth = input(co_applicant_ethnicity, best1.); *converts to numeric;
		coapp_race = input(co_applicant_race_1, best1.);
		coapp_sex = input(co_applicant_sex, best1.);
		sex = input(applicant_sex, best1.); *converts to numeric;
		denial = input(denial_reason_1, best1.); *converts to numeric;
		ethnicity = input(applicant_ethnicity, best1.); *converts to numeric;
		loan_amount = input(loan_amount_000s, best32.); *converts to numeric;
		min_pop = input(minority_population, best32.); *converts to numeric;
		lien = input(lien_status, best1.); *converts to numeric;
		loan_prps = input(loan_purpose, best1.); *converts to numeric;
		preapp = input(preapproval, best1.); *converts to numeric;
		county_code = put(input(cats(county_code),8.), z3.); *adds leading zeros;
	 	state_code = put(input(cats(state_code),8.), z2.); *adds leading zeros;
		comb_fips = catt(vvalue(state_code), vvalue(county_code)); *combines state and county fips;
		fips = input(comb_fips, best5.); *new numeric variable;
		app_income = 1000*(app_income); *initally rounded to nearest thousand;
		app_income = log(app_income); 
		loan_amount = 1000*(loan_amount); *initally rounded to nearest thousand;
		loan_amount = log(loan_amount);
	
	if coapp_eth = 3 or coapp_eth = 4 then delete;
	if coapp_race = 6 or coapp_race = 7 then delete;
	if coapp_sex = 3 or coapp_sex = 4 then delete;
	if coapp_eth = 5 or coapp_race = 8 then coapp = 0;
		else coapp = 1;
	if action = 1 then denial = 0;
	if cmiss(app_income) then delete; *deletes rows with missing data ...;
	if cmiss(denial) then delete;
	if cmiss(min_pop) then delete;
	if cmiss(fips) then delete;
run;
*This section creates data sets specifically for the Fixed-Effects Model;
data econ.panel16 (where = (race < 6 and action = 1 and ethnicity < 3 
							  or race < 6 and action = 3 and ethnicity < 3) 
	keep = year state action race ai a b na app_income sex lien loan_prps preapp loan_amount min_pop fips 
		ethnicity coapp co_applicant_ethnicity coapp_eth co_applicant_race_1 coapp_race co_applicant_sex coapp_sex);
	set econ.hmda2016;
		race = input(applicant_race_1, best1.); *converts to numeric;
		year = input(as_of_year, best4.); *converts to numeric;
		action = input(action_taken, best1.); *converts to numeric;
 		app_income = input(applicant_income_000s, best32.); *converts to numeric;
		sex = input(applicant_sex, best1.); *converts to numeric;
		denial = input(denial_reason_1, best1.); *converts to numeric;
		ethnicity = input(applicant_ethnicity, best1.); *converts to numeric;
		coapp_eth = input(co_applicant_ethnicity, best32.);
		coapp_race = input(co_applicant_race_1, best32.);
		coapp_sex = input(co_applicant_sex, best32.);
		loan_amount = input(loan_amount_000s, best32.); *converts to numeric;
		min_pop = input(minority_population, best32.); *converts to numeric;
		lien = input(lien_status, best1.); *converts to numeric;
		loan_prps = input(loan_purpose, best1.); *converts to numeric;
		preapp = input(preapproval, best1.); *converts to numeric;
		county_code = put(input(cats(county_code),8.), z3.); *adds leading zeros;
	 	state_code = put(input(cats(state_code),8.), z2.); *adds leading zeros;
		comb_fips = catt(vvalue(state_code), vvalue(county_code)); *combines state and county fips;
		fips = input(comb_fips, best5.); *new numeric variable;
		app_income = 1000*(app_income); *initally rounded to nearest thousand;
		app_income = log(app_income); 
		loan_amount = 1000*(loan_amount); *initally rounded to nearest thousand;
		loan_amount = log(loan_amount);
	
	if co_applicant_ethnicity = 3 or co_applicant_ethnicity = 4 then delete;
	if co_applicant_race_1 = 6 or co_applicant_race_1 = 7 then delete;
	if co_applicant_sex = 3 or co_applicant_sex = 4 then delete;
	if co_applicant_ethnicity = 5 or co_applicant_race_1 = 8 then coapp = 0;
		else coapp = 1;
	if race = 1 then ai = 1; else ai = 0;
	if race = 2 then a = 1; else a = 0;
	if race = 3 then b = 1; else b = 0;
	if race = 4 then na = 1; else na = 0;
	if cmiss(app_income) then delete; *deletes rows with missing data ...;
	*if cmiss(denial) then delete;
	if cmiss(min_pop) then delete;
	if cmiss(fips) then delete;
run;
data econ.panel15 (where = (race < 6 and action = 1 and ethnicity < 3 
							  or race < 6 and action = 3 and ethnicity < 3) 
	keep = year state action race ai a b na app_income sex lien loan_prps preapp loan_amount min_pop fips 
		ethnicity coapp co_applicant_ethnicity coapp_eth co_applicant_race_1 coapp_race co_applicant_sex coapp_sex);
	set econ.hmda2015;
		race = input(applicant_race_1, best1.); *converts to numeric;
		year = input(as_of_year, best4.); *converts to numeric;
		action = input(action_taken, best1.); *converts to numeric;
 		app_income = input(applicant_income_000s, best32.); *converts to numeric;
		sex = input(applicant_sex, best1.); *converts to numeric;
		denial = input(denial_reason_1, best1.); *converts to numeric;
		ethnicity = input(applicant_ethnicity, best1.); *converts to numeric;
		coapp_eth = input(co_applicant_ethnicity, best32.);
		coapp_race = input(co_applicant_race_1, best32.);
		coapp_sex = input(co_applicant_sex, best32.);
		loan_amount = input(loan_amount_000s, best32.); *converts to numeric;
		min_pop = input(minority_population, best32.); *converts to numeric;
		lien = input(lien_status, best1.); *converts to numeric;
		loan_prps = input(loan_purpose, best1.); *converts to numeric;
		preapp = input(preapproval, best1.); *converts to numeric;
		county_code = put(input(cats(county_code),8.), z3.); *adds leading zeros;
	 	state_code = put(input(cats(state_code),8.), z2.); *adds leading zeros;
		comb_fips = catt(vvalue(state_code), vvalue(county_code)); *combines state and county fips;
		fips = input(comb_fips, best5.); *new numeric variable;
		app_income = 1000*(app_income); *initally rounded to nearest thousand;
		app_income = log(app_income); 
		loan_amount = 1000*(loan_amount); *initally rounded to nearest thousand;
		loan_amount = log(loan_amount);
	
	if co_applicant_ethnicity = 3 or co_applicant_ethnicity = 4 then delete;
	if co_applicant_race_1 = 6 or co_applicant_race_1 = 7 then delete;
	if co_applicant_sex = 3 or co_applicant_sex = 4 then delete;
	if co_applicant_ethnicity = 5 or co_applicant_race_1 = 8 then coapp = 0;
		else coapp = 1;
	if race = 1 then ai = 1; else ai = 0;
	if race = 2 then a = 1; else a = 0;
	if race = 3 then b = 1; else b = 0;
	if race = 4 then na = 1; else na = 0;
	if cmiss(app_income) then delete; *deletes rows with missing data ...;
	*if cmiss(denial) then delete;
	if cmiss(min_pop) then delete;
	if cmiss(fips) then delete;
run;
data econ.panel14 (where = (race < 6 and action = 1 and ethnicity < 3 
							  or race < 6 and action = 3 and ethnicity < 3) 
	keep = year state action race ai a b na app_income sex lien loan_prps preapp loan_amount min_pop fips 
		ethnicity coapp co_applicant_ethnicity coapp_eth co_applicant_race_1 coapp_race co_applicant_sex coapp_sex);
	set econ.hmda2014;
		race = input(applicant_race_1, best1.); *converts to numeric;
		year = input(as_of_year, best4.); *converts to numeric;
		action = input(action_taken, best1.); *converts to numeric;
 		app_income = input(applicant_income_000s, best32.); *converts to numeric;
		sex = input(applicant_sex, best1.); *converts to numeric;
		denial = input(denial_reason_1, best1.); *converts to numeric;
		ethnicity = input(applicant_ethnicity, best1.); *converts to numeric;
		coapp_eth = input(co_applicant_ethnicity, best32.);
		coapp_race = input(co_applicant_race_1, best32.);
		coapp_sex = input(co_applicant_sex, best32.);
		loan_amount = input(loan_amount_000s, best32.); *converts to numeric;
		min_pop = input(minority_population, best32.); *converts to numeric;
		lien = input(lien_status, best1.); *converts to numeric;
		loan_prps = input(loan_purpose, best1.); *converts to numeric;
		preapp = input(preapproval, best1.); *converts to numeric;
		county_code = put(input(cats(county_code),8.), z3.); *adds leading zeros;
	 	state_code = put(input(cats(state_code),8.), z2.); *adds leading zeros;
		comb_fips = catt(vvalue(state_code), vvalue(county_code)); *combines state and county fips;
		fips = input(comb_fips, best5.); *new numeric variable;
		app_income = 1000*(app_income); *initally rounded to nearest thousand;
		app_income = log(app_income); 
		loan_amount = 1000*(loan_amount); *initally rounded to nearest thousand;
		loan_amount = log(loan_amount);
	
	if co_applicant_ethnicity = 3 or co_applicant_ethnicity = 4 then delete;
	if co_applicant_race_1 = 6 or co_applicant_race_1 = 7 then delete;
	if co_applicant_sex = 3 or co_applicant_sex = 4 then delete;
	if co_applicant_ethnicity = 5 or co_applicant_race_1 = 8 then coapp = 0;
		else coapp = 1;
	if race = 1 then ai = 1; else ai = 0;
	if race = 2 then a = 1; else a = 0;
	if race = 3 then b = 1; else b = 0;
	if race = 4 then na = 1; else na = 0;
	if cmiss(app_income) then delete; *deletes rows with missing data ...;
	*if cmiss(denial) then delete;
	if cmiss(min_pop) then delete;
	if cmiss(fips) then delete;
run;
data econ.panel13 (where = (race < 6 and action = 1 and ethnicity < 3 
							  or race < 6 and action = 3 and ethnicity < 3) 
	keep = year state action race ai a b na app_income sex lien loan_prps preapp loan_amount min_pop fips 
		ethnicity coapp co_applicant_ethnicity coapp_eth co_applicant_race_1 coapp_race co_applicant_sex coapp_sex);
	set econ.hmda2013;
		race = input(applicant_race_1, best1.); *converts to numeric;
		year = input(as_of_year, best4.); *converts to numeric;
		action = input(action_taken, best1.); *converts to numeric;
 		app_income = input(applicant_income_000s, best32.); *converts to numeric;
		sex = input(applicant_sex, best1.); *converts to numeric;
		denial = input(denial_reason_1, best1.); *converts to numeric;
		ethnicity = input(applicant_ethnicity, best1.); *converts to numeric;
		coapp_eth = input(co_applicant_ethnicity, best32.);
		coapp_race = input(co_applicant_race_1, best32.);
		coapp_sex = input(co_applicant_sex, best32.);
		loan_amount = input(loan_amount_000s, best32.); *converts to numeric;
		min_pop = input(minority_population, best32.); *converts to numeric;
		lien = input(lien_status, best1.); *converts to numeric;
		loan_prps = input(loan_purpose, best1.); *converts to numeric;
		preapp = input(preapproval, best1.); *converts to numeric;
		county_code = put(input(cats(county_code),8.), z3.); *adds leading zeros;
	 	state_code = put(input(cats(state_code),8.), z2.); *adds leading zeros;
		comb_fips = catt(vvalue(state_code), vvalue(county_code)); *combines state and county fips;
		fips = input(comb_fips, best5.); *new numeric variable;
		app_income = 1000*(app_income); *initally rounded to nearest thousand;
		app_income = log(app_income); 
		loan_amount = 1000*(loan_amount); *initally rounded to nearest thousand;
		loan_amount = log(loan_amount);
	
	if co_applicant_ethnicity = 3 or co_applicant_ethnicity = 4 then delete;
	if co_applicant_race_1 = 6 or co_applicant_race_1 = 7 then delete;
	if co_applicant_sex = 3 or co_applicant_sex = 4 then delete;
	if co_applicant_ethnicity = 5 or co_applicant_race_1 = 8 then coapp = 0;
		else coapp = 1;
	if race = 1 then ai = 1; else ai = 0;
	if race = 2 then a = 1; else a = 0;
	if race = 3 then b = 1; else b = 0;
	if race = 4 then na = 1; else na = 0;
	if cmiss(app_income) then delete; *deletes rows with missing data ...;
	*if cmiss(denial) then delete;
	if cmiss(min_pop) then delete;
	if cmiss(fips) then delete;
run;
data econ.panel12 (where = (race < 6 and action = 1 and ethnicity < 3 
							  or race < 6 and action = 3 and ethnicity < 3) 
	keep = year state action race ai a b na app_income sex lien loan_prps preapp loan_amount min_pop fips 
		ethnicity coapp co_applicant_ethnicity coapp_eth co_applicant_race_1 coapp_race co_applicant_sex coapp_sex);
	set econ.hmda2012;
		race = input(applicant_race_1, best1.); *converts to numeric;
		year = input(as_of_year, best4.); *converts to numeric;
		action = input(action_taken, best1.); *converts to numeric;
 		app_income = input(applicant_income_000s, best32.); *converts to numeric;
		sex = input(applicant_sex, best1.); *converts to numeric;
		denial = input(denial_reason_1, best1.); *converts to numeric;
		ethnicity = input(applicant_ethnicity, best1.); *converts to numeric;
		coapp_eth = input(co_applicant_ethnicity, best32.);
		coapp_race = input(co_applicant_race_1, best32.);
		coapp_sex = input(co_applicant_sex, best32.);
		loan_amount = input(loan_amount_000s, best32.); *converts to numeric;
		min_pop = input(minority_population, best32.); *converts to numeric;
		lien = input(lien_status, best1.); *converts to numeric;
		loan_prps = input(loan_purpose, best1.); *converts to numeric;
		preapp = input(preapproval, best1.); *converts to numeric;
		county_code = put(input(cats(county_code),8.), z3.); *adds leading zeros;
	 	state_code = put(input(cats(state_code),8.), z2.); *adds leading zeros;
		comb_fips = catt(vvalue(state_code), vvalue(county_code)); *combines state and county fips;
		fips = input(comb_fips, best5.); *new numeric variable;
		app_income = 1000*(app_income); *initally rounded to nearest thousand;
		app_income = log(app_income); 
		loan_amount = 1000*(loan_amount); *initally rounded to nearest thousand;
		loan_amount = log(loan_amount);
	
	if co_applicant_ethnicity = 3 or co_applicant_ethnicity = 4 then delete;
	if co_applicant_race_1 = 6 or co_applicant_race_1 = 7 then delete;
	if co_applicant_sex = 3 or co_applicant_sex = 4 then delete;
	if co_applicant_ethnicity = 5 or co_applicant_race_1 = 8 then coapp = 0;
		else coapp = 1;
	if race = 1 then ai = 1; else ai = 0;
	if race = 2 then a = 1; else a = 0;
	if race = 3 then b = 1; else b = 0;
	if race = 4 then na = 1; else na = 0;
	if cmiss(app_income) then delete; *deletes rows with missing data ...;
	*if cmiss(denial) then delete;
	if cmiss(min_pop) then delete;
	if cmiss(fips) then delete;
run;

data econ.elections (keep = year fips party); *Cleans Elections data;
	set econ.elections16;
	year = 2016;
	if per_dem > per_gop then party = 1;
	if per_dem < per_gop then party = 0;
	run;
proc sort data = econ.elections out = econ.elections; *Sorts;
	by year fips;
run;

data econ.loan; *Concatenates loan data for 2012 - 2016 into a loan slave file;
 	set econ.loan12 econ.loan13 econ.loan14 econ.loan15 econ.loan16;
run;
proc sort data = econ.loan out = econ.loan; *sorts;
	by year fips;
run;
data econ.loan_coapp; *Concatenates loan data with coapp info for 2012 - 2016 into a loan slave file;
 	set econ.loan12_coapp econ.loan13_coapp econ.loan14_coapp econ.loan15_coapp econ.loan16_coapp;
run;
proc sort data = econ.loan_coapp out = econ.loan_coapp; *sorts;
	by year fips;
run;
data econ.loan_den_coapp; *Concatenates loan data with coapp & denial info for 2012 - 2016 into a loan slave file;
 	set econ.loan12_den_coapp econ.loan13_den_coapp econ.loan14_den_coapp econ.loan15_den_coapp econ.loan16_den_coapp;
run;
proc sort data = econ.loan_den_coapp out = econ.loan_den_coapp; *sorts;
	by year fips;
run;
data econ.panel; *Concatenates Panel data into slave file;
 	set econ.panel16 econ.panel15 econ.panel14 econ.panel13 econ.panel12;
run;
proc sort data = econ.panel out = econ.panel; *sorts;
	by year fips;
run;
data econ.acs; *Concatenates veteran data for 2012 - 2016 into a veteran slave file;
 	set econ.acs12 econ.acs13 econ.acs14 econ.acs15 econ.acs16;
run;
proc sort data = econ.acs out = econ.acs; *sorts;
	by year fips;
run;
data econ.va; *Concatenates va loan limit data data for 2012 - 2016 into a va loan limit slave file;
 	set econ.va12 econ.va13 econ.va14 econ.va15 econ.va16;
run;
proc sort data = econ.va out = econ.va; *sorts;
	by year fips;
run;
data econ.unemp; *Concatenates unemployment data for 2012 - 2016 into an unemployment slave file;
 	set econ.unemp12 econ.unemp13 econ.unemp14 econ.unemp15 econ.unemp16;
run;
proc sort data = econ.unemp out = econ.unemp; *sorts;
	by year fips;
run;
data econ.masterloan; *Merges all four slave files into a master file;
	merge econ.loan econ.acs econ.unemp econ.race;
	by year fips;
	*if cmiss(of _all_) then delete; *deletes rows with missing data;
run;
data econ.masterloan_coapp (drop = m_18_34 m_35_54 m_55_64 m_65_74 m_75_over f_18_34 f_35_54 f_55_64 f_65_74 
							f_75_over); *Merges all four slave files into a master file;
	merge econ.loan_coapp econ.acs econ.unemp econ.race econ.va;
	by year fips;
	if nmiss(of _numeric_) > 0 then delete; *deletes rows with missing data;
run;
data econ.masterloan_den_coapp; *Merges all four slave files into a master file;
	merge econ.loan_den_coapp econ.acs econ.unemp econ.race;
	by year fips;
	*if cmiss(of _all_) then delete; *deletes rows with missing data;
run;
data econ.master2016 (where = (year = 2016)); *Merges all four slave files into a master file for 2016;
	merge econ.loan_coapp econ.acs econ.unemp econ.race econ.elections econ.va;
	by year fips;
	if cmiss(of _all_) then delete; *deletes rows with missing data;
run;  
data econ.masterloan_coapp1 (drop = m_18_34 m_35_54 m_55_64 m_65_74 m_75_over f_18_34 f_35_54 f_55_64 f_65_74 
							f_75_over); *Merges all four slave files into a master file;
	merge econ.loan_coapp econ.acs econ.unemp econ.race econ.va;
	by year fips;
	if nmiss(of _numeric_) > 0 then delete; *deletes rows with missing data;
	if action = 3 then response = 0;
		else response = 1;
run;
data econ.masterloan_coapp_noprps (drop = m_18_34 m_35_54 m_55_64 m_65_74 m_75_over f_18_34 f_35_54 f_55_64 f_65_74 
							f_75_over); *Merges all four slave files into a master file;
	merge econ.loan_coapp econ.acs econ.unemp econ.race econ.va;
	by year fips;
	if nmiss(of _numeric_) > 0 then delete; *deletes rows with missing data;
	if action = 3 then response = 0;
		else response = 1;
	if loan_prps = 2 or loan_prps = 3 then delete;
	if loan_amount > 18 then delete; *deletes outliers;
run;
data econ.master_panel (drop = m_18_34 m_35_54 m_55_64 m_65_74 m_75_over f_18_34 f_35_54 f_55_64 f_65_74 
							f_75_over); *Merges all four slave files into a master file;
	merge econ.panel econ.acs econ.unemp econ.race econ.va;
	by year fips;
	if nmiss(of _numeric_) > 0 then delete; *deletes rows with missing data;
	if action = 3 then response = 0;
		else response = 1;
	if ethnicity = 1 then eth = 1; else eth = 0;
	*if loan_prps = 2 or loan_prps = 3 then delete;
	if loan_prps = 1 then purchase = 1; else purchase = 0;
	if loan_prps = 2 then improv = 1; else improv = 0;
	if lien = 1 then firstlien = 1; else firstlien = 0;
	if lien = 2 then secondlien = 1; else secondlien = 0;
	if loan_amount > 18 then delete; *deletes outliers;
run;
*This section creates the regression models;
proc glmselect data = econ.masterloan_coapp_noprps; *GLM;
	class race state year ethnicity lien sex/param=ref;
	model loan_amount = race state year app_income sex ethnicity min_pop coapp lien
	m_vet f_vet wa_m wa_f ba_m ba_f ia_m ia_f aa_m aa_f na_m na_f unemployment_rate loan_limit/ selection=none stats = all;
	ods select parameterestimates FitStatistics;
	ods output parameterestimates=econ.glmparms;
quit;
proc glmselect data = econ.masterloan_coapp_noprps; *GLM with interatcion;
	class state race year ethnicity lien sex/param=ref;
	model loan_amount = state*race state*ethnicity state race year app_income sex ethnicity min_pop lien coapp
	m_vet f_vet wa_m wa_f ba_m ba_f ia_m ia_f aa_m aa_f na_m na_f unemployment_rate loan_limit/ selection=none stats = all;
	ods select parameterestimates FitStatistics;
	ods output parameterestimates=econ.glmparms_int;
quit;
proc glm data = econ.master_panel; *Fixed-Effects;
	absorb fips year;
	model loan_amount = ai a b na app_income sex min_pop coapp fips year eth purchase improv firstlien secondlien
	m_vet f_vet wa_m wa_f ba_m ba_f ia_m ia_f aa_m aa_f na_m na_f unemployment_rate loan_limit / noint;
	*ods select parameterestimates FitStatistics;
	ods output parameterestimates=econ.panelparms;
run;
*Exports data in .CSV;
proc export 
  data = econ.glmparms
  dbms = csv 
  outfile = "C:\Users\User\Documents\TexasA&M Courses\Fall2017\ECON 675\Data\SAS\GLM Summary.csv" 
  replace;
run;
proc export 
  data = econ.glmparms_int
  dbms = csv 
  outfile = "C:\Users\User\Documents\TexasA&M Courses\Fall2017\ECON 675\Data\SAS\GLM_Int Summary.csv" 
  replace;
run;
proc export 
  data = econ.panelparms
  dbms = csv 
  outfile = "C:\Users\User\Documents\TexasA&M Courses\Fall2017\ECON 675\Data\SAS\Panel Summary.csv" 
  replace;
run;
data econ.logplots (rename = (loan_amount = LoanAmount)); *Cleans data for plots;
	set econ.masterloan_coapp1;
	length ApplicantRace LoanOutcome ApplicantEthnicity $50;
	if race = 1 then ApplicantRace = "American-Indian";
	if race = 2 then ApplicantRace = "Asian";
	if race = 3 then ApplicantRace = "African-American";
	if race = 4 then ApplicantRace = "Native Hawaiian";
	if race = 5 then ApplicantRace = "White";
	if ethnicity = 1 then ApplicantEthnicity = "Hispanic or Latino";
		else ApplicantEthnicity = "Not Hispanic or Latino";
	if response = 1 then LoanOutcome = "Loan Originated";
		else LoanOutcome = "Loan Denied";
run;
proc sgplot data = econ.logplots; *Histogram for Race by Loan Outcomes;
TITLE 'Histogram of Race by Loan Outcomes';
vbar ApplicantRace / group = LoanOutcome grouporder = ascending groupdisplay = cluster; 
yaxis labelpos = TOP ranges = (0 - 400000 1200000 - 1350000);
run;
proc sgplot data = econ.logplots; *Histogram for Ethnicity by Loan Outcomes;
TITLE 'Histogram of Ethnicity by Loan Outcomes';
vbar ApplicantEthnicity/ group = LoanOutcome grouporder = ascending groupdisplay = cluster; 
yaxis labelpos = TOP ranges = (0 - 500000 1200000 - 1500000);
run; 
proc sgplot data = econ.logplots; *Box Plot of Loan Amount vs. Applicant's Race;
TITLE 'Box Plot of Loan Amount vs. Applicant''s Race';  
vbox LoanAmount / group = ApplicantRace grouporder = ascending; 
yaxis labelpos = TOP label = 'ln(Loan Amount)';
run;
proc sgplot data = econ.logplots; *Box Plot of Loan Amount vs. Applicant's Ethnicity;
TITLE 'Box Plot of Loan Amount vs. Applicant''s Ethnicity';  
vbox LoanAmount / group = ApplicantEthnicity grouporder = ascending; 
yaxis labelpos = TOP label = 'ln(Loan Amount)';
run;
quit; 


proc means data=outme n mean;
      var Meff_P2_race_1 Meff_P2_race_2 Meff_P2_race_3 Meff_P2_race_4;
      title 'Average of the Individual Marginal Effects';
   run;
quit;


proc logistic data = econ.masterloan_coapp1 desc; *Logistic;
	class state race year sex ethnicity lien loan_prps/ param = ref;
	model response = state race year app_income sex ethnicity loan_amount min_pop loan_amount lien loan_prps
	coapp m_vet f_vet wa_m wa_f ba_m ba_f ia_m ia_f aa_m aa_f na_m na_f unemployment_rate loan_limit/lackfit rsquare;
	ods output parameterestimates=econ.logparms;
	output out = econ.logout xbeta = xb;
run;
proc export data = econ.logparms 
  dbms = csv 
  outfile = "C:\Users\User\Documents\TexasA&M Courses\Fall2017\ECON 675\Data\SAS\LOG Summary.csv" 
  replace;
run;
proc logistic data = econ.masterloan_coapp1 desc; *Logistic with Interaction;
	class state race year sex ethnicity/ param = ref;
	model response = state*race state race year app_income sex ethnicity loan_amount min_pop loan_amount 
	coapp m_vet f_vet wa_m wa_f ba_m ba_f ia_m ia_f aa_m aa_f na_m na_f unemployment_rate loan_limit/lackfit rsquare;
	ods output parameterestimates=econ.logparms_int;
	output out = econ.logout_int xbeta = xb;
run;
data econ.logparms (keep = parm estimate); *Calculates Marginal Effects for the Logistic Model;
set econ.logparms;
parm = CATT(OF variable ClassVal0);
run;
data econ.mef_logout;
  set econ.logout;
  margin_race1 = exp(xb) / ((1 + exp(xb)) ** 2) * (-0.6453);
  margin_race2 = exp(xb) / ((1 + exp(xb)) ** 2) * (-0.2699);
  margin_race3 = exp(xb) / ((1 + exp(xb)) ** 2) * (-0.5785);
  margin_race4 = exp(xb) / ((1 + exp(xb)) ** 2) * (-0.4050);
  *margin_year2012 = exp(xb) / ((1 + exp(xb)) ** 2) * (0.0836);
  *margin_year2013 = exp(xb) / ((1 + exp(xb)) ** 2) * (0.0446);
  *margin_year2014 = exp(xb) / ((1 + exp(xb)) ** 2) * (0.00835);
  *margin_year2015 = exp(xb) / ((1 + exp(xb)) ** 2) * (0.0678);
  *margin_app_income = exp(xb) / ((1 + exp(xb)) ** 2) * (0.6013);
  *margin_sex = exp(xb) / ((1 + exp(xb)) ** 2) * (0.0788);
  margin_ethnicity1 = exp(xb) / ((1 + exp(xb)) ** 2) * (-0.1683);
  *margin_loan_amount = exp(xb) / ((1 + exp(xb)) ** 2) * (-0.0699);
  margin_min_pop = exp(xb) / ((1 + exp(xb)) ** 2) * (-0.00348);
  *margin_lien1 = exp(xb) / ((1 + exp(xb)) ** 2) * (-0.2198);
  *margin_lien2 = exp(xb) / ((1 + exp(xb)) ** 2) * (-1.6342);
  *margin_loan_prps1 = exp(xb) / ((1 + exp(xb)) ** 2) * (1.6321);
  *margin_loan_prps2 = exp(xb) / ((1 + exp(xb)) ** 2) * (0.5703);
  *margin_coapp = exp(xb) / ((1 + exp(xb)) ** 2) * (0.1750);
  margin_m_vet = exp(xb) / ((1 + exp(xb)) ** 2) * (0.000068);
  margin_f_vet = exp(xb) / ((1 + exp(xb)) ** 2) * (0.1033);
  margin_WA_MALE = exp(xb) / ((1 + exp(xb)) ** 2) * (0.6415);
  margin_WA_FEMALE = exp(xb) / ((1 + exp(xb)) ** 2) * (-0.7316);
  margin_BA_MALE = exp(xb) / ((1 + exp(xb)) ** 2) * (-0.00648);
  margin_BA_FEMALE = exp(xb) / ((1 + exp(xb)) ** 2) * (-0.0335);
  margin_IA_MALE = exp(xb) / ((1 + exp(xb)) ** 2) * (-0.1975);
  margin_IA_FEMALE = exp(xb) / ((1 + exp(xb)) ** 2) *  (0.1428);
  margin_AA_MALE = exp(xb) / ((1 + exp(xb)) ** 2) * (-0.3004);
  margin_AA_FEMALE = exp(xb) / ((1 + exp(xb)) ** 2) * (0.3553);
  margin_NA_MALE = exp(xb) / ((1 + exp(xb)) ** 2) * (0.0437);
  margin_NA_FEMALE = exp(xb) / ((1 + exp(xb)) ** 2) * (0.00380);
  *margin_Unemployment_Rate = exp(xb) / ((1 + exp(xb)) ** 2) *(-0.0215);
  *margin_loan_limit = exp(xb) / ((1 + exp(xb)) ** 2) *(-0.3651);
run;
proc means data = econ.mef_logout mean;
	var _numeric_; 
	output out = econ.me_logout;
run;
proc transpose data = econ.me_logout out = econ.me_logout_trans (keep = _name_ col4);
run;
proc export 
  data = econ.me_logout_trans
  dbms = csv 
  outfile = "C:\Users\User\Documents\TexasA&M Courses\Fall2017\ECON 675\Data\SAS\MEF LOGout.csv" 
  replace;
run;


