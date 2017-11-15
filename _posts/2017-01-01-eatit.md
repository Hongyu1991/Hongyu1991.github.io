---
layout: post
title: Eatit
<!-- categories: Projects
date-string: November 14, 2017 -->
---
<style>
div .eatit {
	width:80%;
	display:inline-block;
	margin:10px;
	/*border:1px solid grey;*/
}
</style>

Built a web app which enables users to search restaurants nearby, and get recommendations according to their favorite records.

* Developed a web user interface (*HTML5/CSS/JS*) with page views of Nearby, Favorite, & Recommendation. 

<div style="text-align:center;">
	<img class="eatit" src="/images/eatit/login.png">
	<img class="eatit" src="/images/eatit/nearby.png">
	<img class="eatit" src="/images/eatit/fav.png">
	<img class="eatit" src="/images/eatit/recommendation.png">
</div>

* Created Java servlet *RESTful* APIs under **Apache Tomcat** software to listen & respond to HTTP requests. 
<div class="language-java highlighter-rouge"><div class="highlight"><pre class="highlight"><code>
<span class="k">@WebServlet</span>(<span class="s1">"/restaurants"</span>)
public class SearchRestaurants extends HttpServlet {}

<span class="k">@WebServlet</span>(<span class="s1">"/favorite"</span>)
public class FavRecords extends HttpServlet {}

<span class="k">@WebServlet</span>(<span class="s1">"/recommendation"</span>)
public class RecommendRestaurants extends HttpServlet {}
</code></pre></div></div>

* Built database services (Relational/Nosql **MySQL/MongoDB**) to store restaurant/user/favorite records. 

* Implemented restaurant geo-search function through **Yelp API** and stored the returned data into databases. 

* Deployed the service on AWS EC2, enabling a 200 requests/sec performance tested in **Apache JMeter**. 

* Tested test cases in JUnit and completed **Elastic Search/Logstash/Kibana** log analysis. 

