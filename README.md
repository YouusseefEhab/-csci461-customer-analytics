# 🧠 Customer Analytics Pipeline (Cancer Data Project)

## 📘 Project Overview
This project implements a **complete automated data analytics pipeline** inside a **Docker environment**.  
It processes cancer dataset features — performing **data ingestion, preprocessing, analytics, visualization, and clustering** automatically.  
The pipeline demonstrates how machine learning and data analytics can be combined in a reproducible, containerized workflow.

---

## 👥 Team Members
1. **Youssef Ehab Fawzy**  
2. **Mohamed Montasser**  
3. **Ziad Hamada**  
4. **Fady**

---

## 🐳 Docker Build & Run Commands
```bash
# Build the Docker image
docker build -t csci461-customer-analytics:latest .

# Run the container
docker run -it --name csci461_run -v $(pwd):/app/pipeline csci461-customer-analytics:latest

# Execute the main pipeline
python ingest.py /app/pipeline/cancer_data.xlsx

# (Optional) Run summary script
chmod +x summary.sh
./summary.sh csci461_run
