# OS-Climate FAQ
## What is the Data Commons?

The Global Data Commons is envisioned as a Library of Libraries that will ultimately provide a “One Stop Shop” for accessing both public and proprietary data needed for climate-aligned financial decision-making, as well as a useful platform that can be installed behind corporate firewalls to manage private data as well.  We are still at the early stages of building the Data Commons, but this is in part because all institutions are in the early stages of bringing together the broad, multifactorial data necessary to manage their way into alignment with the Paris Climate Accord.

See an overview of the Data Commons here: https://github.com/os-climate/os_c_data_commons/blob/main/README.md.  

The Data Commons platform aims at bridging climate-related data gaps across 3 dimensions:
1. Data Availability: The platform supports data availability through data democratization via self-service data infrastructure as a platform. A self-service platform is fundamental to a successful data mesh architectural approach where existing data sources are federated and can be made discoverable and shareable easily across an organization and ecosystem through open tools and readily available infrastructure supporting data creation, storage, transformation and distribution.
2. Data Comparability: The platform supports data comparability through domain-oriented decentralized data ownership and architecture, i.e., data is treated like a product. A key objective goal is to stop proliferation of data puddles to “connect” the data with proper referential and relevant industry identifiers in order to have collections of data aligned with business goals.
3. Data Reliability: The platform supports data reliability through federated data access, data lifecycle management, security, and compliance. This supports a “data as code” approach where the data pipeline code, the data itself and data schema are versioned so as to have transparency and reproducibility (time machine), while enforcing authentication and authorization required for data access management with consistent policies across the platform and throughout the data lineage.

To see how the Data Commons aims to do this, please read the Data Commons architecture blueprint here: https://github.com/os-climate/os_c_data_commons/blob/main/os-c-data-commons-architecture-blueprint.md.  If you wish to delve into the details of federated data governance, data mesh architectures, data pipeline development and management, data lineage, data security, and other topics covered in the blueprint, ask us to arrange a call with the authors of that paper.

At a nuts-and-bolts level, we are building the Data Commons in parallel with real-world use-cases: Physical Risk and Resilience, Transition Scenario Analysis, Portfolio Analysis, and PCAF Sovereign Footprint analysis.  All of these use-cases are based on the best scientific methodologies known to our Members, using the most transparent data sources we can find.  We are well aware that strong governance is vital to ensuring that we don’t lose trust as we build functionality.

## What data is in the Data Commons?

In terms of Data content (availability), we have loaded several types of sources thus far, based on priorities of the Members’ uses cases and requirements for the initial OS-C analytic tools:

● Public Data (financial, ESG, and geospatial raster data) in a Trino Database:
 - EPA GHGRP (2010-2020 years of "large emitter" data across all sectors, US-only)
 - US Census (2017 All-Sector survey)
 - ESSD (Earth System Science Dataset 1970-2018 global emissions by country, gas species, sector, and IPCC region)
 - RMI Utilities Data (2000-2020 detailed emissions, generation, targets, fuel types, ownership, etc from FERC and EIA sources)
 - WRI Global Power Plant Data (2013-2020 summary emissions, generation, fuel type, etc. for 33,000+ plants globally)
 - SFI (Spatial Finance Initiative) Steel and Cement plant location, capacity and ownership data 
 - UNFCCC GHG data
 - OECD data
 - World Bank GDP data
 - OECM Benchmark Data for Electricity Utilities and Steel Sector (with several additional sectors just released by OECM).
 - SEC DERA (2018-2022 SEC 10-K, 20-F, and 40-F financial reports, summarizing market float, revenues, assets, cash, debt, and income for over 10,000 reporting companies; 200M+ rows of financial facts)

● Public Data in S3 buckets
 - WRI Aqueduct flood data (1km resolution, translated to ZARR)
 - WorldClim Climate data (10-minute and 30-second data for 26 metrics)
 - PUDL data (the most detailed integration of FERC, EIA, and EPA data for US-based utilities and the basis of RMI’s Utilities Transition Hub dataset).

● Data Federated from ASDI (Amazon Sustainability Data Initiative)
 - GLEIF Legal Entity Identifiers (2M+ LEIs, Global)
 - LEI-ISIN mapping (7M+ records, mostly bonds, but many stocks as well)

● Data licensed by Members to OS Climate Community for permissive uses
 - Jupiter Intelligence Global Climate hazards (30km resolution, 6 hazards, 5 timeframes, 2 scenarios)
 - S&P Global - ~8,500 Corporate ESG/Sustainability reports (~75,000 anticipated in 2Q22)
 - RiskThinking.ai:
  1. 13352 datasets are scenario related (primarily NGFS projections, CMIP6, and SSP) such as solar electric capacity, CO2 emission, agricultural waste, peat burning, secondary energy.
  2. 3725 datasets are climate data sets (e.g., max temp, days of ice, frost days)
  3. 447 datasets are geophysical (e.g., storm track, flood inundation)3 are asset related (SPI cement, SPI steel, and Global Power Plant information)

