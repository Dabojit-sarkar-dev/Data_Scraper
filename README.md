# Competitor Analysis Scraper

A robust backend system for scraping and comparing company data for competitor analysis with AI-powered data gathering
and real-time financial accuracy.

![Sample Comparison](https://via.placeholder.com/800x400?text=Competitor+Analysis+Dashboard)

## Features

- **🤖 AI-Powered Data Collection**: Multi-tier AI integration with Gemini AI (primary) and Mistral AI (fallback)
- **📊 Advanced Company Analysis**: Comprehensive data including financials, user metrics, strengths, weaknesses, and
  market position
- **💹 Real-Time Financial Data**: Live market cap and stock prices from CompaniesMarketCap.com (10,000+ companies)
- **📈 User Metrics**: Analyze customer base size, growth rates, and satisfaction scores
- **🎯 Smart Visual Comparison**: Accurate charts with proper billion/million/trillion scaling
- **🔄 Intelligent Fallback System**: Multiple data sources ensure high availability and accuracy
- **🌐 Built-in UI**: Professional web interface for instant company comparisons
- **📱 Responsive Design**: Mobile-friendly interface that adapts to all screen sizes
- **⚡ Fast Performance**: Efficient caching system with intelligent source selection

## ✨ Recent Updates

### 🆕 Latest Features (v2.1)

- **Real-Time Market Data**: Added CompaniesMarketCap.com integration for live financial data
- **Enhanced Accuracy**: Real-time market cap and stock prices for 10,000+ companies
- **Improved Coverage**: Better data availability with additional fallback source
- **No API Limits**: Free real-time data without rate restrictions

### 🔄 Previous Updates (v2.0)
- **Gemini AI Integration**: Primary data source providing comprehensive company intelligence
- **Fixed Chart Scaling**: Proper visualization of billions, millions, and trillions
- **Enhanced Data Quality**: More accurate financial metrics and user data
- **Smart Source Priority**: Multi-tier fallback hierarchy for maximum reliability
- **Improved Error Handling**: Better fallback mechanisms and data validation

## Quick Start

### Windows

1. Download or clone the repository
2. Double-click `run-enhanced-server.bat`
3. Open your browser to the URL shown (typically http://localhost:9000)
4. Enter two company names to compare (e.g., "Tesla", "Ford")
5. View comprehensive AI-powered analysis with real-time financial data

### Other Platforms

```bash
# Clone repository
git clone https://github.com/Dabojit-sarkar-dev/Competitor-Analysis-Scraper.git
cd Competitor-Analysis-Scraper

# Run with Node.js
node src/enhanced-server.js
```

## 🔑 API Keys Setup

For optimal performance, configure these API keys:

### Required for Full Features:
- **Gemini AI**: Get free key from [Google AI Studio](https://makersuite.google.com/app/apikey)
- **Mistral AI**: Get key from [Mistral AI Platform](https://console.mistral.ai/)
- **Alpha Vantage**: Get free key from [Alpha Vantage](https://www.alphavantage.co/support/#api-key)

### Configuration Options:

#### Option 1: Direct Configuration (Recommended)
Edit `src/config.js`:
```javascript
api: {
  gemini: {
    key: 'your_gemini_api_key_here',
    enabled: true
  },
  mistral: {
    key: 'your_mistral_api_key_here', 
    enabled: true
  },
  alphaVantage: {
    key: 'your_alpha_vantage_key_here'
  }
}
```

#### Option 2: Environment Variables
```bash
set GEMINI_API_KEY=your_gemini_key_here
set MISTRAL_API_KEY=your_mistral_key_here
set ALPHA_VANTAGE_API_KEY=your_alpha_vantage_key_here
```

#### Option 3: Batch File (Windows)
Edit `run-enhanced-server.bat` and uncomment:
```batch
set GEMINI_API_KEY=your_gemini_key_here
set MISTRAL_API_KEY=your_mistral_key_here
set ALPHA_VANTAGE_API_KEY=your_alpha_vantage_key_here
```

## Screenshots

### Company Comparison

![Company Comparison](https://via.placeholder.com/600x300?text=AI-Powered+Company+Analysis)

### Financial Metrics with Proper Scaling

![Financial Charts](https://via.placeholder.com/600x300?text=Accurate+Financial+Charts)

## 🏗️ Tech Stack

- **Node.js**: JavaScript runtime environment
- **Core HTTP Module**: Native Node.js HTTP server (no Express dependency)
- **Gemini AI**: Primary comprehensive data source (Google)
- **Mistral AI**: Secondary AI-enhanced data gathering
- **Alpha Vantage API**: Financial data and stock information
- **CompaniesMarketCap**: Real-time market cap and stock price data
- **Wikipedia API**: Basic company information and descriptions
- **In-memory Database**: Fast responses with intelligent caching

## 📊 Data Source Hierarchy

The system uses an intelligent multi-tier fallback approach for maximum accuracy:

1. **🥇 Gemini AI** (Primary): Comprehensive company analysis with financial data, metrics, strengths/weaknesses
2. **🥈 Mistral AI** (Fallback 1): Enhanced data gathering when Gemini fails
3. **🥉 Alpha Vantage** (Fallback 2): Professional financial data and stock information
4. **🎯 CompaniesMarketCap** (Fallback 2.5): **NEW** - Real-time market cap and stock prices (10,000+ companies)
5. **📚 Wikipedia** (Fallback 3): Basic company information and descriptions
6. **🏅 Yahoo Finance** (Final Fallback): Last resort for financial data

### 🚀 **Why This Hierarchy Works:**

- **AI Intelligence** (Gemini/Mistral) provides comprehensive analysis
- **Real-Time Data** (CompaniesMarketCap) ensures current financial accuracy
- **Professional APIs** (Alpha Vantage) offer structured financial data
- **Broad Coverage** (Wikipedia) fills information gaps
- **Reliability** (Yahoo Finance) ensures data availability

## API Reference

### Companies

| Endpoint                     | Method | Description                                                       |
|------------------------------|--------|-------------------------------------------------------------------|
| `/api/companies`             | GET    | List all companies in database                                    |
| `/api/companies/:identifier` | GET    | Get details for a specific company (AI-enhanced + real-time data) |

### Comparisons

| Endpoint                                          | Method | Description                                                   |
|---------------------------------------------------|--------|---------------------------------------------------------------|
| `/api/comparison?company1=:name1&company2=:name2` | GET    | Compare two companies with AI analysis + real-time financials |
| `/api/comparison/chart/finances`                  | GET    | Financial performance chart data                              |
| `/api/comparison/chart/usermetrics`               | GET    | User metrics chart data                                       |

### Health Checks

| Endpoint      | Method | Description                                       |
|---------------|--------|---------------------------------------------------|
| `/api/health` | GET    | Server health + API status + data source priority |

### Example Requests

```bash
# Get company data (AI-enhanced + real-time)
curl "http://localhost:9000/api/companies/Tesla"

# Compare companies with real-time financial data
curl "http://localhost:9000/api/comparison?company1=Apple&company2=Microsoft"

# Get financial chart data
curl "http://localhost:9000/api/comparison/chart/finances?company1=Google&company2=Meta"
```

## 🚀 Running the Server

### Windows (Recommended)

```batch
run-enhanced-server.bat  # Full AI-powered version with real-time data
```

### Command Line (Any Platform)

```bash
# Navigate to project directory
cd path/to/competitor-analysis-scraper

# Run the enhanced server with AI features + real-time data
node src/enhanced-server.js
```

### Server Features:
- ✅ Automatic port selection (9000, 9001, 9002, etc.)
- ✅ Graceful shutdown and cleanup
- ✅ Real-time logging and monitoring
- ✅ API key validation and warnings
- ✅ Multiple data source integration

## 📁 Project Structure

```
├── logs/                      # Automatic log files
├── src/
│   ├── config.js              # API keys and configuration
│   ├── enhanced-server.js     # Main AI-powered server with real-time data
│   ├── simple-server.js       # Basic server (legacy)
│   ├── controllers/           # Request handlers
│   ├── models/                # Data models
│   ├── routes/                # API routes
│   ├── services/              # AI and data services
│   └── utils/                 # Utilities and helpers
├── public/                    # Static web assets
├── run-enhanced-server.bat    # Windows launcher (AI + real-time enabled)
├── run-simple-server.bat      # Basic launcher
└── README.md                  # This documentation
```

## 🔧 Recent Fixes & Enhancements

### Real-Time Data Integration (v2.1.0)

- ✅ **CompaniesMarketCap Integration**: Live market cap data for 10,000+ companies
- ✅ **Real-Time Accuracy**: Current stock prices and market valuations
- ✅ **No API Limits**: Free access to real-time financial data
- ✅ **Smart Name Processing**: Automatic company name normalization for URL generation
- ✅ **Seamless Fallback**: Integrates smoothly with existing data sources

### Chart Visualization Fix (v2.0.1)
- ✅ **Proper Scaling**: Fixed billion/million/trillion chart scaling issue
- ✅ **Accurate Proportions**: Charts now correctly show value relationships
- ✅ **Unit Conversion**: Smart handling of T (trillion), B (billion), M (million)
- ✅ **Visual Improvements**: Better bar sizing and minimum widths

### AI Integration (v2.0.0)
- ✅ **Gemini AI Primary**: Most comprehensive company data source
- ✅ **Smart Fallbacks**: Automatic failover between data sources
- ✅ **Enhanced Accuracy**: Better financial and user metrics
- ✅ **Source Tracking**: Know which AI/source provided your data

## 🌟 Data Quality & Coverage

The system provides exceptionally rich company data including:

### **📈 Financial Metrics**

- **Real-Time Market Cap**: Live data from CompaniesMarketCap (10,000+ companies)
- **Current Stock Prices**: Up-to-date pricing information
- **Financial Ratios**: P/E ratios, EPS, profit margins
- **Revenue Data**: Annual revenue and growth metrics

### **👥 User Analytics**

- **Customer Counts**: User base size and demographics
- **Growth Rates**: User acquisition and retention metrics
- **Satisfaction Ratings**: Customer satisfaction scores

### **🎯 Strategic Analysis**

- **SWOT Analysis**: Strengths, weaknesses, opportunities, threats
- **Competitive Positioning**: Market position and competitive advantages
- **Recent Developments**: Latest news and market movements

### **🏢 Company Intelligence**

- **Corporate Details**: Founded date, headquarters, leadership
- **Product Portfolio**: Main products and services with ratings
- **Market Presence**: Industry classification and market segment

## 🔍 Troubleshooting

| Issue                       | Solution                                                       |
|-----------------------------|----------------------------------------------------------------|
| **Chart scaling wrong**     | ✅ **Fixed in v2.0.1** - Charts now properly scale B/M/T values |
| **Outdated financial data** | ✅ **Fixed in v2.1** - Real-time data from CompaniesMarketCap   |
| **Limited company data**    | Configure Gemini API key for comprehensive AI analysis         |
| **API rate limits**         | System automatically falls back to other sources               |
| **Port conflicts**          | Server tries multiple ports automatically (9000-9003)          |
| **Slow initial response**   | First AI requests take 3-5 seconds (normal)                    |
| **No Gemini data**          | Check API key in config.js or environment variables            |
| **Missing real-time data**  | CompaniesMarketCap automatically provides fallback data        |

### API Key Verification:

Visit `http://localhost:9000/api/health` to check all data sources:

```json
{
  "apis": {
    "gemini": true,           // ✅ Gemini AI working
    "mistral": true,          // ✅ Mistral AI working  
    "alphaVantage": true      // ✅ Alpha Vantage working
  },
  "dataSourcePriority": [
    "Gemini AI",
    "Mistral AI", 
    "Alpha Vantage",
    "CompaniesMarketCap (Real-time)",  // ✅ NEW
    "Wikipedia",
    "Yahoo Finance (fallback)"
  ]
}
```

## 🎯 **What Makes This Special:**

### **🔥 Unique Features:**

- **AI + Real-Time Hybrid**: Combines AI intelligence with live financial data
- **Multi-Source Accuracy**: 6-tier fallback system ensures data availability
- **No Rate Limits**: CompaniesMarketCap provides unlimited real-time access
- **Comprehensive Coverage**: 10,000+ companies with live market data
- **Zero Configuration**: Real-time data works out-of-the-box (no API keys needed)

### **💡 Perfect For:**

- **Financial Analysis**: Real-time market cap and pricing data
- **Investment Research**: Comprehensive company intelligence
- **Competitive Analysis**: Side-by-side comparisons with live data
- **Market Monitoring**: Track real-time market movements
- **Academic Research**: Rich datasets for financial studies

## 🤝 Contributing

Contributions welcome! Areas of high interest:

- Additional real-time data sources
- New AI integrations
- Enhanced visualization types
- Performance optimizations
- Alternative financial data sources

1. Fork the repository
2. Create feature branch: `git checkout -b feature/amazing-feature`
3. Commit changes: `git commit -m 'Add amazing feature'`
4. Push to branch: `git push origin feature/amazing-feature`
5. Open Pull Request

## 📄 License

MIT License - see [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **Google Gemini AI** for comprehensive company intelligence
- **Mistral AI** for enhanced data gathering capabilities
- **Alpha Vantage** for professional financial market data
- **CompaniesMarketCap.com** for real-time market cap and stock price data
- **Wikipedia** for open company information
- All contributors and users providing feedback

---

**Ready to analyze competitors with real-time data?** Run `run-enhanced-server.bat` and visit http://localhost:9000 🚀

### 🎉 **Experience the difference real-time financial data makes!**
