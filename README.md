# ETL Pipeline Project

An ETL (Extract, Transform, Load) pipeline built using Apache Airflow for data processing and workflow management. This project is designed to handle data extraction from various sources, transform the data according to specified rules, and load it into a target system for analysis.

## Overview
This ETL pipeline is implemented as an Apache Airflow DAG (Directed Acyclic Graph) that automates the data processing workflow. The pipeline is containerized using Docker for easy deployment and management.

### High-Level Architecture
```plaintext
┌──────────────┐       ┌──────────────┐       ┌──────────────┐       ┌──────────────┐
│    Source    │───────►    Extract   ├───────►    Transform  ├───────►     Load     │
└──────────────┘       └──────────────┘       └──────────────┘       └──────────────┘
                                │
                                │
                                ▼
                         ┌──────────────┐
                         │   Storage    │
                         └──────────────┘
```

## Project Structure
```
d:/ETL Pipeline/
├── .dockerignore
├── .gitignore
├── docker-compose.yml
├── Dockerfile
├── packages.txt
├── README.md
├── requirements.txt
├── dags/
│   ├── .airflowignore
│   ├── etl.py
│   └── exampledag.py
├── include/
├── plugins/
└── tests/
    └── dags/
        └── test_dag_example.py
```

## Features

### Data Extraction
- Multiple data source support (APIs, databases, files)
- Configurable extraction intervals
- Data versioning and tracking

### Data Transformation
- Data validation and cleansing
- Data mapping and schema transformation
- Data aggregation and filtering

### Data Load
- Support for multiple target systems (databases, data warehouses)
- Incremental loading strategies
- Data integrity checks

### Orchestration
- Automated workflow management using Airflow
- Task dependencies and parallel execution
- Error handling and retries

### Utilities
- Logging and monitoring
- Configuration management
- Environment isolation

## Technical Stack
- **Apache Airflow**: Workflow management and orchestration
- **Docker**: Containerization and deployment
- **Python**: Data processing and transformation logic
- **SQLAlchemy**: Database operations and connections
- **Apache HTTP Server**: Serving the Airflow web interface

## Requirements
- Docker installed on the system
- Docker Compose installed for container orchestration
- Python 3.8 or higher
- Airflow dependencies (specified in requirements.txt)

## Getting Started

### Prerequisites
1. Install Docker and Docker Compose
2. Install Python 3.8 or higher
3. Clone the repository:
```bash
git clone https://github.com/abhishek-paul-d/airflow-nasa-etl-pipeline.git
```

### Installation
1. Navigate to the project directory:
```bash
cd airflow-nasa-etl-pipeline
```
2. Build and start the containers using Docker Compose:
```bash
docker-compose up -d
```

### Running the Pipeline
1. Access the Airflow web interface at `http://localhost:8080`
2. Trigger the ETL DAG manually or schedule it according to your needs
3. Monitor the pipeline execution and logs through the Airflow interface

## Configuration

### Environment Variables
 Configure the following variables in your `.env` file:
- `AIRFLOW_HOME`: Path to Airflow home directory
- `DB_HOST`: Database host address
- `DB_PORT`: Database port
- `DB_USERNAME`: Database username
- `DB_PASSWORD`: Database password

### Pipeline Configuration
Modify the DAG configuration in `dags/etl.py` to:
- Set source and target connections
- Define data transformation rules
- Configure logging and monitoring

## Best Practices
1. Follow standard Python coding conventions
2. Use meaningful commit messages
3. Test changes locally before pushing
4. Document new features and configuration options
5. Maintain backward compatibility

## Contributing
1. Fork the repository
2. Create a feature branch:
```bash
git checkout -b feature/your-feature-name
```
3. Commit your changes:
```bash
git commit -m "Add feature description"
```
4. Push to the branch:
```bash
git push origin feature/your-feature-name
```
5. Open a Pull Request

## Changelog
- v1.0.0 - Initial release with basic ETL functionality
- v1.1.0 - Added Docker containerization support
- v1.2.0 - Implemented Airflow DAG for workflow management
- v1.3.0 - Enhanced documentation and project structure
- v1.4.0 - Added comprehensive logging and monitoring

## License
MIT License

## Acknowledgments
- Inspired by Apache Airflow's best practices
- Thanks to the open-source community for the amazing tools and libraries
- Special thanks to [Your Name] for initial implementation
