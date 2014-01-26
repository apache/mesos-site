---
title: Apache Mesos | Getting Started
breadcrumb: Getting Started
---

  <div class="row">
		<div class="col-md-2">
			<ul class="list-group">
				<li class="list-group-item"><a href="#system-requirements">Requirements</a></li>
				<li class="list-group-item"><a href="#downloading-mesos">Download Mesos</a></li>
				<li class="list-group-item"><a href="#buildingmesos">Build Mesos</a></li>
				<li class="list-group-item"><a href="#running-example-frameworks">Run Frameworks</a></li>
			</ul>
		</div>
    <div class="col-md-10">
      <h1>Getting Started with Apache Mesos</h1>

<h3><a name="system-requirements">System Requirements</a></h3>

<p>Mesos runs on Linux and Mac OS X, and has previously also been tested on OpenSolaris. You will need the following packages to run it:</p>

<ul>
	<li>g++ 4.1 or higher.</li>
	<li>Python 2.6 (for the Mesos web UI). On Mac OS X 10.6 or earlier, get Python from <a href="http://www.macports.org">MacPorts</a> via <code>port install python26</code>, because OS X's version of Python is not 64-bit.</li>
	<li>Python 2.6 developer packages (on red-hat - <code>sudo yum install python26-devel python-devel</code>) (on debian - <code>sudo apt-get python2.6-dev</code>)</li>
	<li>cppunit (for building zookeeper) (on red-hat - <code>sudo yum install cppunit-devel</code>) (on debian - <code>sudo apt-get install libcppunit-dev</code>)</li>
	<li>libunwind (for building gperftools) (on red-hat - <code>sudo yum install libunwind-devel</code>) (on debian - <code>sudo apt-get install libunwind7-dev</code>)</li>
	<li>Java JDK 1.6 or higher. Mac OS X 10.6 users will need to install the JDK from http://connect.apple.com/ and set <code>JAVA_HEADERS=/System/Library/Frameworks/JavaVM.framework/Versions/A/Headers</code>.</li>
</ul>

<h3><a name="downloading-mesos">Downloading Mesos</a></h3>

<p>Mesos is available as a tar file, or the source can be downloaded directly from git. To get running with Mesos version 0.15.0, our most-recent release by either:</p>

<ul>
	<li><a href="http://www.apache.org/dyn/mirrors/mirrors.cgi/mesos/0.15.0/">Download Mesos 0.15.0</a></li>
	<li>Obtain the current Mesos development HEAD by checking it out from Apache Git mirror repository, using: <code>git clone git://git.apache.org/mesos.git</code>, or <code>https://git-wip-us.apache.org/repos/asf/mesos.git</code></li>
</ul>

<h3><a name="buildingmesos">Building Mesos</a></h3>

<ul>
  <li>Only if running from source code cloned from git, run <code>./bootstrap</code> otherwise skip to step 3</li>
  <li>If you get error <code>Autoreconf may not be installed</code>, on debian run <code>sudo apt-get install autoconf</code>
  <li>If you get error <code>Makefile.am:27: Libtool library used but `LIBTOOL' is undefined</code>, on debian run <code>sudo apt-get update && sudo apt-get install autotools-dev libltdl-dev libtool autoconf autopoint </code></li>	
  <li>Run <code>./configure</code>, which includes the web UI and included Zookeeper.  Advanced users may want to exclude these options or include other options, see <a href="http://mesos.apache.org/documentation/latest/configuration/">Mesos Command-Line Flags</a>.</li>
  <li>Run <code>make</code></li>
</ul>

<h4>NOTES:</h4>
<ul>
	<li>The build process attempts to guess where your Java include directory is, but if you have set the $JAVA_HOME environment variable, it will use $JAVA_HOME/include, which may not be correct (or exist) on your machine (in which case you will see an error such as: "configure: error: failed to build against JDK (using libtool)"). If this is the case, we suggest you unset the JAVA_HOME environment variable.</li>
	<li>`configure` may print a warning at the end about "unrecognized options: --with-java-home, ...". This comes from one of the nested `configure` scripts that we call, so it doesn't mean that your options were ignored.</li>
	<li>(NOT SURE IF THIS IS STILL RELEVANT) On 32-bit platforms, you should set `CXXFLAGS="-march=i486"` when running `configure` to ensure certain atomic instructions can be used.</li>
</ul>

<h3><a name="running-example-frameworks">Running Example Frameworks</a></h3>

<p>Currently, in order to run the example frameworks (in src/examples), you must first build the test suite, as instructed below.</p>

<p>After you build Mesos by running the `make` command, you can set up a small Mesos cluster and run a job on it as follows:</p>

<ul>
	<li>Go into the directory where you built Mesos.
	<li>Type `bin/mesos-master.sh` to launch the master.
	<li>Take note of the IP and port that the master is running on, which will look something like <code>192.168.0.1:5050</code>. <i>Note: In this example the IP address of master is 192.168.0.1, and the port is 5050. We will continue to use the URL shown here for the rest of this example; however when you run the following commands replace all instances of it with the URL of your master.</i></li>
	<li>URL of master: <code>192.168.0.1:5050</code>
	<li>View the master's web UI at `http://[hostname of master]:5050`.
	<li>Launch a slave by typing <code>bin/mesos-slave.sh --master=192.168.0.1:5050</code>. The slave will show up on the master's web UI if you refresh it.
	<li>Run the C++ test framework (a sample that just runs five tasks on the cluster) using <code> src/test-framework --master=localhost:5050 </code>. It should successfully exit after running five tasks.</li>
	<li>You can also try the example python or Java frameworks, with commands like the following:</li>
		<ul>
			<li>`src/examples/java/test-framework 192.168.0.1:5050`</li>
			<li>`src/examples/python/test-framework 192.168.0.1:5050`</li>
		</ul>
</ul>
   </div>
  </div>
