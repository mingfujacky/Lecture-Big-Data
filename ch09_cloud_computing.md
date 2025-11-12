---
marp: true
theme: default
class: default
size: 16:9
paginate: true
header: 國立陽明交通大學 電子與光子學士學位學程
headingDivider: 1
style: |
  section::after {
    content: attr(data-marpit-pagination) '/' attr(data-marpit-pagination-total);
  }
  
  .columns {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 1rem;
  }
  .columns img {
    width: 50%;
  }
  .middle-grid {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 1rem;
  }
  .middle-grid img {
    width: 75%;
  }
  .grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 10px;
  }
  .grid img {
    width: 100%;
  }
  .red-text {
    color: red;
  }
  
  .blue-text {
    color: blue;  
  }
  .yellow-text {
    color: yellow;  
  }

  .small-text {
    font-size: 0.50rem;
  }

---
# Cloud Computing
![bg right:60% w:90%](https://zd-brightspot.s3.us-east-1.amazonaws.com/wp-content/uploads/2021/07/09134159/38-3-e1715636964776.png)

# Introduction of Cloud Computing
- <span class="blue-text">**Cloud computing**</span> is the <u> on-demand </u> availability of computer system resources, especially <u>cloud storage</u> and <u>computing power</u>, without direct active management by the user. 
- <span class="blue-text">**On-premises**</span> refers to IT hardware and software that are hosted on-site. Businesses have more control of on-premises IT assets.
- Many legacy and traditional data center resources are on-premises. There has been a shift to migrate IT assets to the cloud in recent years or creating <span class="blue-text">**hybrid environments**</span> that use a mix of cloud and on-premises solutions. 
- Large clouds often have functions distributed over <u>multiple locations (data center)</u>. Cloud computing relies on sharing of resources to achieve coherence and typically uses a <u>pay-as-you-go model</u>.

# Major Cloud Service Providers
- Amazon (AWS): Cloud computing is the on-demand delivery of IT resources over the Internet with pay-as-you-go pricing. Instead of buying, owning, and maintaining physical data centers and servers, you can access technology services, such as computing power, storage, and databases, on an as-needed basis from a cloud provider like Amazon Web Services (AWS).
- Microsoft (Azure): 雲端運算可透過網際網路 (也就是「雲端」) 來傳遞伺服器、儲存體、資料庫、網路、軟體、分析、智慧功能等運算服務，以加快創新的速度、確保資源彈性，並實現規模經濟。一般來說，您只需支付所使用的雲端服務費用，如此有助於降低營運成本、更有效率地執行基礎結構，並隨著業務需求變更來進行調整。
- Google (GCP, Google Cloud Platform): 雲端運算架構能根據使用者需求，透過網路以服務的形式提供運算資源，例如儲存空間和基礎架構。這樣個人和企業就不必自行管理實體資源，而且用多少付多少。

# Deployment Models
- Public cloud
- Private cloud (on-premises)
- Community cloud (government, education, back)
- Hybrid cloud
![bg right:60% w:90%](https://uniprint.net/wp-content/uploads/2017/05/Cloud-deployment-structures-diagram.png)

# Public vs Private Cloud
| Feature               | Public Cloud                          | Private Cloud                         |
|-----------------------|--------------------------------------|--------------------------------------|
| Ownership             | Third-party cloud service provider   | Single organization                  |
| Accessibility        | Over the internet                    | Restricted to organization           |
| Cost                  | Pay-as-you-go pricing                | Higher upfront costs                 |
| Scalability           | Highly scalable                      | Limited by organization's resources  |
| Security              | Shared responsibility model          | Greater control over security        |
| Maintenance           | Managed by cloud provider            | Managed by organization's IT team    | 

# Service Models
![bg right:50% w:90%](https://d2ds8yldqp7gxv.cloudfront.net/Blog+Explanatory+Images/Cloud+Service+Model+1.webp)  
- IaaS (Infrastructure as a service)
- PaaS (Platform as a service) <br>MySQL, Kubernetes, Google App Engine
- SaaS (Software as a service)

# Shared Responsibility
![bg right:50% w:90%](https://assets.bacancytechnology.com/blog/wp-content/uploads/2023/11/03065559/Internal-image-4.jpg)

# Cloud Computing Explained
[![What Is Cloud Computing?](https://i.ytimg.com/vi/M988_fsOSWo/default.jpg)](https://youtu.be/M988_fsOSWo?si=HrTrbhx3aQL8r6XB)

