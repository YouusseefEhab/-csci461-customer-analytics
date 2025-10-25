Names Of Team Work In This Project:
1)youssef Ehab Fawzy
2)Mohamed Montasser
3)Ziad Hamada
4)Fady 

all Docker build / run commands used.

docker build -t csci461-customer-analytics:latest .
docker run -it --name csci461_run -v $(pwd):/app/pipeline csci461-customer-analytics:latest
python ingest.py /app/pipeline/cancer_data.xlsx
chmod +x summary.sh
./summary.sh csci461_run
execution flow

1. Build the Docker Image
docker build -t csci461-customer-analytics:latest .
2. Run the Container
docker run -it --name csci461_run -v $(pwd):/app/pipeline csci461-customer-analytics:latest
3. Execute the Pipeline
python ingest.py /app/pipeline/cancer_data.xlsx
Pipeline Flow
cancer_data.xlsx
      ↓
ingest.py → creates data_raw.csv
      ↓
preprocess.py → cleans & saves data_preprocessed.csv
      ↓
analytics.py → generates insights (3 text files)
      ↓
visualize.py → saves plots (.png)
      ↓
cluster.py → creates clusters.txt

Results Location
/app/pipeline/results
Contents:

data_raw.csv — raw converted data

data_preprocessed.csv — cleaned data

insight1.txt, insight2.txt, insight3.txt — analytical insights

all_features_hist.png, correlation_heatmap.png — visualizations

clusters.txt — K-Means cluster counts


Screen Shots
