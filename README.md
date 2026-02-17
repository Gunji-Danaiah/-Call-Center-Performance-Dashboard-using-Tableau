# 📞 Call Center Performance Dashboard

## 📊 Project Overview
An interactive Tableau dashboard designed to analyze call center performance, agent productivity, and sales conversion rates. This dashboard provides business stakeholders with actionable insights through intuitive visualizations and interactive filters.

<img width="637" height="480" alt="Screenshot 2026-02-17 124602" src="https://github.com/user-attachments/assets/ed1f5967-0230-4156-93ce-aaab0202e02a" />


## 🎯 Objective
- Design an interactive dashboard for business stakeholders
- Track key call center metrics and KPIs
- Enable data-driven decision making
- Provide agent performance insights

## 📁 Dataset
- **Source**: Custom call center dataset
- **Records**: 1,000 call entries
- **Fields**: 8 columns including Agent info, Call details, Sales data

### Data Structure
| Column | Description | Data Type |
|--------|-------------|-----------|
| AgentID | Unique agent identifier | Integer |
| CallID | Unique call identifier | Integer |
| CustomerID | Customer identifier | Integer |
| PickedUp | Call answered (1) or not (0) | Binary |
| Duration | Call length in seconds | Integer |
| ProductSold | Product sold (1) or not (0) | Binary |
| Agent_Name | Agent full name | String |
| Header | Metadata | String |

## 🛠️ Tools Used
- **Tableau Public** (Free version)
- **GitHub** for version control
- **PowerPoint** for presentation

## 📈 Key Performance Indicators (KPIs)

### Primary KPIs
1. **Total Calls**: Overall call volume (COUNT of CallID)
2. **Answer Rate**: Percentage of calls answered (SUM(PickedUp)/COUNT(CallID))
3. **Products Sold**: Total sales conversions (SUM(ProductSold))
4. **Conversion Rate**: Sales per answered call (SUM(ProductSold)/SUM(PickedUp))

### Secondary Metrics
- Average Call Duration
- Call Distribution by Length
- Agent Performance Rankings

## 🎨 Dashboard Components

### 1. KPI Cards (Top Row)
- **Total Calls**: 1,000 total calls analyzed
- **Answer Rate**: [69.62 %] call pickup rate
- **Products Sold**: [2089 #] total sales
- **Conversion Rate**: [30.2 %] conversion rate

### 2. Agent Performance Visualizations
- **Sales by Agent**: Bar chart showing total sales per agent
- **Answer Rate by Agent**: Percentage of calls answered by each agent
- **Conversion Rate by Agent**: Sales effectiveness per agent

### 3. Call Analysis Charts
- **Call Duration Distribution**: Histogram showing call length patterns
- **Call Duration by Agent**: Average call time per agent

### 4. Interactive Elements
- **Agent Filter**: Dropdown to select specific agents
- **Cross-filtering**: Click charts to filter related data
- **Tooltips**: Detailed information on hover

## 🔧 Calculated Fields Created

```tableau
// Answer Rate
SUM([PickedUp]) / COUNT([CallID])

// Conversion Rate
SUM([ProductSold]) / SUM([PickedUp])

// Duration in Minutes
[Duration] / 60

// Call Category
IF [Duration] = 0 THEN "No Answer"
ELSEIF [Duration] < 60 THEN "Very Short (<1 min)"
ELSEIF [Duration] < 180 THEN "Short (1-3 min)"
ELSEIF [Duration] < 300 THEN "Medium (3-5 min)"
ELSE "Long (>5 min)"
END

## Author
Danaiah GUnji
