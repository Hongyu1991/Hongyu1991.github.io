---
layout: post
title:  VideoStyle
<!-- categories: Projects
date-string: November 14, 2017 -->
---
<style>
div .videostyle {
	width:80%;
	display:inline-block;
	margin:15px;
}
</style>


**Designed for users to stylize their videos into their favored types, and offers users an interface to upload their videos and get stylized videos.**


* Designed the index web page(HTML5/CSS/JavaScript) for a user to upload video, enter email address, & choose the preferred style and show page for user to view/download/share the processed video. 
<div style="text-align:center;">
	<img class="videostyle" src="/images/videostyle/home.png">
	<img class="videostyle" src="/images/videostyle/input.png">
	<img class="videostyle" src="/images/videostyle/result.png">
</div>

* Fulfilled video type, email input, & empty checkings to ensure the correctness of data submitted to backend.


* Created a backend server with Python Flask that implemented routing for indexing & showing page, and receiving the video & info data sent from the user. 
<div class="language-ruby highlighter-rouge"><div class="highlight"><pre class="highlight"><code>
#index page 
@application.route(<span class="s1">'/'</span>, methods=[<span class="s1">'GET'</span>, <span class="s1">'POST'</span>])
<span class="k">def</span> <span class="nf">init</span>():
	if request.method == <span class="s1">'POST'</span>:
		file.save(filepath)
		upload_file(bucket_name,filepath,filename_time)
		send_msg(queue_name=queue_name,email=email,style=style,image=filename_time)
	return render_template(<span class="s1">'index.html'</span>)

#show processed video
@application.route(<span class="s1">'/show_result'</span>, methods=[<span class="s1">'GET'</span>, <span class="s1">'POST'</span>])
<span class="k">def</span> <span class="nf">show_result</span>():
	return render_template(<span class="s1">'show.html'</span>)
</code></pre></div></div>


* Used AWS APIs to store the uploaded videos to S3 and send processing tasks to SQS. 


* Implemented the API for receiving SNS notification when video has been processed, creating new web address for user to fetch processed video and sending the address to the registered email. 
<div class="language-ruby highlighter-rouge"><div class="highlight"><pre class="highlight"><code>
#used to receive sns
@application.route(<span class="s1">'/notification'</span>, methods=[<span class="s1">'GET'</span>, <span class="s1">'POST'</span>])
<span class="k">def</span> <span class="nf">sns</span>():
	download_file(bucket_name,s3img,local_location)
	send_link_to_user(user_email, url)
</code></pre></div></div>

