# Experiment 8: Kafka-Based Event-Driven Publishing Pipeline

This project demonstrates an event-driven architecture using Apache Kafka in KRaft mode and Spring Boot. It includes:

- A Spring Boot backend that schedules posts and publishes Kafka events
- A Kafka consumer that processes events asynchronously
- A retry and dead-letter queue pattern for failed messages
- A React frontend dashboard for scheduling and monitoring posts

## Project structure

- `backend/` - Spring Boot application
- `frontend/` - React + Vite dashboard
- `docker-compose.yml` - Kafka broker setup
- `INSTRUCTIONS.md` - lab instructions
- `explanation.md` - summary notes
- `experiment_8.pdf` - experiment PDF

## Run the project

1. Start Kafka:
   ```bash
   docker compose up -d
   ```

2. Start the backend:
   ```bash
   cd backend
   ./mvnw spring-boot:run
   ```

3. Start the frontend:
   ```bash
   cd frontend
   npm install
   npm run dev
   ```

4. Open the frontend URL shown by Vite (typically http://localhost:5173).

## Notes

- The backend uses a scheduled post workflow and Kafka topics to process delayed publications.
- Failed events are retried, and messages that exceed the retry limit can be routed to a dead-letter flow.
- The frontend polls for updates and reflects post status changes in real time.
