load('ext://dotenv', 'dotenv')

# Load environment variables
dotenv('.env')  # Load the root .env file; adjust the path if specific to backend

# Backend
backend_yaml = local('kubectl kustomize fullstack-nestjs-backend/k8s')
k8s_yaml(backend_yaml)

docker_build(
    'backend', 
    'fullstack-nestjs-backend', 
    dockerfile='fullstack-nestjs-backend/Dockerfile'
)

# Frontend
frontend_yaml = local('kubectl kustomize fullstack-react-frontend/k8s')
k8s_yaml(frontend_yaml)

docker_build(
    'frontend', 
    'fullstack-react-frontend', 
    dockerfile='fullstack-react-frontend/Dockerfile'
)

# Port forwards
k8s_resource(
    'backend', 
    port_forwards=3000
)

k8s_resource(
    'frontend', 
    port_forwards=3001
)
