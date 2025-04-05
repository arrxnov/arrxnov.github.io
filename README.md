<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>RedELK x Sliver Integration</title>
  <link href="https://fonts.googleapis.com/css2?family=Fira+Sans&display=swap" rel="stylesheet">
  <style>
    body {
      font-family: 'Fira Sans', sans-serif;
      background-color: #f9f9f9;
      color: #222;
      max-width: 800px;
      margin: auto;
      padding: 2rem;
      line-height: 1.6;
    }
    h1, h2, h3 {
      color: #222;
    }
    code {
      background-color: #eee;
      padding: 2px 6px;
      border-radius: 4px;
      font-family: monospace;
    }
    pre {
      background-color: #111;
      color: #0f0;
      padding: 1rem;
      overflow-x: auto;
      border-radius: 8px;
    }
    a {
      color: #007acc;
      text-decoration: none;
    }
    a:hover {
      text-decoration: underline;
    }
    .screenshot {
      max-width: 100%;
      border: 1px solid #ccc;
      border-radius: 4px;
      margin: 1rem 0;
    }
    .note {
      background: #fffbdd;
      border-left: 4px solid #ffd33d;
      padding: 0.5rem 1rem;
      margin: 1rem 0;
    }
  </style>
</head>
<body>

  <h1>RedELK + Sliver: Custom C2 Visibility</h1>
  <p><em>Published on April 4, 2025</em></p>

  <p>
    This post walks through the full setup of <strong>Sliver C2</strong> integrated with <strong>RedELK</strong> for visibility, log forwarding, and operational monitoring.
  </p>

  <h2>🔧 What We Built</h2>
  <p>
    We used Filebeat on the Sliver server to ship logs into a custom <code>sliver.conf</code> pipeline in Logstash, with output to Elasticsearch for real-time analysis via Kibana dashboards.
  </p>

  <h2>📦 Docker Setup</h2>
  <p>Here's the minimal <code>docker-compose.yml</code> stack:</p>
  <pre><code>version: '3.8'
services:
  elasticsearch:
    image: docker.elastic.co/elasticsearch/elasticsearch:8.12.2
    ...
  kibana:
    image: docker.elastic.co/kibana/kibana:8.12.2
    ...
  logstash:
    image: docker.elastic.co/logstash/logstash:8.12.2
    ...
</code></pre>

  <h2>📈 Results</h2>
  <p>Here's a sample dashboard showing parsed log events:</p>
  <img class="screenshot" src="images/sliver-dashboard.png" alt="Kibana Sliver Dashboard" />

  <h2>📁 GitHub Repo</h2>
  <p>
    Full config and dashboard templates are available at:
    <a href="https://github.com/yourusername/redelk-sliver" target="_blank">github.com/yourusername/redelk-sliver</a>
  </p>

  <div class="note">
    💡 Want to integrate detection logic or anomaly alerts? Stay tuned for Part 2.
  </div>

  <footer>
    <hr />
    <p>&copy; 2025 Your Name — Built with 💀 and ☕</p>
  </footer>

</body>
</html>

