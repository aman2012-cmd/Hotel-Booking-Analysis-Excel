## 📊 Hotel Booking Cancellation Analysis (Excel Project)

## 📌 Project Overview
This project analyzes hotel booking data from Kaggle to uncover insights about cancellations, guest behavior, and booking patterns.
The dataset was explored and transformed in Microsoft Excel, and custom calculated fields were created to enhance the analysis.

## 📂 Dataset
- Source: Kaggle (Hotel Booking Dataset)
- Rows (hotel_booking sheet): 119,390
- Columns (hotel_booking sheet): 14

## Key Columns
- `hotel` – Type of hotel (Resort or City)
- `is_canceled` – Whether the booking was canceled (1) or not (0)
- `arrival_date_year`, `arrival_date_month` – Arrival details
- `adults`, `children`, `babies` – Number of guests per booking
- `country` – Guest country
- `reserved_room_type`, `assigned_room_type` – Room allocation details
- `reservation_status`, `reservation_status_date` – Final booking status
- `room_status` – Custom column (Desired/Un-Desired)
- `guest_type` – Custom column (Single/Couples/Family)

## 🛠️ Custom Columns

## room_status
```excel
=IF([@[reserved_room_type]]=[@[assigned_room_type]],"Desired","Un-Desired")
```
- Desired → Guest got the reserved room type
- Un-Desired → Guest was assigned a different room type

## guest_type
```excel
=IF(AND(D3=2,E3=0,F3=0),"Couples",IF(AND(D3=1,E3=0,F3=0),"Single","Family"))
```
- Couples → 2 Adults, no children/babies
- Single → 1 Adult, no children/babies
- Family → Any other combination

## 📊 Sheets in the Project
1. hotel_booking → Raw + transformed data with custom columns.
2. Pivot → Pivot analysis summarizing total guests and cancellations.
3. Dashboard → Interactive Excel dashboard (visual representation of booking insights).

## 🔎 Highlights / Insights
- Couples form a large share of bookings.
- Many cancellations observed, highlighting the importance of customer behavior analysis.
- "Un-Desired" room allocation could influence guest satisfaction and cancellations.

## 🚀 How to Use
1. Open the Excel file `DataScienceProjectOfExcel_HotelCancellation.xlsx`.
2. Explore the `hotel_booking` sheet for raw + processed data.
3. Check the `Pivot` sheet for aggregated insights.
4. Navigate to the `Dashboard` sheet for visual analysis.

## 📈 Future Improvements
- Automating data cleaning with Python.
- Creating interactive dashboards using Power BI / Tableau.
- Extending analysis with ML models for cancellation prediction.
