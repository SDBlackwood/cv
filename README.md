# CV - Scott Blackwood - Software and Data Engineer

I am an experienced software and data engineer with 8 years experience.  I am looking to build a deep and robust career in and in support of machine learning and AI applications.
I mix an excellent technical aptitude with an intuition of team managment and organistaion.                     

## Career Highlights

See below various career highlights further detailing my experience.  

### Flyte Kubernetes Operator

Developed a Kubernetes operator using kubebuilder which helped us register our Flyte workflows on our flyte cluster when we did not want to make it accessible over the public network.
The operator acted on a `FlyteRegistration` CRD and would check for a flyte package which was pushed to AWS ECR during CI builds and push it to the Flyte cluster.

### Mydex Design System

### Inference Cluster Workflow Orchestration Pipeline

In Autumn 2023, Adarga launched a new initiative to centralise its inference processing within a single cluster, rather than having separate inference processes in multiple individual clusters.
This new architecture would differ from our existing setup by batch processing documents through various data processing pipelines, utilising a workflow orchestration platform.
I was part of the team responsible for the design, implementation, and rollout of the new cluster, which included three Data Scientists, two MLOps Engineers, and four Software Engineers.

I was heavily involved in each phase of the project from the very start up to this day.  This involved the fleshing out of the requirements for improved scalability, throughput and reduced cost.
This process involved conducting discovery and refinement sessions with the team, which resulted in the creation of multiple technical design documents that I either authored or contributed
significantly to. These documents often went through several rounds of revisions during the initial proof-of-concept phases. 

I spent six months integrating several key components:
- Developed a REST and gRPC API for caching and batch processing documents on the inference cluster.
- Created a Kubernetes operator for pushing workflow packages to the cluster via CI within our VPC.
- Productionised data processing workflows previously managed by the data scientists.
- Implemented Prometheus metrics and Grafana dashboards to track document throughput and latency per workflow.
- Led efforts to monitor and enhance scaling for machine learning operations and system performance.
- Set up Grafana alerts to identify workflow failures or document processing issues.

### gRPC / REST CRUD App

We created a mobile app called Panoptic which was based on some data science work to extract the claims in which an actor had stated on a given topic.
The team built it very fast and they had a situation where they only had a cache to store data and the cache would be nuked and they had no historical info.
They needed a bit of a refactor.  I was asked to come in, help "make the solution more robust", which was my only mandate.  I took part in the design to
create a basic API which could be invoked via gRPC on the backend or REST on the front end which was backed by a DB.  I advocated for splitting the indexing
and retrieval of the systems in 2 so that data was only indexed securely on the backend and could not be invoked via the front end.   I implemented that,
developed some extra quality of life changes like a dashboard to view the database, some alerts to know if the data was not being indexed and some future proposals
that the team might want to do in the future.  Ran benchmarks on the database and presented them with a PDF of when there db might begin to degrade.  
              
### Simple Python Abstractions

Developed a system for *language providers* which simply abstracted a `TranslationProvider` class with a `translate` function
which was implemented via a `AWSTranslationProvider`, `LLMTranslationProvider` and `SelfHostedLanguageProvider` each implementing translation differently.
Within that we had a simple `determine_provider` function which encapsulated all the logic to determine the provider based on both deploy time and run time configurations.
