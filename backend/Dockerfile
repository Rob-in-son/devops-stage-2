FROM python:3.11-slim

# Set working directory
WORKDIR /app

# Install curl and other necessary dependencies
RUN apt-get update && apt-get install -y curl

# Install Poetry and add it to PATH in the same layer
RUN curl -sSL https://install.python-poetry.org | python3 - && \
    echo 'export PATH="/root/.local/bin:$PATH"' >> ~/.bashrc

# Load the updated PATH
ENV PATH="/root/.local/bin:${PATH}"

# Copy Poetry configuration files
COPY poetry.lock pyproject.toml ./

# Install dependencies 
RUN poetry install 

# Copy the entire project
COPY . .

# Expose the port that the application will run on
EXPOSE 8000

# Run the prestart script and start the server (modified)
CMD ["sh", "-c", "poetry run ./prestart.sh; poetry run uvicorn app.main:app --host 0.0.0.0 --port 8000 --reload"]
