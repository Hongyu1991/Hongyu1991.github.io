---
layout: post
title: PostNearby
<!-- categories: Projects
date-string: November 13, 2017 -->
---
<style>
div .postnearby {
	width:35%;
	display:inline-block;
	margin:30px;
	border:1px solid grey;
	margin-top: 0px;
}
</style>

**PostNeaby is an iOS app where you can post anything on the system and also search posts around you.**

* Built an **iOS app** for users to send posts in their location and search other user’s posts on the map.

In the home page, the user can scan the posts from others' posts around. Click one record, the user can see the detail of that post. The user can also do post from home page. In the explore page, the user can search posts around in the map and have the access to see the detail if he/she hit the markers on the map.  
<div style="text-align:center;">
	<img class="postnearby" src="/images/postnearby/home.png">
	<img class="postnearby" src="/images/postnearby/search2.png">
	<img class="postnearby" src="/images/postnearby/post.png">
	<img class="postnearby" src="/images/postnearby/detail.png">
</div>

* Created a backend server using **Go** in scalable **Google App Engine** to handle user’s post/search operations. 
<div class="language-ruby highlighter-rouge"><div class="highlight"><pre class="highlight"><code>
<span class="k">func</span> <span class="nf">handlerSearch</span>(w <span class="nb">http.ResponseWriter</span>, r <span class="nb">*http.Request</span>) {}
<span class="k">func</span> <span class="nf">handlerPost</span>(w <span class="nb">http.ResponseWriter</span>, r <span class="nb">*http.Request</span>) {}
<span class="k">func</span> <span class="nf">main</span>() {
	<span class="nb">http.HandleFunc</span>("/post", handlerPost)
	<span class="nb">http.HandleFunc</span>("/search", handlerSearch)
	<span class="nb">log.Fatal</span>(http.ListenAndServe(":8080", nil))
}
</code></pre></div></div>



* Implemented the geo-search functionality through the service of a **Elastic Search** endpoint in EC2. 
<div class="language-ruby highlighter-rouge"><div class="highlight"><pre class="highlight"><code>
//search function:
<span class="m">searchResult</span>, err := <span class="nb">es_client</span>.<span class="k">Search</span>().
	<span class="nb">Index</span>(INDEX).
	<span class="nb">Query</span>(query).
	<span class="nb">Pretty</span>(true).
	<span class="nb">Do</span>()

//insert function:
<span class="m">_</span>, err = <span class="nb">es_client</span>.Index().
	<span class="nb">Index</span>(INDEX).
	<span class="nb">Type</span>(TYPE).
	<span class="nb">Id</span>(id).
	<span class="nb">BodyJson</span>(p).
	<span class="nb">Refresh</span>(true).
	<span class="nb">Do</span>()
</code></pre></div></div>
* Utilized **Google Dataflow** to dump user posts from **BigTable** to **BigQuery** for content analysis. 
<div class="language-ruby highlighter-rouge"><div class="highlight"><pre class="highlight"><code>
<span class="m">Pipeline</span> p = Pipeline.<span class="k">create</span>(options);

<span class="m">PCollection</span>&lt;Result&gt; btRows = p.<span class="k">apply</span>(Read.from(CloudBigtableIO.read(config)));

<span class="m">PCollection</span>&lt;TableRow&gt; bqRows = btRows.<span class="k">apply</span>(ParDo.of());

bqRows.<span class="k">apply</span>(BigQueryIO.Write());

p.<span class="k">run</span>();
</code></pre></div></div>


<div style="text-align:center;">
	<img class="postnearby" src="/images/postnearby/dataflow.png">
</div>

