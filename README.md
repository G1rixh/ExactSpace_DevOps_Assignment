# ExactSpace DevOps Assignment 

This is a multi-stage Dockerized web scraping project that uses **Node.js with Puppeteer** for scraping and **Python Flask** for serving the data via a REST API.

---

## 📁 Project Structure

```
├── scrape.js              # Puppeteer script to scrape data from a target URL
├── server.py              # Flask app serving the scraped data
├── Dockerfile             # Multi-stage Dockerfile (Node.js + Python)
├── package.json           # Node.js dependencies
├── requirements.txt       # Python dependencies
├── README.md              # Project documentation
```

---

## 🧰 Prerequisites

- Docker installed and running
- Basic understanding of terminal/command-line usage

---

## ⚙️ Configuration

You can specify the URL to scrape using an environment variable:

```env
SCRAPE_URL=https://example.com
```

If not set, it defaults to `https://example.com`.

---

## 🔧 Setup & Build

To build the Docker image:

```bash
docker build -t puppeteer-flask-scraper .
```

This command performs the following:
1. Installs dependencies and runs the Node.js Puppeteer script to scrape data.
2. Copies the scraped data to a second Python-based container.
3. Sets up a Flask server to serve the data.

---

## 🚀 Run the Application

To start the container:

```bash
docker run -p 5000:5000 puppeteer-flask-scraper
```

Then open your browser or API tool at:

```
http://localhost:5000
```

You should see the JSON response from the scraping process.

---

## 🧪 Development & Testing

If you want to test locally (outside Docker):

### 1. Run Puppeteer script:

```bash
node scrape.js
```

Make sure Chromium or Chrome is installed on your system.

### 2. Run Flask server:

```bash
pip install -r requirements.txt
python server.py
```

Then open `http://127.0.0.1:5000` to access the API.

---

## 🐳 Docker Cleanup (Optional)

To stop and remove the container:

```bash
docker ps
docker stop <container_id>
docker rm <container_id>
```

To remove the image:

```bash
docker rmi puppeteer-flask-scraper
```

---

## 🧠 Troubleshooting

- **Chromium not found**: Make sure the required Chromium dependencies are installed in the Node container.
- **Flask not found**: Ensure Python packages are installed correctly or installed in the right environment.
- **Docker 401 errors**: Try logging into Docker using `docker login`.

---

## 📬 Contact

For questions, reach out to [Girish](https://github.com/G1rixh)

---

## ✅ Status

Project complete and containerized successfully.