Above already linked to SFI cement, SFI steel, and WRI Global Power Plant information

● Proprietary data to be licensed from Members for specific open source uses, such as (pending licensing negotiations currently underway): 
 - LSEG Sectoral Emissions, Production, and Financial Data
 - Urgentem Sectoral Scope 3 Emissions Data

● Extracted data developed by OS-Climate Member-led projects 
 - Corporate GHG footprint and forward looking data extracted from ESG reports using NLP/AI developed by Allianz and BNPP
 
● Other data aggregated or derived by Member-led projects for specific use cases. 
 - Portfolio and company-specific Implied Temperature Rise metrics. 
 - Portfolio and corporate asset-specific physical risk metrics. 
 - PCAF Sovereign Data (using public data from EDGAR, OECD, etc.)

In general, tabular data is ingested by a data pipeline that populates data tables available in a Trino (SQL) database, whereas raster and geospatial data resides in S3 buckets offering programmatic access.  In some cases, data is available via API calls, and we have libraries and documentation to make those APIs available to Data Scientists using their favorite tools (typically Python-based Jupyter notebooks).

### How are the datasets within Data Common linked together? What Metadata is available?

As the number of datasets in the Data Commons grows, it will become increasingly important to build a Data Catalog for finding and linking datasets together.  We are closely following the ISSB technical prototype from the IFRS, as well as other taxonomies and ontologies that Members have brought to review in our Data Governance Workstream.  All Members are aware that this is a large open problem, and not a problem that can be solved by one lone genius or one magical technology.  But it can be solved through collaborative, incremental innovation, and we have done considerable research on major open source technology components that give us confidence that with the right Member participation and engagement, we can solve it.

**Entity Matching:** OS-C has as part of its roadmap the development of an open source Security Master File.  This would provide a vital solution for a wide range of climate aligned data aggregation and analytics tools.  This is a clear example of what should be part of the Public Utility for climate-aligned finance, and of the pre-competitive layer of technology that would enable climate action and propel commercial innovation, while reducing cost of many companies developing and maintaining their own SCMs. 
OS-C has made significant strides toward this goal.  One of the most basic requirements of any financial data system is legal entity identification.  We have been working with GLEIF data for the past year and are impressed with its consistent growth and quality improvements.  We have established a partnership with GLEIF, and connected them with Amazon, specifically,  the Amazon Sustainability Data Initiative, so that it can have broader public impact on climate and ESG.  We have a pair of projects to support name-entity resolution optimized for ESG data: https://github.com/os-climate/financial-entity-cleaner and https://github.com/os-climate/esg-matching.

One example of using data pipelines to fit together multiple data sources is a Jupyter Notebook that uses a Sankey diagram to show the flow of data from the EPA GHG Reporting Program through corporate ownership, industry sectorization, and ultimately to emissions and revenues that can be seen in terms of relative intensities.  The source code is here: https://github.com/os-climate/data-platform-demo/blob/iceberg/notebooks/Sankey.ipynb and produces a diagram like this:

### How are you normalizing data in your data pipelines?

