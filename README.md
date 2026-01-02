# Daily Weather Reports with OpenWeather API, Google Sheets, and Gmail

### 🌦️ Automated Daily Weather Tracker & Reporter (n8n | OpenWeather | Google Sheets | Gmail)

This workflow fetches real-time weather data from the OpenWeather API, stores it in a Google Sheet, formats it into a beautifully styled HTML report and emails it to recipients automatically every day at 10:00 AM. It helps teams track and monitor daily weather trends and optionally correlate them with energy production or field operations.

---

## 🎯 Who's it for?

- Renewable energy teams monitoring solar/wind energy output vs weather.
- Facility or operations managers requiring daily climate updates.
- Researchers or analysts logging environmental metrics.
- Any team needing automated, daily weather reports by email.

---

## 🛠 Requirements

- **n8n account** (self-hosted or cloud)
- **OpenWeather API key** (free or paid)
- **Google account** with access to:
  - Google Sheets
  - Gmail
- **A valid Google Sheet** created with the following headers (columns):
  - Country, Location, Latitude, Location Longitude, Temperature (°C), Feels Like (°C), Min Temp (°C), Max Temp (°C), Humidity (%), Pressure (hPa), Sea Level (hPa), Ground Level (hPa), Visibility (m), Wind Speed (m/s), Wind Direction (°), Wind Gust (m/s), Cloudiness (%), Sunrise (UTC), Sunset (UTC), Date Time (UTC).

---

## 🧠 How it works?

1. **Schedule Trigger:** The workflow begins with a Schedule Trigger set to run at 10:00 AM IST daily.
2. **OpenWeather API:** It calls the OpenWeather API to fetch weather metrics for a predefined location.
3. **Google Sheets Logging:** The data is passed to a Google Sheets node named "Append Weather to Sheet", which stores all key values into a structured spreadsheet.
4. **HTML Generation:** A Set or Function node generates a clean, styled HTML email using inline CSS and the weather values.
5. **Gmail Delivery:** Finally, a Gmail node sends this report to recipients with a clear subject line and formatted body.

---

## 🔧 How to set up?

1. **Import Workflow:** Create/Open your n8n instance and upload the workflow.
2. **Connect Credentials:**
   - Google Sheets (OAuth2)
   - Gmail (OAuth2)
3. **Configure API:** Set your OpenWeather API key in the HTTP Request node (`api.openweathermap.org`).
4. **Set Location:** Replace latitude/longitude in the request URL as per your location.
5. **Link Sheet:** Link your Google Sheet and define the correct tab name and headers.
6. **Recipient Settings:** Configure recipient email(s) in the Gmail node.
7. **Deploy:** Enable the workflow and test.

---

## ✨ How to customize?

- **Change timing:** Adjust the scheduled time in the Schedule Trigger node.
- **Update location:** Modify the location coordinates in the OpenWeather API URL.
- **Style reports:** Update the HTML template with different formatting or company branding.
- **Multi-channel:** Extend the workflow with Slack, Notion, or Telegram alerts.
- **Data Correlation:** Add a second sheet for energy output to correlate with weather.

---

## ➕ Add-ons

- Integrate with a solar energy API to track power production alongside weather.
- Post weather summaries to Notion, Slack, or internal dashboards.
- Generate visual charts in Google Sheets over time using the collected data.
- Trigger alerts when specific thresholds are exceeded (e.g., wind gust > 10 m/s).

---

## 📈 Use Case Examples

- **Solar farm reporting:** Monitor daily weather impact on solar panel output.
- **Logistics planning:** Notify teams of visibility or wind risks before dispatch.
- **Site operations:** Send forecasts to maintenance or ground staff.
- **Academic logging:** Track atmospheric data over time for research.

---

## 🧯 Troubleshooting Guide

| Issue                    | Possible Cause                  | Solution                                              |
| :----------------------- | :------------------------------ | :---------------------------------------------------- |
| **Email not sent**       | Gmail credentials not connected | Reconnect Gmail account via n8n credential manager    |
| **Weather data missing** | API key invalid or URL format   | Verify OpenWeather API key and URL latitude/longitude |
| **Sheet not updating**   | Incorrect spreadsheet ID/tab    | Double-check spreadsheet ID and sheet name in node    |
| **HTML renders poorly**  | Broken tags in HTML             | Test output HTML separately in a browser/preview tool |

---

## 📞 Need Assistance?

If you need assistance setting up or customizing this workflow, feel free to reach out. We're here to help!

👉 **Contact WeblineIndia** | Experts in workflow automation and environmental data monitoring.
