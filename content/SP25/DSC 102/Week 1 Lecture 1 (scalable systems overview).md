#dsc
#### Current works
- Teradata vector store
	- managing and organizing vector embeddings by context
	- vector stores need to be highly performant with large and multi-dimensional vectors
	- need to arrange vector embeddings to be retrievable with intelligent searches
		- KMeans
		- HNSW- https://www.pinecone.io/learn/series/faiss/hnsw/

#### Why this course
- recommender systems
- search across structured data
- how do these service providers know how to pick and select (quickly) what the user wants 

#### Large datasets + ML/DL/AI
- recommendations are driven by machine learning
- everything is math and statistics packaged to process data
- knowledge base construction process
	- extracts tabular/relational data from large amounts of text data
- knowledge vault
	- data from web, prior data from FB $\rightarrow$ document object model

#### Use cases
- product recommendation
- chatting with documentation
- healthcare
- biotech
- medicine
- everything to do with information that needs to be processed and used

#### Software systems
- for data analytics, ML, and AI over large and complex datasets
- now critical for digital applications in many domains
	- what tools do we use?
		- this course ^^^

#### Vision
- data science professionals ought to be familiarized with data systems from the user's standpoint
	- as opposed to the conventional approach of a system implementer
- need to know how to use them and when to use them for daily work

#### DSC 102
- fundamentals of scalable analytics
- interested in systems that can process the data
	- analytics systems
- systems
	- what resources does a computer have?
	- how do you store and efficiently compute over large data?
	- what is the cloud?
		- resources might not be physically present
- scalability
	- how to scale and parallelize data-intensive computations
		- splitting process into smaller pieces that take a shorter amount of time to execute
- analytics
	- source
		- interested in where we get the data and how we process it
	- build
		- model selection and deep learning systems
		- how can we represent the process that we would like to study
		- building an accurate representation to get results about how this process operates
	- deploying
		- deploying the ML models
		- making it available for users
- will have hands-on experiences in this course

#### The lifecycle of ML-based analytics
- overall, we want to solve problems
	- solve the traffic problem on I-5
		- source
			- figure out where the cars are coming from
			- get traffic data
		- build
			- linear model that suggests that the amount of cars is proportional to some observations
		- deploy
			- university community uses and benefits from the model
	- what do you need to solve this problem?
		- ML/AI + data systems infrastructure
			- python, scikit, R, tensorflow, pytorch, dask, spark, AWS
- data acquisition
- data preparation
- feature engineering
	- figure out what observations are relevant to what you want
- training & inference
	- based on what we want to figure out
- model selection
	- pick the model that works the best
- server monitoring
	- offering findings to the customers

#### ML Systems
- data processing system (data system)
	- for mathematically advanced data analysis operations
		- inferential or predictive
	- interface for inputting the data
		- statistic analysis; ML, deep learning, data mining (domain-specific applied ML + feature engineering)
		- high-level APIs to express ML computations over (large) datasets

#### Categorizing ML systems
- orthogonal dimensions of categorization
	- dimensions that do NOT go together; they are orthogonal to each other
		- things that cannot be associated with each other
	- scalability
		- one item of interest
		- want to make things grow as the amount of data I throw into the system increases
		- in-memory libraries vs. scalable ML system (works on larger-than-memory datasets)
			- don't want training time to double with doubling the data
	- target workloads
		- general ML library vs. decision tree-oriented vs. deep learning
	- implementation reuse
		- layered on top of scalable data system vs. custom from-scratch framework

#### Major existing ML systems
- general ML libraries
	- in-memory
		- scikit-learn
		- R
	- disk-based files
		- SAS
		- DASK
	- layered on RDBMMS/Spark
		- MADlib
		- Apache Spark
		- MLlib
	- cloud-native
		- azure machine learning
		- amazon sagemaker
	- "AutoML" platforms:
		- DataRobot
		- $H_{2}O$ ai
		- black box, automatic machine learning...
		- practical in some cases
	- decision tree-oriented
		- dmlc XGBoost
		- microsoft LightGBM

#### Data systems concerns in ML
- how do ML systems relate to ML?
	- using scope operators...
	- through the language, access specific parts of the ML systems
- key concerns in ML
	- accuracy
		- always a concern
	- runtime efficiency (sometimes)
		- ex. scanning credit card at grocery store, don't want this to take a few minutes
- additional key *practical* concerns in ML systems
	- scalability (and efficiency at scale)
		- feeding so much data that the system starts having trouble processing all of the data
	- usability
		- is it intuitive? or do I need to read thousands of pages before I can use the system?
	- manageability
		- initial creation is great, want to build on top of it
		- code starts becoming longer
			- can you maintain your code?
			- will your code start to break down?
	- developability
		- is it easy to keep working on the system
	- explain-ability
		- in simple terms, can you provide an outlook and a description of what your work does
		- desirable property; it is a business requirement for DS applications
- the practical concerns are long-standing concerns in the DB systems world
	- when you build and work with database systems--as a user or a developer
- what if the dataset is larger than single-node RAM?
	- RAM on laptop is inadequate to process all the data at once
	- another instance of scalability issue 

#### Conceptual system stack analogy
- ![[stackanalogy.png]]

#### Real-World ML: pareto surfaces
- model accuracies
	- A: 95%
	- B: 85%
	- C: 90%
	- D: 85%
- which model do we prefer?
	- want the cheapest one and want the most efficient one
		- in most scenarios, cannot have both
		- pareto frontier
			- usually want to pick the happy medium
- pareto surfaces
	- accuracy, monetary cost, training time, scalability, inference latency, tool availability, interpretability, fairness, etc.
		- these are all things that real-world ML users must deal with
		- multi-objective optimization

#### Learning outcomes
- explain basic principles of memory hierarchy, parallelism paradigms, scalable data systems, cloud computing, and containerization
- identify abstract data access patterns, opportunities of efficiency, scale
- outline how to use different services and workflows
- apply programming scales for end-to-end pipelines
- reason critically about practical tradeoffs

