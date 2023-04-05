FROM python:3.9-slim-buster

# Install dependencies
RUN apt-get update && \
    apt-get install -y git gcc libpq-dev && \
    rm -rf /var/lib/apt/lists/*

# Clone the Reposaur repository
RUN git clone https://github.com/reposaur/reposaur.git /reposaur

WORKDIR /reposaur

# Install Python dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Set environment variables
ENV DATABASE_URL=postgres://user:password@host:port/database
ENV AWS_REGION=your-aws-region
ENV AWS_ACCESS_KEY_ID=your-aws-access-key-id
ENV AWS_SECRET_ACCESS_KEY=your-aws-secret-access-key

# Expose the default port
EXPOSE 8080

# Start the application
CMD ["python", "run.py"]


# Below command to create this image 
# docker build -t kaustubhsingh47/reposaur:latest 

# push the code to docker registry so that it can be pulled from yaml 
# docker push kaustubhsingh47/reposaur:latest


