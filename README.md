# Ant Colony Algorithm Simulation

A web-based simulation and analysis tool for the Ant Colony Optimization (ACO) algorithm, designed to optimize network routing and traffic flow. This project combines an interactive React frontend with a Python backend powered by Google's Gemini AI for intelligent chatbot assistance.

## Features

- **Interactive Simulation**: Visualize ant colony algorithm in real-time on a network canvas
- **Network Analysis**: Perform comprehensive analysis of network performance metrics
- **Traffic Optimization**: Simulate and optimize traffic flow using ACO principles
- **AI-Powered Chatbot**: Get intelligent assistance and explanations using Gemini API
- **Route Comparison**: Compare different routing algorithms (ACO vs Dijkstra)
- **Performance Metrics**: Track and display key performance indicators
- **Customizable Parameters**: Adjust algorithm parameters for different scenarios

## Tech Stack

### Frontend
- **React 18** with TypeScript
- **Vite** for fast development and building
- **Tailwind CSS** for styling
- **ESLint** for code quality

### Backend
- **Python 3.13** with Flask
- **Google Generative AI (Gemini)** for chatbot functionality
- **Flask-CORS** for cross-origin requests

### Key Libraries
- Ant Colony Algorithm implementation
- Dijkstra's algorithm for comparison
- Network analysis utilities
- Animation and visualization tools

## Project Structure

```
Ant_Colony_Algorithm_EL/
├── src/                          # Frontend source code
│   ├── components/               # React components
│   │   ├── SimulationCanvas.tsx  # Main simulation visualization
│   │   ├── NetworkAnalysisCanvas.tsx
│   │   ├── ControlPanel.tsx      # Simulation controls
│   │   ├── ChatbotModal.tsx      # AI chatbot interface
│   │   ├── CompareNetworks.tsx   # Algorithm comparison
│   │   └── ...                   # Other UI components
│   ├── store/                    # State management
│   ├── types/                    # TypeScript type definitions
│   ├── utils/                    # Utility functions
│   │   ├── antColonyAlgorithm.ts # ACO implementation
│   │   ├── dijkstra.ts          # Dijkstra algorithm
│   │   └── ...                   # Other utilities
│   └── services/                 # API services
├── app/                          # Additional app pages
├── model_backend/                # Python backend
│   ├── gemini_model_api.py      # Flask API with Gemini
│   ├── test_model.py            # Backend tests
│   └── env/                      # Python virtual environment
├── public/                       # Static assets
├── index.html                    # Main HTML file
├── package.json                  # Node.js dependencies
├── tsconfig.json                 # TypeScript configuration
├── vite.config.ts               # Vite configuration
## API Endpoints

The backend provides the following REST API endpoints:

### Chatbot API (`gemini_model_api.py`)
- **POST** `/predict`
  - **Description**: Processes user queries about the ant colony algorithm and network analysis
  - **Request Body**:
    ```json
    {
      "prompt": "User question about ACO",
      "history_data": [...],  // Historical route data
      "name_matrix": [...]    // Node name mappings
    }
    ```
  - **Response**:
    ```json
    {
      "response": "AI-generated answer"
    }
    ```

### Network Analysis API (`test_model.py`)
- **POST** `/analyze_network`
  - **Description**: Analyzes network data and returns performance metrics
  - **Request Body**:
    ```json
    {
      "history_data": [...],  // Historical route data
      "name_matrix": [...]    // Node name mappings
    }
    ```
  - **Response**:
    ```json
    {
      "metrics": {
        "total_routers": "number",
        "total_devices": "number",
        "average_latency": "number",
        "network_efficiency": "number",
        "average_congestion": "number",
        "number_of_hops": "number",
        "topology_used": "text",
        "packet_drop_rate": "number",
        "aco_score": "number"
      },
      "status": "success"
    }
    ```

## Installation

### Prerequisites
- Node.js (v16 or higher)
- Python 3.13
- npm or yarn

### Frontend Setup
1. Clone the repository:
   ```bash
   git clone https://github.com/Sathwikpai7/AntColony.git
   cd AntColony
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Start the development server:
   ```bash
   npm run dev
   ```

### Backend Setup
1. Navigate to the backend directory:
   ```bash
   cd model_backend
   ```

2. Activate the virtual environment:
   ```bash
   # On Windows
   env\Scripts\activate
   ```

3. Install Python dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. Set up your Gemini API key:
   - Create a `.env` file in the `model_backend` directory
   - Add your Google AI API key: `GOOGLE_API_KEY=your_api_key_here`

5. Start the Flask server:
   ```bash
   python gemini_model_api.py
   ```

## Usage

1. **Start both servers** (frontend and backend) as described above
2. **Open your browser** to `http://localhost:5173` (default Vite port)
3. **Configure simulation** using the control panel:
   - Set number of ants
   - Adjust pheromone evaporation rate
   - Configure network parameters
4. **Run simulation** and watch the ants optimize routes
5. **Analyze results** using the analysis tools
6. **Chat with AI** for explanations and insights

## Key Components

### Simulation Canvas
Interactive visualization of the ant colony algorithm where you can see:
- Ants moving through the network
- Pheromone trails forming optimal paths
- Real-time route optimization

### Network Analysis
Comprehensive analysis including:
- Route efficiency metrics
- Traffic flow optimization
- Performance comparisons between algorithms

### AI Chatbot
Powered by Google's Gemini, provides:
- Algorithm explanations
- Parameter tuning advice
- Simulation insights
- Educational content

## Development

### Available Scripts
- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run preview` - Preview production build
- `npm run lint` - Run ESLint

### Backend Development
- `python test_model.py` - Run backend tests
- Modify `gemini_model_api.py` for API changes

## Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature-name`
3. Make your changes and test thoroughly
4. Commit your changes: `git commit -am 'Add new feature'`
5. Push to the branch: `git push origin feature-name`
6. Submit a pull request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- Inspired by the Ant Colony Optimization metaheuristic
- Built with modern web technologies
- Powered by Google's Generative AI

## Contact

For questions or feedback, please open an issue on GitHub or contact the maintainers.