# MMM_v.3.8
Multisectoral Micro-Macro model Version 3.8 (Finance-Augmented+Government)

## What's new?

Introduction of Complex Governement
* Four Types of government expenses composition.
* Four types of taxation structure.
* Two(Three) types of fiscal rules.

Introduction of Gini Index for Analysis

For more information on previous versions: <https://thttnn.github.io/MMM_CORE/>

### GOVERNMENT EXPENSES:
**Control Parameter**: "switch_government_composition"

Determines the composition and priority of government expenses, and initial distribution

* 0--> Government Wages(100%) [Only Public Workers]
* 1--> Government Wages(100%) + Unemployment Benefits(0%) [Public Workers and Unemployment Benefits]
*	2--> Government Wages(70%) + Unemployment Benefits(0%) + Government Consumption, Investment and Intermediate Demand(10% each) [Public Workers, Unemployment Benefits, and Demand to Sectors]

**Other Relevant Parameters** (to be subjected to sensitivity):
* "government_productivity_passtrought": determines how desired goverment wages grow based on average productivity of the economy
* "government_demand_growth": determined desired real growth rate of government demand (consumption, investment and inputs)
* "government_benefit": determines the share of average wage to be paid as unemployment benefits
* "switch_unemployment_benefits": determines how unemployment benefits are distributed
  * distributed by wage shares
  * distributed to lowest income class only

### TAXATION STRUCTURE:
**Control Parameter**: "taxation_structure" 

Determines which types of taxes will be used

* 0--> Only Wages
* 1--> Wages and Profits
* 2--> Wages, Profits and Interest
* 3--> Wages, Profits, Interest and Wealth

**Other Relevant Parameters** (to be subjected to sensitivity):
* "class_direct_tax": determines the tax rate on income, used in cases 1, 2 and 3
* "class_wealth_tax": determines the tax rate on wealth, used in case 4

### FISCAL RULES:
**Control Parameters**:
* "begin_surplus_target_rule": determines WHEN the surplus target rule starts (-1 if inactive)
* "begin_expenses_ceiling_rule": determines WHEN the expenses ceiling rule starts (-1 if inactive)
	
**Other Relevant Parameters** (to be subjected to sensitivity):
* "government_surplus_rate_target": initial government surplus target
* "government_surplus_target_adjustment": marginal increase in surplus target if it is adjusted based on debt-to-GDP (0, if not adjusted)
* "government_max_debt": maximum accepted debt-to-GDP if surplus target is adjusted
* "government_min_debt": minimum accepted debt-to-GDP if surplus target is adjusted

### SOME CONFIGURATIONS:

Sim1: 

* "begin_surplus_target_rule"        = -1 
* "begin_expenses_ceiling_rule"      = -1
* "taxation_structure"               = 1
* "switch_government_composition"    = 0

Sim2: 

* "begin_surplus_target_rule"        = -1 
* "begin_expenses_ceiling_rule"      = -1
* "taxation_structure"               = 1
* "switch_government_composition"    = 1

Sim3: 

* "begin_surplus_target_rule"        = 100
* "begin_expenses_ceiling_rule"      = -1
* "taxation_structure"               = 1
* "switch_government_composition"    = 1

Sim4: 

* "begin_surplus_target_rule"        = -1 
* "begin_expenses_ceiling_rule"      = 100
* "taxation_structure"               = 1
* "switch_government_composition"    = 1

Sim5: 

* "begin_surplus_target_rule"        = 100
* "begin_expenses_ceiling_rule"      = 100
* "taxation_structure"               = 1
* "switch_government_composition"    = 1
