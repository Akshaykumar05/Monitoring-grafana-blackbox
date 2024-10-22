# DevOps Project : Monitoring-grafana-blackbox
![image](https://github.com/user-attachments/assets/ce2141ef-d435-4302-878a-27e6a32c8c0b)

* **Purpose:** In this project we will setup the Grafana-blackbox locally using Docker Compose. And we"ll configure some URLs to monitor them on the Grafana dashbpard.
* **Prerequisites:** Before starting we need to confirm that we have Ubuntu and GitHub.
----------------
### Lets understand the basics of Grafana
* In today's world of **DevOps** and **CloudComputing**, Grafana has emerged as a go-to tool for monitoring and observability. Whether you're tracking server performance, application logs, or business metrics, Grafana makes it easy to create beautiful, real-time dashboards that provide actionable insights.

Here’s why Grafana should be in your toolkit: 
1. 📊 Customizable Dashboards - Tailor your views to what matters most. 
2. 🔗 Integrations Galore - From Prometheus to InfluxDB, it integrates with numerous data sources. 
3. 🔍 Powerful Alerts - Stay ahead of issues with Grafana’s alerting system. 
4. 🚀 Scalability - Suitable for startups to enterprise-level infrastructures.

### Ready to supercharge your monitoring and observability game? Try out Grafana and see the difference it makes!
---------------
## Grafans installation:
1. Run the following command.
   * Firstly we cloned the repository frm the GitHub.
   ```
   git clone https://github.com/cmjagtap/Website-Monitoring.git
   ```
   * Then we will see inside the repo and enter in the "Website-Monitoring" directory and from there we"ll go inside "blackbox_exporter-0.18.0.linux-amd64".
     
![image](https://github.com/user-attachments/assets/d4efd131-59f9-4c66-ad1d-bd5d801af885)

   * Now run the command inside 

   ```
   ./blackbox_exporter --config.file=blackbox.yml &> output.log &
   ```
![image](https://github.com/user-attachments/assets/c90334aa-0bd0-4347-9a82-50e969a779f5)

 * Now we checked the port status with the following command and got that Port 9115 is open for blackbox.
   ```
   ss -tulnp
   ```
   
![image](https://github.com/user-attachments/assets/6c4f553a-5950-4b10-b659-3f999a6a8ae7)

* Check the IP and hit on the browser with port 9115
  ```
  ip a
  ```

![image](https://github.com/user-attachments/assets/b2d4bdb5-165b-42c8-b036-b11c94fe007d)



---------------
![image](https://github.com/user-attachments/assets/788940ed-9e8c-492c-a8ff-9d46ad805a49)

![blackbox](https://github.com/user-attachments/assets/8ac7feb7-4e3e-4779-9bfe-b6b6921ca570)

![Promethus](https://github.com/user-attachments/assets/1a6cc78c-a4cc-4df7-a51c-3293ae4c7e6e)

![grafan-blackbox](https://github.com/user-attachments/assets/6988c6e8-8eed-42e9-80a7-3e8247e884b3)

![Grafana-dashboard](https://github.com/user-attachments/assets/5c89ab28-9c5d-4a8d-aeb0-d00f306931ff)







