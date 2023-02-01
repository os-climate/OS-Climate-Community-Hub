# Data Commons 
## What is it?
Data Commons is the platform and infrastructure which manages data as code.  The components include data ingestion pipelines, metadata management, data access management, data extraction technology, and functionality that enables different data sources to be federated and linked together (e.g. using entity matching for legal entities and subsidiaries). 
- Leverages Open MetaData to ensure data sources are discoverable and shareable.  
- Supports different types of data pipelines (batch data, federated data, real-time streamed data) in data creation, storage, transformation and distribution.
- Supports “data as code” approach where the data pipeline code, the data itself and data schema are versioned so as to have transparency and reproducibility (time travel). 

Key technical design aspects:
- The entire deployment of the Data Commons platform (and our future data exchange services components) is based on declarative GitOps continuous delivery on Kubernetes, leveraging ArgoCD as the Continuous Delivery tool. 
- All components of the platform are open source (we don't use any native cloud service) - we test and validate specific container images and maintain the deployment blueprint as code (application manifests) in an open source repository under OperateFirst (for an example, look at OpenMetadata manifests under https://github.com/operate-first/apps/tree/master/openmetadata) 
- The platform itself follows a data mesh architecture which means it leverages a query federation technology (Trino) to query distributed data directly across SQL, NoSQL, streaming, etc... data sources, only leveraging container storage on the given cloud provider infrastructure to ingest or cache data as required. 
- All data ingestion, transformation, data quality controls and metadata ingestion required is maintained as data pipeline code in OS-Climate repositories. This means that if you install the Data Commons component on any Cloud and run all existing data pipelines, you would get a carbon copy of the data we now have on current instances running on AWS (with a caveat - this will not get historical data for previous versions of the code that may not have been cleaned).

### [Overview & Videos](https://os-climate.org/data-commons/)
   - Data Commons Architecture: [Learn More](https://github.com/os-climate/os_c_data_commons/blob/main/README.md)
     - [Scaling the Open Source Climate Community](https://pretalx.com/bbuzz22/talk/JNJTHF/) Video featuring OS-C's software, data science, platforms, and community architecture (note: specifics about OS-C infrastructure starts at ~11 minute mark).
     - Managing Data as Code: [Data pipeline example using Open Metadata and streamed data from CO2Signal](https://osclimateorg.sharepoint.com/:v:/g/EXdxjJKjCSlCqGBkYIA83DoBaCm9O5IWZdljoralV0zMKg?e=FHVML3)
     - Architecture & 2023 Roadmap [Presentation](https://osclimateorg.sharepoint.com/:b:/g/EYUQfI7k9tNHtVrHVxnqg8cBmPiOzzjYi9mH_bZGU9g9Ag?e=kRa0AT)
     - COP27 Data Commons Overview [Presentation](https://osclimateorg.sharepoint.com/:b:/g/EQtilRdHpjJBnJm08KLOmv4Bqb_UekwF1Z6qahhNdDmnTw?e=dmnJrM) 
     - Building Data Pipelines [Video](https://drive.google.com/file/d/1Ll-bDjbycqIdmVi2h-Mdg7WATs7PcGXM/view?usp=share_link)
     - OS-Climate Data Commons article on [Data Mesh](https://towardsdatascience.com/makingclimate-data-easy-to-find-use-and-share5190a0926407)
   - **UPDATED JAN-2023** [Data Commons Developers Guide](https://github.com/os-climate/os_c_data_commons/blob/main/os-c-data-commons-developer-guide.md)
   - Attend a Data Commons team meeting: [Meeting Info](https://github.com/os-climate/OS-Climate-Community-Hub/blob/main/MEETING_LIST.md#note)
   - [Data Commons Project Board](https://github.com/orgs/os-climate/projects/7)
   - Related Repos: 
     - [Data Platform Demo](https://github.com/os-climate/data-platform-demo)
     - [OS-C Data Commons](https://github.com/os-climate/os_c_data_commons)
     - [Trino ACL DSL](https://github.com/os-climate/osc-trino-acl-dsl)
     - [Pachyderm Notebook Image](https://github.com/os-climate/pachyderm-notebook-image)
     - [Trinto Github Group Provider](https://github.com/os-climate/trino-github-group-provider)
     - [Elyra Plotly Notebook](https://github.com/os-climate/elyra-plotly-notebook)
