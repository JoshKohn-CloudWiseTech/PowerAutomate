# Holiday and Event Reminder from SharePoint Calendar

This Power Automate flow automates notifications for upcoming **events** and **public holidays** by integrating SharePoint, Microsoft Teams, Outlook, and Planner. It helps Shared Services staff stay informed and prepared for scheduled calendar items. 

---

## 📅 Trigger

- **Recurrence**: Daily at 8:00 AM (E. Australia Standard Time)

---

## 📥 Data Source

- **SharePoint Calendar**: `pj-CNS-SharedServices-team`
- **Fields Used**:
  - `Title`
  - `Start` (Date)
  - `Category` (Choice: `Public Holiday` or `Event`)

---

## 🔍 Flow Logic

### 1. **Get Items**
- Retrieves all calendar entries from the SharePoint list.

### 2. **Filter Events in the Next 7 Days**
- Filters items where `Start` date is 7 days from today.

### 3. **Send Notifications for Upcoming Events**
- **Email** to `Distribution Group`
- **Teams message** to `Microsoft Team`

### 4. **Filter Events for Tomorrow**
- Filters items where `Start` date is 1 day from today.

### 5. **Send Notifications for Tomorrow’s Events**
- **Email** and **Teams message** similar to above.

### 6. **Filter for Public Holidays**
- Filters tomorrow’s events where `Category = Public Holiday`.

### 7. **Create Planner Task**
- Creates a task in Microsoft Planner titled:
  ```
This flow is for demonstration purposes. Connection details and identifiers have been anonymized.
