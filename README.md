
## Local Setup & Prerequisites

- Docker

## How to Run
1. clone this repository 

2. Run the build command in the repo directory:
    ```bash
        docker build -t assign18-app .
    ```
3. Run the application:
     ```bash
        docker run --rm -it -p 8080:8080 -v $(pwd):/workspace assign18-app
    ```
4. On the link , run the app.ipynb cell by cell.


## Summary of Operations Demonstrated

* **Data Generation**: Creates 5,000,000 rows using `spark.range()`.
* **Partition Inspection**: Retrieves counts via `df.rdd.getNumPartitions()`.
* **Upscaling (12 Partitions)**: Uses `.repartition(12)` which triggers a data shuffle to balance rows.
* **Downscaling (3 Partitions)**: Uses `.coalesce(3)` to minimize shuffling by merging existing data blocks.
