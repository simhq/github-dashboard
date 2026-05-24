# GitHub Dashboard

A powerful, single-page dashboard to explore and discover trending GitHub repositories and AI skill-focused projects. The dashboard provides dual views: **Top Repos** (general trending repositories) and **Top Skills** (specialized AI instruction sets, prompt templates, and agent workflows), with filtering, sorting, and tagging capabilities.

## ✨ Features

-   **Dual Dashboard Views**
    -   **Top Repos**: Most-starred repositories over customizable time periods (Last 4 Months, 1 Year, 3 Years, All Time).
    -   **Top Skills**: Specially curated list of repositories focused on AI skills, prompts, agents, and workflows, with a proprietary **relevance score**.
-   **Smart Filtering & Sorting**
    -   Sort by stars, creation date (Top Repos), or relevance (Top Skills).
    -   Filter by dynamic, auto-generated categories (e.g., AI/ML, Framework, Dev Tool).
    -   Full-text search across repository names, descriptions, and owners.
-   **GitHub Integration**
    -   Uses the **GitHub REST API v3** for live data.
    -   Optional **Personal Access Token (PAT)** support to increase rate limits from 60 to 5,000 requests per hour.
-   **Responsive & Modern UI**
    -   Clean, dashboard-style interface with a light theme.
    -   Repository cards display key metadata: stars, creation date, language, topics, and category tags.
    -   Fully responsive design for desktop, tablet, and mobile devices.

## 🚀 Live Demo

You can access and use the dashboard directly from your browser. No build or installation is required.

👉 **[Launch GitHub Dashboard](https://simhq.github.io/github-dashboard/)**  *(Replace with your actual GitHub Pages URL)*

## 🛠️ How to Use

The dashboard is entirely client-side and runs in your browser.

1.  **Open the Dashboard**: Navigate to the live URL or open the `index.html` file locally.
2.  **Switch Views**: Use the tabs at the top to toggle between **Top Repos** and **Top Skills**.
3.  **Adjust Time Period**: Click on time pills (e.g., "Last 4 Months", "All Time") to change the data range.
4.  **Sort Results**: Use the sort buttons to order repositories by stars, creation date, or relevance.
5.  **Apply Filters**:
    -   **Search**: Use the search bar to find specific repositories by name or description.
    -   **Category Tags**: Click the **Filter ▾** button to filter repositories by auto-detected categories like `AI / ML`, `Database`, or `Coding / Dev`.
6.  **Use a GitHub PAT (Optional)**:
    -   Enter your [GitHub Personal Access Token](https://github.com/settings/tokens) (no scopes required) in the "PAT" field to increase your API rate limit.

## 🧠 How It Works

### Top Repos (Trending)
-   Fetches data from the `GET /search/repositories` endpoint.
-   Queries are built using the `created:` qualifier for different time periods.
-   Repositories are automatically tagged with categories based on their name, description, language, and topics.

### Top Skills (AI-Focused)
-   Performs **two parallel GitHub searches**:
    1.  `skill in:name stars:>500`
    2.  `skill in:description stars:>500`
-   Results are merged, deduplicated, and ranked.
-   A custom **relevance score** is calculated based on keywords like `prompt`, `agent`, `workflow`, `instruction`, and `mcp`.
-   Each skill repository displays a badge: **Core Skill**, **Strong Match**, **Skill-Adjacent**, or **Related**.

## 🔧 Local Development

To run this project locally:

1.  **Clone the repository**:
    ```bash
    git clone https://github.com/your-username/github-dashboard.git
    cd github-dashboard
