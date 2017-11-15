---
layout: post
title:  Dashboard for Mangata
<!-- categories: Work Experience
date-string: OCTOBER 14, 2017 -->
---

| Software Engineer Internship | Mangata Inc. | Jun. 2017 – Aug. 2017|
| :------------- |:-------------:| -----:|
||||
| Referenced By: ||| 

- CEO Andrei Papancea: <andrei@mangata.io>
- Co-Founder Vlad Papancea: <vlad@mangata.io>

#### Worked on a team to build a platform to manage products, orders and gift sending policies. Build the FrontEnd, BackEnd and Databases for the platform.

### Frontend Framework:
* Structured Components, Services and Routing Module for dashboard platform using **AngularJS 2**, hosting on S3.
* Implemented web design with ***HTML, CSS and Bootstrap*** for different components with proper data binding. 


The products page: 
![](/images/dashboard-mangata/products.png)

The orders page:
![](/images/dashboard-mangata/orders.png)

### Backend AWS Services: 
* Created **DynamoDB** databases for products and orders and **Elasticsearch** endpoint for search service. 
* Implemented **Lambda** functions: Create/Read/Update/Delete operations on databases; Post/Delete(DBs triggered) and Filter operations on Elasticsearch. 
* Designed **RESTful** APIs under designed parameter and data requirements on **API Gateway**, connected APIs with corresponding Lambda functions, and integrated API Gateway SDK to AngularJS. 

The AWS service basic structureand designed API:
<div class="dashdiv" style="text-align:center;">
    <img src="/images/dashboard-mangata/diagram.png" style="width:55%;display:inline-block;">
	<img src="/images/dashboard-mangata/APIs.png" style="width:55%;display:inline-block;">
</div>

<style>
.dashdiv{
    padding:0;
}
.dashdiv img{
    margin:0;
}

</style>
<!-- 
The AWS service structure: 
<img src="/images/dashboard-mangata/diagram.png"> -->
