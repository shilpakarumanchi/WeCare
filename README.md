# Overview
This analysis explores key patterns and anomalies in shift activity and performance on the WeCare Medical Staffing platform across three core areas, to support the team for a deeper understanding of business outcomes:
1.	Shift Popularity - Trends in shift views, availability, and shifts worked.
2.	Earning Insights - Top performing months, days of the week, and time slots.
3.	Data Anomalies - Misaligned slot types, shifts lasting for zero hours, claimed shifts deleted after their start time, offers with revenue loss, and multiple shift claims.

# Data processing
- Original dataset in Excel can be found [here](https://github.com/shilpakarumanchi/WeCare/blob/56df8f77df12083a9a22cc7fe28fc0688aa5fe9f/connect_shift_python.xlsx)
- Data analysis in Python can be found [here](https://github.com/shilpakarumanchi/Avada-e-commerce/blob/a087a4413d174ad601b6fcfbed092c1fd3b2eef5/Avada_ecommerce_Analysis_git.xlsx)


# Executive Summary
•	A total of 19,900 shifts were posted by 132 workplaces and are available between September 22, 2024, and January 20, 2025.
•	63% (12,541) of the posted shifts have been fulfilled, generating revenue of $612,578.
•	Weekends accounted for the largest share of revenue at $234,141 (38%).
•	Oct ‘24 was the highest-earning month, contributing to $200,744 in revenue (33%).
•	My investigation indicates a need to strategically boost weekend shift claims while enhancing shift conversion rates across all days of week.
•	Amongst other anomalies, there were 192 (1%) post-claim deletions by workplaces, potentially impacting worker trust, an issue reflected in reviews citing shift reliability.

### Shift Volume Peaked in Oct ’24, Then Gradually Declined   
![image](https://github.com/user-attachments/assets/19e382ac-aaee-4fce-af6e-d890715b9f21)


# Insights Deep Dive
## Descriptive Analysis
•	A total of 19,900 shifts, that were posted by 132 workplaces between 29 July ‘24 & 21 Jan ‘25, covering work periods from 22 Sep ‘24 to 20 Jan ’25.
•	A total of 10,291 workers used the app, and 12,541 shifts were worked.
•	Each workplace posted an average of 56 shifts, with shifts ranging from 1 to 1,779.
•	Shifts were typically created 2.5 to 3 days before their scheduled start time, with lead times extending up to 75 days.
•	Each shift was viewed an average of 3 times, with views ranging from as few as 1 to as many as 335.
•	On average, 161 shifts were available, and 102 shifts were worked per day.
* I used the median to represent the average of any metrics with skewed distributions.
## Weekday Vs Weekend performance
•	Shift views peak on Fridays (46,151) and Saturdays (42,670).
•	Weekend shifts have the highest engagement, totaling 4,457 worked shifts.
•	Tuesdays, Wednesdays, and Thursdays record the lowest number of worked shifts, averaging around 1,500 each.
•	Despite volume differences, the conversion rate from available to worked shifts was highest for Tuesday, Wednesday (67%) and lowest for Friday, Saturday (60%).

### More Shifts Worked during the Weekend
![image](https://github.com/user-attachments/assets/12c6a2a7-33ce-4065-be58-02bb47862e9b)

## Charge Rate Vs Pay Rate
•	On average, each shift was charged $31 per hour to the workplace and paid out at $23 per hour to the worker, generating an average revenue of $8 per hour for WeCare Staffing.
•	However, there are 24,094 shift offers where the pay rate exceeded the charge rate, resulting in a potential revenue loss for WeCare Staffing.
•	Pay rates across different views of the same shift vary up to $1 per hour. However, in certain cases, the difference can be as high as $26 per hour.
### 24,094 Offers with Revenue Loss
![image](https://github.com/user-attachments/assets/523022e4-1474-4640-9003-e01c60ab4206)

 
## Monthly Shift Volume & Revenues
•	Among the months with complete data (October, November, and December 2024), October recorded the highest shift volume with 5,771 shifts available & 3,517 worked, while November had the lowest with 4,436 available & 2,856 worked.
•	Despite its high volume, October had the lowest shift conversion rate (61%), whereas December saw the highest (67%).
•	October also generated the highest revenue, with $972,992 charged to workplaces and $772,246 paid to workers, resulting in a revenue of $200,744.
•	Gross revenue margin (revenue as a percentage of amount charged) ranged from 15% in December and January to 21% in September and October.

### October 2024 Leads in Shift Volume and in Revenue.
![image](https://github.com/user-attachments/assets/6b73db91-cbb8-462b-9e93-fa2a9fc3728a)
![image](https://github.com/user-attachments/assets/a880ea55-49fd-44ad-b0d3-51be6bedcc4b)


 
 
## Slot Types
•	Across the three time slots, the highest number of shifts were created for the PM slot (8,218), followed by AM (7,051), and then NOC (4,631).
•	On average, shifts across all three slots lasted 8 hours, with durations ranging from 0 to 18 hours, showing a similar distribution across slots.
•	Shift duration and charge rate per hour stays consistent across the three slot types and seven days of the week (Figure S1).
•	The interquartile range (25th-75th percentile) of shift starting times for AM shifts fall between 13:00 and 14:30, for PM shifts between 21:30 and 22:30, and for NOC shifts between 05:30 and 06:30.
•	However, these observed slot times do not align with standard shift start times commonly used in the healthcare and staffing industries, where AM shifts typically begin between 07:00 and 08:00, PM shifts between 15:00 and 16:00, and NOC shifts between 23:00 and 00:00.
### Slot Start Time Misalignment with Industry Standards
![image](https://github.com/user-attachments/assets/c5954eb6-c916-4209-8f10-c61e829a9bc4)

 
## Anomalies
I have identified some anomalies in the data that need to be addressed. This includes:
•	Shifts with zero-hour duration (Figure S1).
•	Inconsistencies in labeling slot types with respect to the time of start of the shift.
•	Offers with revenue loss.
•	Workplaces posted shifts after the shift had started (Figure S2).
•	Shifts deleted by workplaces after being claimed and after the start of the shift.
•	Multiple claims of a single shift (by different workers and by the same worker).
•	Multiple cancellations of a single shift (Figure S3).
•	No shows were also noted as verified implying that the shifts had been worked.
## Closing Remarks
This report aims to showcase my analytical capabilities from a business perspective, within a reasonable timeframe. It presents a high-level overview of key performance indicators (KPIs) such as Shift conversion rate & Gross revenue margins and identifies potential data anomalies. To derive precise metrics, a deeper understanding of the event chronology with respect to cases involving multiple claims, cancellations, and no-shows (which were also marked as worked shifts) is essential. Accurate values of the KPIs will require further data validation and cleaning, typically carried out iteratively in collaboration with team members, supervisors, or stakeholders.

## Supplementary Information
### Figure S1: Charge rate per hour and Duration of shift stays consistent across slot type & day of week.
![image](https://github.com/user-attachments/assets/5f7a7bd2-b175-4b38-a9c7-2a8710c9836f)

### Figure S2: Workplace Deletions After Shift Claim and Shift Commencement.
![Screenshot 2025-04-27 121343](https://github.com/user-attachments/assets/1ffccd60-eca1-4e66-92f5-53bb5f17dad0)
 
### Figure S3: Worker Shift Cancelations and No Shows.
 ![Screenshot 2025-04-27 121358](https://github.com/user-attachments/assets/9c4039c1-cb91-4a59-9670-367b45eb832d)


