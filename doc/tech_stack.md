# Crypt Bot - Tech Stack
- Crypt Bot will utilize a micro service architechture that ingests market data and uses that data to fuel algorithmic trading strategies to execute trades and produce suggestions on configured symbols

## Technology
- Language: Python
- Database: Postgres
- Service Orchistration: Docker
- Containers:
    - Portainer: Microservice management
- Packages:
    - NumPy: Numerical analysis
    - PyAlgoTrade?: Backtesting trading strategies
    - Zipline?: Backtesting trading strategies
    - Pyfolio: Portfolio and risk analysis
    - Grpc: Communication between services
    - Protobuf: Message serialization
    - Flask: Http Server
    - Requests: Http requests to exchange APIs
    - PythonSocketIO: Realtime socket communication with exchange APIs
- Web Server: Nginx (Future feature)