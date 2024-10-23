# DevOps Project : Monitoring-grafana-blackbox
![image](https://github.com/user-attachments/assets/ce2141ef-d435-4302-878a-27e6a32c8c0b)

* **Purpose:** In this project we will setup the Grafana-blackbox locally using Docker Compose. And we"ll configure some URLs to monitor them on the Grafana dashbpard.
* **Prerequisites:**
1. OS: Ubuntu
2. Docker
3. GitHub 
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

* Now make up all the containers by running the command.
```
docker-compose up -d
```
![image](https://github.com/user-attachments/assets/58b1eb05-7b19-4f45-a504-4780e1c8d793)

* Open the url of Prometheus with (your system) IP and Port.
  

![image](https://github.com/user-attachments/assets/59f76294-2ed9-422d-99a8-dbf2bf2fbeca)


![image](https://github.com/user-attachments/assets/f9502341-7bc9-4a85-a43b-0e16f8e94625)

* Use "admin" as user and the password for login.

![image](https://github.com/user-attachments/assets/459ab1c9-3feb-4dba-922a-a250c8572576)

![image](https://github.com/user-attachments/assets/5cd33562-550e-4474-9fce-b3473dd2ca79)

* Configure the data source which is Prometheus.

![Screenshot 2024-10-22 185813](https://github.com/user-attachments/assets/74e61dfa-911e-4ef6-9982-a1a4062ce068)


* Import a new dashboard. Use Dashboard id 13659
  
![Screenshot 2024-10-22 162944](https://github.com/user-attachments/assets/1d4fe4d3-7087-429f-b3d6-1bcae862ab3b)


![Screenshot 2024-10-22 173254](https://github.com/user-attachments/assets/7eadecb0-5ab3-408a-9a90-b07bac79f1d9)


![image](https://github.com/user-attachments/assets/b0ffc259-cdd1-4ccb-af57-8cd3c5f61275)

* Now let's check the URLs added for monitoring in the "prometheus.yml" file.

![Screenshot 2024-10-23 120833](https://github.com/user-attachments/assets/62e34d36-7278-4bff-a6a5-74387c738858)

```
vim promethereus.yml
```

![Screenshot 2024-10-23 114804](https://github.com/user-attachments/assets/b610f7c8-e734-4c10-8ff8-0e7acacda533)

* If we need to add more URL in the list to moniter then we have to add the domain name in the same file under "tragets" section. For example I'm adding a new URL.

![Screenshot 2024-10-23 121836](https://github.com/user-attachments/assets/1123b82e-11d2-4727-b0d2-33fbf51b3311)

* After adding the new URL, save the file and restart the prometheus container.

```
docker-compose restart prometheus
```
* Now refresh the Grafana dashboard page and the new URL will reflect in the list as shown in the snapshot.

![Screenshot 2024-10-23 122426](https://github.com/user-attachments/assets/2c3d48b3-a703-44ac-936f-818babdcffb3)







---------------------

* These are the other snapshots of different testing machine.

![Grafana-dashboard](https://github.com/user-attachments/assets/5c89ab28-9c5d-4a8d-aeb0-d00f306931ff)

![Promethus](https://github.com/user-attachments/assets/1a6cc78c-a4cc-4df7-a51c-3293ae4c7e6e)

![grafan-blackbox](https://github.com/user-attachments/assets/6988c6e8-8eed-42e9-80a7-3e8247e884b3)







