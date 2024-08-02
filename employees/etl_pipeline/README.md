Contains the ETL pipeline for the MySQL employees database. This pipeline takes data from all tables of the 
database and denormalizes it to one master dataframe. The data in the database is at 3NF standard. The consolidated
master dataframe brings this down to a 1NF.

**The master dataframe follows 1NF because:**
- Atomicity: Data in each column is atomic as it can not be divided further examples of non-atomic data can be lists.
- Uniqueness: Each record is unique (there are no duplicate entries) and the index is the primary key.
- Consistency: Data in each column has the same data type.

To run the container you may clone this directory and either run the pipeline with Docker (recommended) or
run the pipeline manually. The steps for each is listed below:

**Running with Docker (recommended):**
  1: cd etl_pipeline
  2: docker build -t <image_name> .
  3: docker run --name <container_name> -it <image_name>
  4: docker cp <container_name>:/app/master_data </path/to/your_directory>

**Running manually:**
  1: cd etl_pipeline
  2: bash run_pipeline.sh
  3: cp master_data </path/to/your_directory>
  
