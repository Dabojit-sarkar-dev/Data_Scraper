# Competitor Analysis Scraper

A robust backend system for scraping and comparing company data for competitor analysis with AI-powered data gathering,
real-time financial accuracy, and an enhanced user interface.

![Sample Comparison](https://via.placeholder.com/800x400?text=Competitor+Analysis+Dashboard+v2.3)

## Features

- **📊 Reliable Yahoo Finance Integration**: Primary financial data via the robust `yahoo-finance2` library.
- **💹 Real-Time Financial Data**: Live market cap and stock prices from CompaniesMarketCap.com (with improved redirect
  handling).
- **🤖 AI-Powered Data Collection**: Multi-tier AI integration with Gemini AI and Mistral AI.
- **📈 Advanced Company Analysis**: Financials, user metrics, strengths, weaknesses, market position.
- **🎯 Smart Visual Comparison**: Accurate charts with proper scaling and deterministic tie-breaking.
- **🔄 Intelligent Fallback System**: Multiple data sources ensure high availability.
- **🌐 Built-in UI**: Professional web interface with enhanced company search.
- **🔍 Enhanced Autocomplete**: Dropdown suggestions from ~170 top companies, alphabetically sorted, showing name and
  stock symbol.
- **📱 Responsive Design**: Mobile-friendly interface.
- **⚡ Fast Performance**: Efficient caching and intelligent source selection.

## ✨ Recent Updates

### 🆕 Latest Features (v2.3) - Current Version

- **Enhanced Autocomplete Dropdown**:
    - Suggestions from a pre-loaded list of ~170 top S&P 500-level companies.
    - Companies are alphabetically sorted for easy navigation.
    - Dropdown displays both company name and stock symbol (e.g., "Apple Inc. (AAPL)").
    - Improved UI hints for company search.
- **Deterministic Tie-Breaking Logic**:
    - Replaced random tie-breaking for metrics with equal values.
    - New Logic: 1. Higher Market Cap wins. 2. If Market Caps are also tied, company name appearing first alphabetically
      wins.
- **Improved Yahoo Finance Reliability**:
    - Switched primary Yahoo Finance data fetching to the more stable `yahoo-finance2` library.
    - Deprecated usage of the less reliable `yahoo-stock-api` library.
- **CompaniesMarketCap Scraper Fixed**:
    - Enhanced `makeHtmlRequest` function to intelligently follow HTTP 301/302 redirects, improving data retrieval
      success.
- **Codebase Cleanup**:
    - Removed several unnecessary files and scripts (e.g., old Node installers, Docker files, MongoDB test scripts) to
      streamline the project.
    - Corrected minor syntax issues in `enhanced-server.js`.

### 🔄 Previous Updates (v2.2)

- **Yahoo Finance API Primary**: Original enhancement of Yahoo Finance integration.
- **Improved Data Hierarchy**: Reorganized data source priority.
- **Enhanced Financial Coverage**: Better P/E ratios, EPS, revenue, and profit margin data.

### 🔄 Previous Updates (v2.1)

- **Real-Time Market Data**: Added CompaniesMarketCap.com integration.
- **Enhanced Accuracy**: Real-time market cap and stock prices.

### 🔄 Previous Updates (v2.0)

- **Gemini AI Integration**: Added Gemini for comprehensive company intelligence.
- **Fixed Chart Scaling**: Proper visualization of billions/millions/trillions.

## Quick Start

### Windows

1. Ensure Node.js (v16+ recommended) is installed.
2. Download or clone the repository.
3. Navigate to the project directory in your terminal.
4. Run `npm install` to install dependencies.
5. Double-click `run-enhanced-server.bat`.
6. Open your browser to the URL shown (typically http://localhost:9000).
7. Enter two company names (e.g., "Apple Inc.", "Microsoft Corporation") using the autocomplete suggestions.
8. View comprehensive analysis.

### Other Platforms

```bash
# Ensure Node.js (v16+ recommended) is installed
# Clone repository
git clone https://github.com/Dabojit-sarkar-dev/Competitor-Analysis-Scraper.git
cd Competitor-Analysis-Scraper

# Install dependencies
npm install

# Run with Node.js
node src/enhanced-server.js
```

## 🔑 API Keys Setup

For optimal performance, configure these API keys:

### Optional for Enhanced Features:
- **Gemini AI**: Get free key from [Google AI Studio](https://makersuite.google.com/app/apikey)
- **Mistral AI**: Get key from [Mistral AI Platform](https://console.mistral.ai/)
- **Alpha Vantage**: Get free key from [Alpha Vantage](https://www.alphavantage.co/support/#api-key)

**Note**: `yahoo-finance2` and CompaniesMarketCap work without API keys!

### Configuration Options:

#### Option 1: Direct Configuration (Recommended)
Edit `src/config.js`:
```javascript
// src/config.js
api: {
  gemini: {
    key: process.env.GEMINI_API_KEY || 'YOUR_GEMINI_KEY_HERE', // Updated placeholder
    enabled: true
  },
  mistral: {
    key: process.env.MISTRAL_API_KEY || 'YOUR_MISTRAL_KEY_HERE', // Updated placeholder
    enabled: true
  },
  alphaVantage: {
    key: process.env.ALPHA_VANTAGE_API_KEY || 'YOUR_ALPHA_VANTAGE_KEY_HERE' // Updated placeholder
  }
}
```

#### Option 2: Environment Variables

(Example for Windows, adapt for your OS)
```bash
set GEMINI_API_KEY=your_gemini_key_here
set MISTRAL_API_KEY=your_mistral_key_here
set ALPHA_VANTAGE_API_KEY=your_alpha_vantage_key_here
```

#### Option 3: Batch File (Windows)

Edit `run-enhanced-server.bat` and set your keys directly (less secure, for local testing only):
```batch
REM set GEMINI_API_KEY=your_gemini_key_here
REM set MISTRAL_API_KEY=your_mistral_key_here
REM set ALPHA_VANTAGE_API_KEY=your_alpha_vantage_key_here
```

## Screenshots

### Enhanced Company Search & Comparison

![Enhanced Company Search](https://via.placeholder.com/600x350?text=Enhanced+Company+Search+with+Dropdown)

### Financial Metrics with Deterministic Tie-Breaking

![Financial Charts](https://via.placeholder.com/600x300?text=Real-Time+Financial+Charts+v2.3)

## 🏗️ Tech Stack

- **Node.js**: JavaScript runtime environment.
- **Core HTTP Module**: Native Node.js HTTP server.
- **`yahoo-finance2`**: Primary source for Yahoo Finance financial data (reliable).
- **CompaniesMarketCap Scraper**: Real-time market cap/stock prices (redirect-aware).
- **Gemini AI & Mistral AI**: For AI-enhanced business intelligence.
- **Alpha Vantage API**: Additional financial data.
- **Wikipedia API**: Basic company info.
- **In-memory Database & Caching**: For speed.
- **HTML/CSS/JavaScript**: For the built-in UI.

## 📊 Data Source Hierarchy

The system uses an intelligent multi-tier fallback approach:

1. **🥇 `yahoo-finance2`** (Primary): Reliable financial data.
2. **🥈 CompaniesMarketCap** (Fallback 1): Real-time data, now with redirect handling.
3. **🥉 Gemini AI** (Fallback 2): Comprehensive AI analysis.
4. **🏅 Mistral AI** (Fallback 3): Alternative AI analysis.
5. **📊 Alpha Vantage** (Fallback 4): Structured financial info.
6. **📚 Wikipedia** (Fallback 5): Basic company descriptions/logos.

### 🚀 **Why This Hierarchy Works Better:**

- **Reliable Yahoo Finance Primary**: `yahoo-finance2` offers better stability.
- **Improved Real-Time Backup**: CompaniesMarketCap scraper is more robust.
- **Consistent Tie-Breaking**: Clear logic for tied metric values.
- **AI Intelligence & Broad Coverage**: Maintained.

## API Reference

(API endpoints remain largely the same, refer to `/api/health` for live status)

### Companies
| Endpoint                     | Method | Description                                                             |
|------------------------------|--------|-------------------------------------------------------------------------|
| `/api/companies`             | GET    | List all companies in the *local cache* (primarily from `db.companies`) |
| `/api/companies/:identifier` | GET    | Get details for a specific company (multi-source, AI-enhanced)          |

### Comparisons
| Endpoint                                          | Method | Description                                       |
|---------------------------------------------------|--------|---------------------------------------------------|
| `/api/comparison?company1=:name1&company2=:name2` | GET    | Compare two companies (multi-source, AI analysis) |
| `/api/comparison/chart/finances`                  | GET    | Financial performance chart data                  |
| `/api/comparison/chart/userMetrics`               | GET    | User metrics chart data                           |

### Health Checks
| Endpoint      | Method | Description                                       |
|---------------|--------|---------------------------------------------------|
| `/api/health` | GET    | Server health + API status + data source priority |

### Example Requests

(URLs and port number might vary based on your local setup)
```bash
# Get company data
curl "http://localhost:9000/api/companies/Tesla"

# Compare companies
curl "http://localhost:9000/api/comparison?company1=Apple%20Inc.&company2=Microsoft%20Corporation"
```

## 🚀 Running the Server

### Windows (Recommended)

1. Install Node.js.
2. `npm install` in the project root.
3. `run-enhanced-server.bat`

### Command Line (Any Platform)
```bash
# Navigate to project directory
cd path/to/competitor-analysis-scraper
# Install dependencies
npm install
# Run the enhanced server
node src/enhanced-server.js
```

### Server Features:

- ✅ Automatic port selection (default 9000, then fallbacks).
- ✅ Enhanced autocomplete with ~170 top companies.
- ✅ Deterministic tie-breaking for comparisons.
- ✅ More reliable Yahoo Finance data fetching.
- ✅ Improved CompaniesMarketCap scraping.

## 📁 Project Structure (Simplified)

```
├── logs/                      # Runtime log files
├── src/
│   ├── config.js              # API keys & server configuration
│   ├── enhanced-server.js     # Main application logic
│   └── simple-server.js       # Legacy basic server
├── public/                    
│   └── popular_companies.json # Data for autocomplete (name & symbol)
├── run-enhanced-server.bat    # Main Windows launcher
├── run-simple-server.bat      # Legacy Windows launcher
├── package.json               # Project dependencies & scripts
├── README.md                  # This documentation
└── FRONTEND_GUIDE.md          # Guide for UI integration
```

*(Removed `ENTERPRISE_ROADMAP.md` for now as it might be outdated, can be re-added if current)*

## 🔧 Recent Fixes & Enhancements (Summary - v2.3)

- ✅ **UI & Data**: Enhanced autocomplete with ~170 top companies (name & symbol), alphabetical sort, UI hints.
- ✅ **Comparison Logic**: Deterministic tie-breaking (Market Cap > Alphabetical).
- ✅ **Data Source Reliability**:
    - Switched to `yahoo-finance2` for Yahoo Finance data.
    - Improved `CompaniesMarketCap` scraper to handle redirects.
- ✅ **Code Health**: Removed unused files, fixed minor syntax errors.

## 🌟 Data Quality & Coverage

(Highlights - refer to previous sections for full details)

### **📈 Financial Metrics (`yahoo-finance2` & CompaniesMarketCap)**

- Comprehensive stock data, financial ratios, market performance.
- Live market cap & stock prices.

### **🎯 Strategic Analysis (AI-Powered)**

- SWOT, competitive positioning, recent developments.

## 🔍 Troubleshooting

| Issue                                     | Solution                                                                                                    |
|-------------------------------------------|-------------------------------------------------------------------------------------------------------------|
| **Yahoo Finance data unavailable**        | Switched to more reliable `yahoo-finance2`. Check API keys for AI sources if fallback data is also missing. |
| **CompaniesMarketCap data missing**       | Redirect handling improved. Site structure changes can still affect it.                                     |
| **Slow initial response for new company** | Expected, as data is fetched from multiple sources including AI. Cached responses are faster.               |
| **Tied metric shows a winner**            | Tie broken by: 1. Higher Market Cap, 2. Alphabetical name. Reason now in API response.                      |
| **API rate limits (Alpha Vantage)**       | System has multiple fallbacks. Alpha Vantage is a lower-tier source.                                        |

### API Key Verification:

Visit `http://localhost:9000/api/health` to check data source status. The `dataSourcePriority` now reflects
`yahoo-finance2` as primary for Yahoo data.

## 🎯 **What Makes This Special (v2.3):**

### **🔥 Unique Features:**

- **Reliable Yahoo Finance Primary**: Using `yahoo-finance2`.
- **Robust 6-Tier Fallback System**: Now more resilient.
- **Smart Autocomplete**: Top ~170 companies with symbols, alphabetically sorted.
- **Deterministic Comparisons**: Clear, logical tie-breaking.

### **💡 Perfect For:**

(Remains the same: Financial Analysis, Investment Research, etc.)

## 🤝 Contributing

(Contribution guidelines remain the same)

## 📄 License

MIT License.

## 🙏 Acknowledgments

- **`yahoo-finance2` maintainers** for a robust library.
- (Other acknowledgments remain largely the same)

---

**Ready to analyze competitors with enhanced reliability and UI?**

1. `npm install`
2. Run `run-enhanced-server.bat` (Windows) or `node src/enhanced-server.js`
3. Visit http://localhost:9000 🚀

### 🎉 **Experience the power of refined data fetching and smarter comparisons!**
