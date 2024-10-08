# Sankey Diagram

![image](https://github.com/user-attachments/assets/8ba8abed-ec0e-427c-9b83-c830227d710d)

I created this diagram to show employee movements between departments: movements from one department to another (grey), new employees (blue), and those who left the company (orange). Paths for those who remained in the same department are disabled (filtered out from the "data-links" data table).

If needed then remove this filter:
```
        {
          "type": "filter",
          "expr": "datum.loser!==datum.gainer.gainer"
        }
```
from "data-links" table to enable paths for those who remained in the same department.
Then edit "path-links" mark "stroke" properties by adding a test:
```
            {
              "test": "datum.loser==datum.gainer.gainer",
              "signal": "colorToDisplayPathsOfThoseWhoRemainedInTheSameDepartment"
            }
```
If needed then edit "opacity" propery as well.

It's just a template based on a specific use case. Feel free to modify final view of your chart.

---

Complete dashboard that uses this Sankey diagram: https://powerofbi.org/hr

![Power BI Dashboard - HR Cross-Function Mobility v4 (by Andrzej Leszkiewicz)](https://github.com/user-attachments/assets/ea4e3191-15bc-45da-8460-03bc264633a0)

---

Data sample is an extract from [Real World Fake Data (#RWFD) - HR Cross-Functional Mobility](https://sonsofhierarchies.com/real-world-fake-data-hr-cross-functional-mobility/) dataset
