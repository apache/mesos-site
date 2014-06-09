---
title: Apache Mesos
---

<div class="jumbotron">
	<div class="row">
	  <div class="col-md-7">
	    <h1>Making it easy to build resource-efficient distributed systems</h1>
	    <p class="lead">Apache Mesos is a cluster manager that provides efficient resource isolation and sharing across distributed applications, or <em>frameworks</em>. It can run Hadoop, Jenkins, Spark, Aurora, and other applications on a dynamically shared pool of nodes.</p>
	  </div>
	  <div class="col-md-5 text-center download">
	    <a class="btn btn-lg btn-success" href="/downloads/"><span class="glyphicon glyphicon-download"></span> Download Mesos 0.19.0</a>
	    <p>or learn how to <a href="/gettingstarted/">get started</a></p>
	  </div>
	</div>
</div>

<hr>

<!-- lowersection -->
<div class="row">
  <div class="col-md-8">
    <h3>Mesos Adopters</h3>

		<ul class="media-list">
			<li class="media">
		    <a class="pull-left" href="#">
		      <img class="media-object" src="/assets/img/twitter_logo.png" alt="Twitter logo" />
		    </a>
				<div class="media-body">
					<h4 class="media-heading">Chris Fry, SVP of Engineering at Twitter</h4>
					<p>"Mesos is the cornerstone of our elastic compute infrastructure -- it's how we build all our new services and is critical for Twitter's continued success at scale. It's one of the primary keys to our data center efficiency."</p>
				</div>
			</li>
		  <li class="media">
		    <a class="pull-left" href="#">
		      <img class="media-object" src="/assets/img/airbnb_logo.png" alt="Airbnb logo" />
		    </a>
				<div class="media-body">
					<h4 class="media-heading">Brenden Matthews, AirBnB</h4>
					<p>"At Airbnb, we're using Mesos to manage cluster resources for most of our data infrastructure.  We run <a href="http://airbnb.github.io/chronos/">Chronos</a>, <a href="http://storm-project.net/">Storm</a>, and Hadoop on top of Mesos in order to process petabytes of data."</p>
				</div>
			</li>
			<li class="media">
				<div class="media-body">
					<p><a href="http://mesos.apache.org/documentation/latest/powered-by-mesos/">Other companies powered by Mesos</a>
				</div>
			</li>
		</ul>
		
		<br />

    <h3>Features</h3>
    <ul>
     <li>Fault-tolerant replicated master using ZooKeeper</li>
     <li>Scalability to 10,000s of nodes</li>
     <li>Isolation between tasks with Linux Containers</li>
     <li>Multi-resource scheduling (memory and CPU aware)</li>
     <li>Java, Python and C++ APIs for developing new parallel applications</li>
     <li>Web UI for viewing cluster state</li>
    </ul>
  </div>
  <div class="col-md-4">
    <h3>News</h3>
      <ul>
        <li><em>June 9th, 2014</em> - Mesos 0.19.0 is released! See the <a href="">0.19.0 release notes</a>, blog post
          coming soon!</li>
        
        <li><em>May 29, 2014</em> - Mesos 0.18.1 and 0.18.2 are released!
            See the <a href="https://issues.apache.org/jira/secure/ReleaseNote.jspa?projectId=12311242&version=12326752">0.18.1 release notes</a>,
            <a href="https://issues.apache.org/jira/secure/ReleaseNote.jspa?projectId=12311242&version=12326851">0.18.2 release notes</a>
            and <a href="/blog/mesos-0-18-1-and-0-18-2-released/">blog post announcement</a> for more details.
        </li>
        
        <li><em>April 10, 2014</em> - Mesos 0.18.0 is released!
            See the <a href="https://issues.apache.org/jira/secure/ReleaseNote.jspa?projectId=12311242&version=12326140">release notes</a>
            and <a href="/blog/mesos-0-18-0-released/">blog post announcement</a> for more details.</li>
        
        <li><em>March 28, 2014</em> - Mesos Community Update #1.
            See the <a href="blog/mesos-community-update-1/">blog post</a>.</li>
          
        <li><em>March 6, 2014</em> - Mesos 0.17.0 is released!
            See the <a href="https://issues.apache.org/jira/secure/ReleaseNote.jspa?projectId=12311242&version=12325669">release notes</a>
            and <a href="blog/mesos-0-17-0-released-featuring-autorecovery/">blog post announcement</a>.</li>

        <li><em>Feburary 11, 2014</em> - Mesos 0.16.0 is released!
            See the <a href="/blog/mesos-0-16-0-released/">blog post announcement</a> for more details.</li>

        <li><em>January 09, 2014</em> - Mesos 0.15.0 is released!
            See the <a href="/blog/framework-authentication-in-apache-mesos-0-15-0/">blog post announcement</a>
            for more details.</li>

        <li><em>December 16, 2013</em> - Niklas Nielson becomes project&#39;s newest committer and PMC member
            (<a href="/blog/niklas-nielsen-becomes-mesos-committer/">Announcement</a>)</li>

        <li><em>November 12, 2013</em> - Mesos 0.14.2 is released!
            See the <a href="/blog/mesos-0-14-2-released/">blog post announcement</a> for more details.</li>

        <li><em>October 23, 2013</em> - <a href="/blog/slave-recovery-in-apache-mesos/">New blog post</a> by
            Vinod Kone about the Slave Recovery feature introduced in Mesos 0.14.1</li>

        <li><em>October 21, 2013</em>
            - Mesos 0.14.1 is released! Now <a href="/downloads/">available for download</a>.</li>

        <li><em>October 16, 2013</em>
            - Mesos 0.14.0 is released! Now <a href="/downloads/">available for download</a>.</li>

        <li><em>September 11, 2013</em>
            - Mesos 0.13.0 is released! Now <a href="/downloads/">available for download</a>.</li>
      </ul>

		<br />

		<h3>Follow Us</h3>
		<span class="social">
	  <a href="https://twitter.com/ApacheMesos" class="twitter-follow-button" data-show-count="false" data-size="large">Follow @ApacheMesos</a>
	  <script>!function(d,s,id){var js,fjs=d.getElementsByTagName(s)[0],p=/^http:/.test(d.location)?'http':'https';if(!d.getElementById(id)){js=d.createElement(s);js.id=id;js.src=p+'://platform.twitter.com/widgets.js';fjs.parentNode.insertBefore(js,fjs);}}(document, 'script', 'twitter-wjs');</script>
	  <a href="https://twitter.com/intent/tweet?button_hashtag=mesos" class="twitter-hashtag-button" data-size="large" data-related="ApacheMesos">Tweet #mesos</a>
	  <script>!function(d,s,id){var js,fjs=d.getElementsByTagName(s)[0],p=/^http:/.test(d.location)?'http':'https';if(!d.getElementById(id)){js=d.createElement(s);js.id=id;js.src=p+'://platform.twitter.com/widgets.js';fjs.parentNode.insertBefore(js,fjs);}}(document, 'script', 'twitter-wjs');</script>
	  </span>
 </div>
</div>
<!-- /lowersection -->
