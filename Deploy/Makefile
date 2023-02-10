INVENTORY_URL=10.140.0.13
STORAGE_URL=10.140.0.14

tools:
	apt update && apt install docker.io docker-compose make -y

business:
	INVENTORY_URL=${INVENTORY_URL} STORAGE_URL=${STORAGE_URL} docker-compose  -f docker-compose-single.yml up --build -d business

inventory:
	docker-compose -f docker-compose-single.yml up -d --build inventory

storage:
	INVENTORY_URL=${INVENTORY_URL} STORAGE_URL=${STORAGE_URL} docker-compose -f docker-compose-single.yml up -d --build storage

proxy:
	docker-compose -f docker-compose-single.yml up -d proxy		

down:
	docker-compose down
