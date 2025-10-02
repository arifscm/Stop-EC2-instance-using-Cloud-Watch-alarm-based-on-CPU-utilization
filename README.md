
# Stop EC2 Instance using CloudWatch Alarm (CPU Utilization)

This project demonstrates how to **automatically stop an EC2 instance** when its CPU utilization drops below a defined threshold using **Amazon CloudWatch Alarms**.

---

## 📘 Project Overview
- **Service Used**: Amazon CloudWatch, EC2, SNS (optional)
- **Goal**: Save cost and improve efficiency by automatically stopping idle instances.
- **Trigger**: CloudWatch Alarm on `CPUUtilization`.
- **Action**: EC2 Stop action when alarm condition is met.

---

## 📂 Google Drive Project PDF
🔗 [View Full Project PDF](https://drive.google.com/file/d/1XzCqLpEbnr2vTKucnUUWQtqL3frC858C/view?usp=drive_link)

---

## ⚙️ How It Works
1. **Enable Monitoring**
   - Use *Detailed Monitoring* (1-minute granularity) for accurate CPU metrics.

2. **Create CloudWatch Alarm**
   - Metric: `CPUUtilization`
   - Example Rule: `CPU < 10% for 15 minutes`
   - Action: Stop EC2 instance

3. **Add Notifications (Optional)**
   - Create an SNS topic and subscribe (email/SMS) for alerts before stop action.

---

## 🚀 Step-by-Step Setup
1. **Go to CloudWatch → Alarms → Create Alarm**
2. Select **EC2 → Per-Instance Metrics → CPUUtilization**
3. Define conditions:
   - Static threshold
   - Example: `< 10%` for 3 consecutive 5-min periods
4. Set **Alarm action** → `Stop this instance`
5. (Optional) Add SNS notification
6. Name your alarm and create it

---
## 📊 Alarm States

* **OK** → CPU within normal range
* **ALARM** → CPU below threshold → action triggered
* **INSUFFICIENT_DATA** → Metric not available

---

## ✅ Use Cases

* Stop dev/test servers after office hours
* Save costs by shutting down idle workloads
* Automate environment cleanup

````






👉 Do you want me to also **export this README.md file** so you can directly upload it to GitHub, or will you copy-paste it yourself?
```
