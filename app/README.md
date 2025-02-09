# NFT Purchase Application

This application allows users to purchase NFTs using CRAFT tokens.

## Prerequisites

*   Python 3.9 or higher
*   Node.js 16 or higher
*   Docker (optional, for containerized deployment)
*   PostgreSQL database

## Setup

1.  **Clone the repository:**

    ```bash
    git clone <repository_url>
    cd nft-purchase-application
    ```

2.  **Configure the backend:**

    *   Create a `.env` file in the `backend` directory based on the `.env.example` template.
    *   Set the following environment variables:
        *   `SOLANA_NETWORK`: The Solana network to connect to (e.g., `https://api.devnet.solana.com`).
        *   `CRAFT_TOKEN_ADDRESS`: The address of the CRAFT token on the Solana blockchain.
        *   `NFT_MINT_ADDRESS`: The address of the NFT mint on the Solana blockchain.
        *   `TREASURY_WALLET_PRIVATE_KEY`: The private key of the treasury wallet that will receive the CRAFT tokens.
        *   `EMAIL_HOST`: The hostname of your email server (e.g., `smtp.gmail.com`).
        *   `EMAIL_PORT`: The port number of your email server (e.g., `587`).
        *   `EMAIL_USER`: The username for your email account.
        *   `EMAIL_PASSWORD`: The password for your email account.
        *   `DATABASE_URL`: The connection string for your PostgreSQL database (e.g., `postgresql://user:password@host:port/database`).
        *   `ALLOWED_ORIGINS`: A comma-separated list of allowed origins for CORS (e.g., `http://localhost:3000`).

3.  **Set up the database:**

    ```bash
    cd backend
    python db_setup.py
    ```

    This will create the `transactions` table in your PostgreSQL database.

4.  **Install backend dependencies:**

    ```bash
    pip install -r requirements.txt
    ```

5.  **Configure the frontend:**

    *   Navigate to the `frontend` directory:

        ```bash
        cd ../frontend
        ```

    *   Install frontend dependencies:

        ```bash
        npm install
        ```

## Running the Application

1.  **Start the backend:**

    ```bash
    cd backend
    python app.py
    ```

2.  **Start the frontend:**

    ```bash
    cd frontend
    npm start
    ```

    This will start the frontend development server on `http://localhost:3000`.

## Docker Deployment (Optional)

1.  **Build the Docker images:**

    ```bash
    docker-compose build
    ```

2.  **Run the Docker containers:**

    ```bash
    docker-compose up
    ```

    This will start the backend, frontend, and database containers. The application will be accessible on `http://localhost:3000`.

## Testing

To run the backend tests:

```bash
cd backend
python test_app.py
```

## Remaining Issues/Limitations

*   The Solana integration is currently a placeholder and needs to be implemented.
*   The application lacks rate limiting and should be added for production deployments.
*   The UI is basic and could be improved with a component library.
*   More comprehensive error handling and logging should be implemented.