We have begun enhancing our data pipelines (EPA, RMI, ITR and PCAF) to produce unitized data when loaded into Pandas dataframes.  This makes it easy to normalize data to any unit system (metric, imperial, and even user-defined).  It also makes it easy to identify when data is being wrongly combined (because the units of one quantity cannot be converted into the units of another quantity).  You can see how we use Pint and Pint-Pandas in this branch of the ITR tool [https://github.com/os-climate/ITR/tree/develop] and the PCAF Sovereign project  [https://github.com/os-climate/PCAF-sovereign-footprint], and we expect this to cover virtually all data that is ever expressed with units.

### Are you using Machine Learning or Natural Language Processing to extract metrics from non-standardized information sources?

**Data Extraction:** we have a workstream using NLP to extract data from ESG reports, and ML to improve the models, that can be loaded into the Data Commons: https://github.com/os-climate/corporate_data_pipeline. There are several branches under development at present.  If your firm may be willing to contribute technical resources to this project, we are happy to arrange a briefing from that team, with the aim of determining alignment with your needs and internal roadmap.

### How are the OS-Climate analytic tools and Data Commons connected?
The Alignment, Physical Risk/Resilience, Transition Analysis Tools are not yet major users of the Data Commons, but the objective is for these and other open source tools to be able to access through the Data Commons (including the Data Vault) all of the data required for large scale climate-aligned finance.   The OS-C Analytics projects are presently focused more on specific methodological development, using data that is more readily accessed via Python libraries than via SQL tables.  We expect to see much more interaction between these workstreams and the Data Commons later in the year.  And we also expect that as Members bring forward additional use-cases, additional datasets and data pipelines will be integrated. All in all, the Data Commons is a facility under active development and growing.  

## What functionality does the Physical Risk & Resilence (PRR) workstream provide?
Assessing physical climate risk requires tooling which connects asset location data to climate hazard models and vulnerability curves.  Risk measurement includes not just the hazard value (i.e. flood depth) but also the associated asset vulnerability that determines the damage and disruption risk that those assets will face as a result of the hazard.

OS-Climate are gathering together many climate hazard and vulnerability models in one place which can serve risk measurement use cases.  The idea is to build physical risk tooling for the common good utilising an overarching risk methodology based on insurance standards. 

The OS-C open source development ecosystem fosters a strong collaboration between the research community and industry where model developments can be fuelled with regards to completing gaps in measurement requirements, helping to create a common language on the topic and directing models and data better towards risk measurement needs in particular within the finance industry as a first step.   A physical risk code package will be available through the OS-C Github along with a beta UI to help users get started.  Developments will evolve to incorporate resilience at the more regional and country level over time. 

The PRR aims to collect key climate models into one place, provide an ecosystem for collaborative development through open source mechanism and data commons, and compile vulnerability models for use in physical risk assessment.  Our goal is to reduce barriers to entry for inexperienced/under resourced orgs. We envision our tool being used: (1) during risk management and strategy/investment decision making; (2) on-going research on climate models and vulnerabilities; (3) calibrating models including validation of assumptions.  All corporate and industrial related sectors, in particular, those more suseptible to asset damage and disruption (e.g. power generation, real estate, heavy labor workforce industry) will benefit from this tool.  The tool also supports regulatory compliance on climate risk, helps institutions get a head start on understanding risks, portfolio risk measurement, engaging with counterparts, understanding and measuring the uncertainty (e.g. impact on collateral). The tool leverages publicly and commercialy available climate hazard and vulnerability models, and makes use of public and commercial asset data.

## What functionality does the Portfolio Alignment workstream provide?
OS-Climate is solving climate data and analytics challenges for Financial Institutions to accelerate redirection of capital to climate change mitigation and resilience.  In particular, the ITR tool helps investors align their portfolios with 1.5 degree pathways. OS-Climate's Open Source-based ITR tool enables investors to: 
 1. Objectively assess emissions targets and projections using recommendations from TCFD
 2. Lay out all the steps in calculating a related temperature score transparently
 3. Compare scencarios and their results; (4) allow academia and research institutions to collaborate
 4. Enable a partial independence from commercial data providers. 

The ITR tool is compliant with the recommendations of the Portfolio Alignment Team in the TCFD-Commissioned report “Measuring Portfolio Alignment”

ITR is a forward-looking management tool that facilitates the evaluation of how investment decisions can contribute to long-term climate goals – and whether individual company and portfolio behaviour exceeds net zero budget expectations.  The cumulative emissions relative to this budget at a global level informs what temperature outcome the world is likely to reach.  As a result, the mechanics of the tool are designed to compare forward-looking emissions trajectories against benchmark climate scenarios and to convert those cumulative emissions into a temperature outcome.

The Portfolio Alignment Prototype can support any sector-specific benchmarks to compare against financial institution portfolios. So far, the One Earth Climate Model (OECM) and Transition Pathway Initiative (TPI) benchmarks have been implemented. The Portfolio Alignment Prototype focuses on four highest emitting sectors: Electric Utilities, Steel, Oil & Gas and Automobiles. Data is on-boarded and accessed via an open source data infrastructure, OS-Climate’s ‘Data Commons’ supported by Red Hat.

The tool supports calulation of emission projections, temperature scores and portfolio reporting.  Forward-looking emissions trajectories are calculated using historical emissions intensity relative to sector-specific production metrics. For the temperature score calculation, the TCRE Multiplier approach was applied. Outputs are provided from the tool and visualized in a beta interface. Various parameters, e.g. scenario, temperature scores, weightings, can be adjusted in the final output to see the impact on the portfolio.

## What functionality does the Transition Analysis workstream provide?
The number and nature of risks are increasing with climate change, and combined with energy transition, it is about to disrupt the world as we know it. Generic impacts of energy transition on climate change, economy and people purchasing power… will have ripple consequences in most economic or institutional sectors.

Our Transition Analysis Tool, WITNESS, is a framework to structure the problem following a system of systems approach, allowing to leverage numerical simulation methods and tools to build a complete world transition model. Such a framework offer the possibility to plug-in best-in-class models from various origin, in order to evaluate various strategies in front of possible energy, resources, climate or economy evolutions, collaboratively securing and combining various experts advices on strategies strengths or weaknesses, coverage or gaps.

The Transition Analysis tooling (aka WITNESS and associated UI, SoSTrades) allows organizations to:
 - perform multiple scenario trades/anamysis/business cases
 - optimize global investments vs global objectives (e.g. investments in energy production techno to maximize economy development while minimizing emissions under resources constraints)
 - assess the value/impact of energy production technology or resource
 - project global economy, evolution coupled with energy, resources, climate, policies

The tool should be used for (1) assessing mid to long term investment relevance vs sustainable pathways and (2) evaluating transition risks and how policies can keep it within reasonable boundaries.  The tool will support any sector/region to evaluate sector/region evolution within global evolution context.  It is fully open source with transparent methodologies.  The SoSTrades user interface allows various experts to co-define assumptions and co-analyse results.  Additionally, the tool can connect to various data sources if needed for its models, but the baseline framework is initialized with all the needed data natively.  This embedded framework is open source and free to use.  The existing models' origin and usage are fully documented within the tool online documentation.

WITNESS allows holistic exploration and sustainable paths planning, so that transition risk can be kept at/under an acceptable level to ultimately overcome transition. WITNESS guarantees openness, transparency, allowing to develop trust in a pre-competitive model for a critical mass of actors to consistently act and effectively bend transition trajectory.
The tool allows users to assess policy, macro economic impacts (e.g. capital, labor, production, energy, consumption, investment, walfare, and energy demand) along side population, energy, materials, natural resources, and environmental variables. 

Advanced energy-economy bi-directional coupling: variable investment available from economy optimally spread to various energy production technologies; variable energy mix & price from energy made available to economy, while strain on resources is shared with other domains needs, and carbon emission contributed  to climate.  Advanced energy-technology-resources coupling: 40+ energy production technologies modelled, with assets depreciations & learning curves; interactions between energy production technologies; dynamic estimation emissions by technology; dynamic estimation of resources and materials consumptions. 

Advanced simulation platform capabilities include:
 1. Complete world transition framework to evaluate strategies /scenarios in front of possible energy, resources, climate or economy evolutions
 2. Open framework that can be adapted or completed, enabling open experts collaboration on strategies or models, strengths or weaknesses, coverage or gaps
 3. Open & trusted cooperation for a critical mass of actors to build together a strategy
 4. Tackle global climate change issues
 5. Better evolution predictability to devise mid or long term strategies and/or investments.
 6. Design space explorations:  pareto front extracted from multi-scenario analysis, understanding what are the limiting factors to progress towards an objective.
 7. Run in multi-scenario a current/preferred/planned scenario, together with worst case ones (with pessimistic assumptions):  delta between current and worst cases used as a risk metric.
 8. Run real-options value simulation for possible trade choices: better steer investments

The Transition Analysis tool is a continuously expanding exploratory and decision-support toolset to outsmart energy transition and optimize funds allocation for best environmental impact.

Feel free to contact us at contact@sostrades.org for more info if needed.

## What are the foundational principles in building the Data Commons?
1. Self-service data infrastructure as a platform: The platform provides standardized self-service infrastructure and tooling for creating, maintaining and managing data products, for communities of data scientists and developers who may not have the technology capability or time to handle infrastructure provisioning, data storage and security, data pipeline orchestration and management or product integration.
2. Domain-oriented decentralized data product ownership: Data ownership is decentralized and domain data product owners are responsible for all capabilities within a given domain, including discoverability, understandability, quality and security of the data. In effect this is achieved by having agile, autonomous, distributed teams building data pipelines as code and data product interfaces on standard tooling and shared infrastructure services. These teams own the code for data pipelines loading, transforming and serving the data as well as the related metadata, and drive the development cycle for their own data domains. This is reflected and built into our DataOps / DevOps organization and processes, with contributor team structure, access to the platform and data management capabilities supporting autonomous collaborative development for the various data streams within OS-Climate.
3. Federated governance: The platform requires a layer providing a federated view of the data domains while being able to support the establishment of common operating standards around data / metadata / data lineage management, quality assurance, security and compliance policies, and by extension any cross-cutting supervision concern across all data products.

## Where can I learn more about the technical implementation or ask questions?
 - Come to our Data Commons Office Hours! Every Tues & Thurs at 10:00AM ET (Link to meeting: https://teams.microsoft.com/l/meetup-join/19%3ameeting_ZDc5NDA4MGEtOTAyOS00OTBhLTliNjItMDQwZDliZDkyMjI4%40thread.v2/0?context=%7b%22Tid%22%3a%2214178ab3-3669-440b-a5a8-9025d18e2853%22%2c%22Oid%22%3a%225859dd70-0471-4755-9199-2b91c974baed%22%7d)
 - Create an issue: https://github.com/os-climate/os_c_data_commons/issues/new

## Where can I report a security vulnerability or concern?
Send an email to Security@os-climate.org

## Have another question?
Send an email to Admin@os-climate.org
