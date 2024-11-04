# Use the official Python image from Docker Hub
FROM python:3.9-slim

# Copy requirements.txt into the container
COPY requirements.txt .

# Install Git
RUN apt-get update && apt-get install -y git && apt-get clean

# Install the required packages
RUN pip install --no-cache-dir --upgrade pip && pip install --no-cache-dir -r requirements.txt

# Copy the rest of the application code into the container
COPY .. .

# Install Jupyter
RUN pip install jupyter

# Expose the port for Jupyter Notebook
EXPOSE 8888

# Set the default command to start Jupyter Notebook
CMD ["jupyter", "notebook", "--ip=0.0.0.0", "--no-browser", "--allow-root", "--notebook-dir=/app"]