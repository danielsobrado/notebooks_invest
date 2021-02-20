# Stock Market Notebooks

## Data Sources

### Investpy

[Investpy](https://github.com/alvarobartt/investpy) is a Python package to retrieve data from Investing.com

Install it via pip with a Python3.5 version or higher:

``$ pip install investpy``

### Kaggle

#### Huge Stock Market Dataset

[Huge Stock Market Dataset](https://www.kaggle.com/borismarjanovic/price-volume-data-for-all-us-stocks-etfs)  full historical daily price and volume data for all US-based stocks and ETFs trading on the NYSE, NASDAQ, and NYSE MKT.

The data (last updated 11/10/2017) is presented in CSV format as follows: Date, Open, High, Low, Close, Volume, OpenInt. Note that prices have been adjusted for dividends and splits.

#### Financials as Reported 2010-2020 - SEC Filings

Source: [Finnhub - Financials Reported](https://finnhub.io/docs/api#financials-reported)

[reported-financials](https://www.kaggle.com/finnhub/reported-financials) The data is cleaned and sourced directly from SEC filings from 2010-2020.

#### SEC Filings 1994-2020

Source: [Finnhub - Filings](https://finnhub.io/docs/api#filings)

[SEC Filings 1994-2020](https://www.kaggle.com/finnhub/sec-filings)  The data is cleaned and sourced directly from SEC filings from 1994-2020.

#### S&P 500 futures tick data (SP)

Source: [Finnhub](https://finnhub.io/)

[S&P 500 futures tick data](https://www.kaggle.com/finnhub/sp-500-futures-tick-data-sp)  S&P futures tick dataset from 2000-2019.

#### Historical stock data for all current S&P 500 companies

Historical stock prices (last 5 years) for all companies currently found on the S&P 500 index.

The script I used to acquire all of these .csv files can be found in this [GitHub repository] (https://github.com/CNuge/kaggle-code/tree/master/stock_data)

[Historical stock data for all current S&P 500 companies] (https://www.kaggle.com/camnugent/sandp500) The data from The Investor's Exchange api.

#### Data Scrapping

* [FinViz](https://finviz.com/)
    * Scrap with: [FinViz Finance](https://github.com/lit26/finvizfinance)
        * ``pip install finvizfinance``
        * Sample Notebook: 

## Statistics

## Sentiment

## Insiders

### Webs

* [Sec Api](https://sec-api.io/)
    * Sample Notebook: 
* [Insider Monitor](https://www.insider-monitor.com/)
    * Sample Notebook: 

### SEC filing types: 

DEF 14A: Definitive proxy statement: Form DEF 14A outlines the list of items up for vote by shareholders, such as the hiring of new directors or other business decisions
PRE 14A: Preliminary proxy statement: Form PRE 14A discloses all relevant details related to the issues being put forward for a shareholder vote
SC 13D: When a person or group acquires 5% or more of a company's shares, they must report it to the Securities and Exchange Commission
SC 13D/A: When a person or group acquires 5% or more of a company's shares, they must report it to the Securities and Exchange Commission
SC 13G: Form 13G is used to report a party's ownership of stock which exceeds 5% of a company's total stock issue
SC 13G/A: Form 13G is used to report a party's ownership of stock which exceeds 5% of a company's total stock issue
1: Application for registration or exemption from registration as a national securities exchange
1-A: Regulation A Offering Statement
1-E: Notification under Regulation E
1-K: Annual Reports and Special Financial Reports
1-N: Form and amendments for notice of registration as a national securities exchange for the sole purpose of trading security futures products
1-SA: Semiannual Report or Special Financial Report Pursuant to Regulation A
1-U: Current Report Pursuant to Regulation A
1-Z: Exit Report Under Regulation A
10: General form for registration of securities pursuant to Section 12(b) or (g)
10-D: Asset-Backed Issuer Distribution Report Pursuant to Section 13 or 15(d) of the Securities Exchange Act of 1934
10-K: Annual report pursuant to Section 13 or 15(d)
10-M: Irrevocable Appointment of Agent for Service of Process, Pleadings and Other Papers by Non-Resident General Partner of Broker or Dealer
10-Q: General form for quarterly reports under Section 13 or 15(d)
11-K: Annual reports of employee stock purchase, savings and similar plans pursuant to Section 15(d)
12b-25: Notification of late filing
13F: Information required of institutional investment managers pursuant to Section 13(f)
13H: Information Required of Large Traders Pursuant To Section 13(h) of the Securities Exchange Act of 1934
144: Notice of proposed sale of securities pursuant to Rule 144
15: Certification and notice of termination of registration under Section 12(g) or suspension of duty to file reports under Sections 13 and 15(d)
15F: Certification of a foreign private issuer's termination of registration of a class of securities under Section 12(g) or its termination of the duty to file reports under Section 13(a) or Section 15(d)
17-H: Risk Assessment for Brokers and Dealers
18: Application for registration pursuant to Section 12(b) and (c) of the Securities Exchange Act of 1934
18-K: Annual report for foreign governments and political subdivisions thereof
19b-4: Proposed rule change by self-regulatory organization
19b-4(e): Information required of a self-regulatory organization listing and trading a new derivative securities product pursuant to Rule 19b-4(e) under the Securities Exchange Act of 1934
19b-7: Proposed rule change by self-regulatory organization
2-E: Report of sales pursuant to Rule 609 of Regulation E
20-F: Registration statement / Annual report / Transition report
24F-2: Annual notice of securities sold pursuant to Rule 24-f2
25: Notification of the removal from listing and registration of matured, redeemed or retired securities
3: Initial statement of beneficial ownership of securities
4: Statement of changes in beneficial ownership of securities
40-F: Registration statement pursuant to Section 12 or annual report pursuant to Section 13(a) or 15(d)
5: Annual statement of changes in beneficial ownership of securities
6-K: Report of foreign private issuer pursuant to Rule 13a-16 or 15d-16 under the Securities Exchange Act of 1934
7-M: Irrevocable Appointment of Agent for Service of Process, Pleadings and Other Papers by Individual Non-Resident Broker or Dealer
8-A: Registration of certain classes of securities pursuant to Section 12(b) or (g)
8-K: Current report pursuant to Section 13 or 15(d)
8-M: Irrevocable Appointment of Agent for Service of Process, Pleadings and Other Papers by Corporate Non-Resident Broker or Dealer
9-M: Irrevocable Appointment of Agent for Service of Process, Pleadings and Other Papers by Partnership Non-Resident Broker or Dealer
ABS DD-15E: Certification of Provider of Third-Party Due Diligence Services for Asset-Backed Securities
ABS-15G: Asset-Backed Securitizer Report
ABS-EE: Form for Submission of Electronic Exhibits for Asset-Backed Securities
ADV: Uniform Application for Investment Adviser Registration and Report by Exempt Reporting Advisers
ADV-E: Certificate of accounting of client securities and funds in the possession or custody of an investment adviser
ADV-H: Application for a temporary or continuing hardship exemption
ADV-NR: Appointment of agent for service of process by non-resident general partner and non-resident managing agent of an investment adviser
ADV-W: Notice of withdrawal from registration as investment adviser
ATS: Initial operation report, amendment to initial operation report and cessation of operations report for alternative trading systems
ATS-N: NMS Stock Alternative Trading Systems
ATS-R: Quarterly report of alternative trading systems activities
BD: Uniform application for broker-dealer registration
BD-N: Notice of registration as a broker-dealer for the purpose of trading security futures products pursuant to Section 15(b)(11) of the Securities Exchange Act of 1934
BDW: Uniform request for broker-dealer withdrawal
C: Form C
CA-1: Registration or exemption from registration as a clearing agency and for amendment to registration
CB: Tender offer/rights offering notification form
CFPORTAL: Application or Amendment to Application for Registration or Withdrawal from Registration as Funding Portal Under the Securities Exchange Act of 1934
CUSTODY: Form Custody for Broker-Dealers
D: Notice of Exempt Offering of Securities
F-1: Registration statement for securities of certain foreign private issuers
F-10: Registration statement for securities of certain Canadian issuers
F-3: Registration statement for securities of certain foreign private issuers
F-4: Registration statement for securities of certain foreign private issuers issued in certain business combination transactions
F-6: Registration statement under the Securities Act of 1933 for depositary shares evidenced by American depositary receipts
F-7: Registration statement under the Securities Act of 1933 for securities of certain Canadian issuers offered for cash upon the exercise of rights granted to existing security holders
F-8: Registration statement under the Securities Act of 1933 for securities of certain Canadian issuers to be issued in exchange offers or a business combination
F-80: Registration statement for securities of certain Canadian issuers to be issued in exchange offers or a business combination
F-N: Appointment of agent for service of process by foreign banks and foreign insurance companies
F-X: Appointment of agent for service of process and undertaking
ID: Uniform application for access codes to file on EDGAR
MA: Application for Municipal Advisor Registration; Annual Update of Municipal Advisor Registration; and Amendment of a Prior Application for Registration
MA: Instructions for the Form MA Series
MA-I: Information Regarding Natural Persons who Engage in Municipal Advisory Activities
MA-NR: Designation of U.S. Agent for Service of Process for Non-Residents
MA-W: Notice of Withdrawal from Registration as a Municipal Advisor
MSD: Application for registration as a municipal securities dealer or amendment to such application
MSDW: Notice of withdrawal from registration as a municipal securities dealer
N-14: Form for the registration of securities issued in business combination transactions by investment companies and business development companies
N-17D-1: Report filed by small business investment company (SBIC)
N-17f-1: Certificate of accounting of securities and similar investments of a management investment company in the custody of members of national securities exchanges
N-17f-2: Certificate of accounting of securities and similar investments in the custody of management investment companies
N-18f-1: Notification of election pursuant to Rule 18f-1 under the Investment Company Act of 1940
N-1A: Registration form for open-end management investment companies
N-2: Registration statement for closed-end management investment companies
N-23c-3: Notification of repurchase offer
N-27D-1: Accounting of Segregated Trust Account
N-3: Registration statement of separate accounts organized as management investment companies
N-4: Registration statement of separate accounts organized as unit investment trusts
N-5: Registration statement of small business investment company
N-54A: Notification of election to be subject to Sections 55-65 of the Investment Company Act of 1940
N-54C: Notification of withdrawal of election to be subject to Sections 55-65 of the Investment Company Act of 1940
N-6: Registration statement for separate accounts organized as unit investment trusts that offer variable life insurance policies
N-6EI-1: Notification of claim of exemption pursuant to Rule 6e-2 or 6e-3(T) under the Investment Company Act of 1940
N-6F: Notice of intent to elect to be subject to Sections 55-65 of the Investment Company Act of 1940
N-8A: Notification of registration filed pursuant to Section 8(a) of Investment Company Act of 1940
N-8B-2: Registration statement of unit investment trusts which are currently issuing securities
N-8B-4: Registration statement of face-amount certificate companies
N-8F: Application for deregistration of certain registered investment companies
N-CEN: Annual Report for Registered Investment Companies
N-CR: Current Report, Money Market Fund Material Events
N-CSR: Certified shareholder report of registered management investment companies
N-LIQUID: Current Report Open-End Management Investment Company Liquidity
N-MFP: Monthly Schedule of Portfolio Holdings of Money Market Funds
N-PORT: Monthly Portfolio Investments Report
N-PX: Annual Report of Proxy Voting Record of Registered Management Investment Company
N-Q: Quarterly Schedule of Portfolio Holdings of Registered Management Investment Company
NRSRO: Form NRSRO - April 2009 Instructions
PF: Reporting Form for Investment Advisers to Private Funds and Certain Commodity Pool Operators and Commodity Trading Advisors
PILOT: Initial operation report, amendment to initial operation report and quarterly report for pilot trading systems operated by self-regulatory organizations
R31: Form for Reporting Covered Sales and Covered Round Turn Transactions Under Section 31 of the Securities Exchange Act of 1934
S-1: Registration statement under Securities Act of 1933
S-11: Registration of securities of certain real estate companies
S-20: Registration statement under the Securities Act of 1933
S-3: Registration statement under Securities Act of 1933
S-4: Registration statement under Securities Act of 1933
S-6: Registration under 1933 act of securities of unit investment trusts registered on form N-8B-2
S-8: Registration statement under Securities Act of 1933 to be offered to employees pursuant to certain plans
S-8 POS: Registration statement under Securities Act of 1933 to be offered to employees pursuant to certain plans
SBSE: Application for Registration of Security-based Swap Dealers and Major Security-based Swap Participants
SBSE-A: Application for Registration of Security-based Swap Dealers and Major Security-based Swap Participants that are Registered or Registering with the Commodity Futures Trading Commission as a Swap Dealer
SBSE-BD: Application for Registration of Security-based Swap Dealers and Major Security-based Swap Participants that are Registered Broker-dealers
SBSE-C: Certifications for Registration of Security-based Swap Dealers and Major Security-based Swap Participants
SBSE-W: Request for Withdrawal from Registration as a Security-based Swap Dealer or Major Security-based Swap Participant
SCI: Systems Compliance and Integrity
SD: Specialized Disclosure Report
SDR: Application or Amendment to Application for Registration or Withdrawal from Registration As Security-Based Swap Data Repository Under the Securities Exchange Act of 1934
SE: Submission of Paper Format Exhibits by Electronic Filers
SF-1: Registration Statement Under the Securities Act of 1933
SF-3: Registration Statement Under the Securities Act of 1933
SIP: Application or amendment to application for registration as securities infomation processor
T-1: Statement of eligibility and qualification under the Trust Indenture Act of 1939 of corporations designated to act as trustees
T-2: Statement of eligibility under the Trust Indenture Act of 1939 of an individual designated to act as trustee
T-3: For applications for qualification of indentures under the Trust Indenture Act of 1939
T-4: Application for exemption filed pursuant to Section 304(c) of the Trust Indenture Act of 1939
T-6: Application under Section 310(a)(1) of the Trust Indenture Act of 1939 for determination of eligibility of a foreign personal to act as institutional trustee
TA-1: Uniform form for registration as a transfer agent and for amendment to registration
TA-2: Form for reporting activities of transfer agents
TA-W: Notice of withdrawal from registration as transfer agent
TCR: Tip, Complaint, or Referral
TH: Notification of Reliance on Temporary Hardship Exemption
WB-APP: Application for Award for Original Information Submitted Pursuant to Section 21F of the Securities Exchange Act of 1934
X-17A-19: Report of Change in Membership Status
X-17A-5 Part I: FOCUS Report, Part I
X-17A-5 Part II: FOCUS Report, Part II
X-17A-5 Part II: FOCUS Report, Part II Instructions
X-17A-5 Part IIA: FOCUS Report Part IIa Instructions
X-17A-5 Part IIA: FOCUS Report Part IIa
X-17A-5 Part IIB: FOCUS Report, Part IIb (OTC Derivatives Dealer)
X-17A-5 Part III: FOCUS Report: Information Required of All Brokers and Dealers Pursuant to Rule 17a-5, Part III
X-17A-5 Schedule I: (Financial and Operational Combined Uniform Single) FOCUS Report: Information Required of All Brokers and Dealers Pursuant to Rule 17a-5
X-17F-1A: Missing/Lost/Stolen/Counterfeit Securities Report


### SEC-Edgar

[sec-edgar](https://github.com/sec-edgar/sec-edgar) is a Python package to  download all of a company’s periodic reports, filings and forms from the EDGAR database.

Install it via pip with:

``$ pip install secedgar``

## Constituents

## Indicators

## Strategies

### Buy & Hold

## Interesting Repos

### Compilations
* Compilation of resources Quant Machine Learning: [Awesome Quant Machine Learning Trading](https://github.com/grananqvist/Awesome-Quant-Machine-Learning-Trading)
* Compilation of resources Deep Learning Trading: [Awesome Deep Trading](https://github.com/cbailes/awesome-deep-trading)

### Visualization
* Visual analysis of financial data: [Matplotlib Finance](https://github.com/matplotlib/mplfinance)
``pip install --upgrade mplfinance``

### Machine Learning
* Reinforcement Learning for trading: [FinRL: A Deep Reinforcement Learning Library for Quantitative Finance](https://github.com/AI4Finance-LLC/FinRL-Library)

## Interesting Links

### Portfolio Optimization

Portfolio Allocation backtesting and simulations:

* Portfolio Charts: https://portfoliocharts.com/portfolios/
* Portfolio Visulizer: https://www.portfoliovisualizer.com/
* Backtest: https://backtest.curvo.eu/