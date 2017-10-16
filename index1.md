---
layout: post
title:  "Dashboard for Mangata"
date:   2017-10-14
categories: Work Experience
---
<script src="//ajax.googleapis.com/ajax/libs/jquery/1.9.1/jquery.min.js"></script>
<script>window.jQuery || document.write('<script src="_/js/libs/jquery-1.9.1.min.js"><\/script>')</script>

| Software Engineer Internship | *Mangata Inc.* | Jun. 2017 – Aug. 2017|


Referenced By:
- CEO Andrei Papancea: <andrei@mangata.io>
- Co-Founder Vlad Papancea: <vlad@mangata.io>

#### Worked on a team to build a platform to manage products, orders and gift sending policies. Build the FrontEnd, BackEnd and Databases for the platform.

### Frontend Framework:
* Structured Components, Services and Routing Module for dashboard platform using **AngularJS 2**, hosting on S3.
* Implemented web design with ***HTML, CSS and Bootstrap*** for different components with proper data binding. 

The major web pages created: 
<center>
    <div class="photoset-grid-custom" data-layout="22213">
        <img src="/images/dashboard-mangata/orders.png">
        <img src="/images/dashboard-mangata/products.png">
    </div>
</center>

### Backend AWS Services: 
* Created **DynamoDB** databases for products and orders and **Elasticsearch** endpoint for search service. 
* Implemented **Lambda** functions: Create/Read/Update/Delete operations on databases; Post/Delete(DBs triggered) and Filter operations on Elasticsearch. 
* Designed **RESTful** APIs under designed parameter and data requirements on **API Gateway**, connected APIs with corresponding Lambda functions, and integrated API Gateway SDK to AngularJS.

Back End service structure and APIs:
<center>
    <div class="photoset-grid-custom" data-layout="22213">
    	<img src="/images/dashboard-mangata/diagram.png">
        <img src="/images/dashboard-mangata/APIs.png">
    </div>
</center>

<script src="/assets/js/jquery.photoset-grid.js"></script>

<script type="text/javascript">
    $('.photoset-grid-custom').photosetGrid({
    // Set the gutter between columns and rows
    gutter: '5px',
  
    // Wrap the images in links
    highresLinks: true,
  
    // Asign a common rel attribute
    rel: 'print-gallery',

    onInit: function(){},
    
    onComplete: function(){
        // Show the grid after it renders
        $('.photoset-grid-custom').attr('style', '');
    }
});
</script>