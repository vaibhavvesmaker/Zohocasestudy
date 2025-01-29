# 🚀 Zoho One for SaaS Project Management: Automation & Analytics  

## 📌 Overview  
This project demonstrates how **Zoho One** tools (Projects, CRM, Analytics, Flow) solve **real-world SaaS project challenges** for a fictional company, **CloudFlow Solutions**. It includes:  
- **Automated task tracking** using Python and Zoho APIs.  
- **Client feedback integration** between Zoho CRM and Projects.  
- **Predictive analytics** for project delays.  

## 🔧 Tools Used  
- **Zoho Projects**: Task management & Gantt charts.  
- **Zoho CRM**: Client feedback tracking.  
- **Zoho Analytics**: Real-time dashboards.  
- **Python**: API automation & data analysis.  

---

## 🎯 **Problem Statement**  
**CloudFlow Solutions**, a SaaS startup, struggled with:  
1. **Missed deadlines** due to poor task visibility.  
2. **Low client satisfaction** from delayed feature requests.  
3. **Manual reporting** consuming 15+ hours/week.  

## 🛠️ **Solution Architecture**  
![Workflow Diagram](docs/workflow_diagram.png)  

### **Phase 1: Zoho Projects Setup**  
- Migrated tasks from Excel to Zoho Projects using `project_tasks_sample.csv`.  
- Created Agile boards and Gantt charts for sprint planning.  

### **Phase 2: Automation with Python**  
**Script**: `scripts/zoho_api_integration.py`  
- **Auto-Update Task Status**:  
  ```python
  import requests
  
  def update_task_status(task_id, status):
      api_key = "YOUR_ZOHO_API_KEY"
      url = f"https://projectsapi.zoho.com/rest/v1/tasks/{task_id}"
      headers = {"Authorization": f"Zoho-oauthtoken {api_key}"}
      data = {"status": status}
      response = requests.put(url, headers=headers, json=data)
      return response.json()
  
  # Example: Mark task 456 as "In Progress"
  print(update_task_status(456, "In Progress"))
