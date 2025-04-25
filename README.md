# cs6250-project-1-bgp-hijacking-solved



**<span style='color:red'>TO GET THIS SOLUTION VISIT:</span>** https://www.ankitcodinghub.com/product/cs6250-bgp-hijacking-project-solved/

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;126475&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;3&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (3 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;CS6250 Project  1-BGP Hijacking  Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">
            
<div class="kksr-stars">
    
<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
    
<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>
                

<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (3 votes)    </div>
    </div>
&nbsp;

<h1><a name="_Toc14609"></a>Overview</h1>
<h2><a name="_Toc14610"></a>Introduction</h2>
In this project you will explore a vulnerability of the <a href="https://en.wikipedia.org/wiki/Border_Gateway_Protocol">Border Gateway Protocol</a> (BGP). Specifically, your goal is to recreate a <a href="https://www.cloudflare.com/learning/security/glossary/bgp-hijacking/">BGP Hijacking</a> attack where a “rogue” AS (<a href="https://en.wikipedia.org/wiki/Autonomous_system_(Internet)">autonomous</a> <a href="https://en.wikipedia.org/wiki/Autonomous_system_(Internet)">system</a><a href="https://en.wikipedia.org/wiki/Autonomous_system_(Internet)">)</a> hijacks a prefix from another AS, thereby “stealing” traffic.

As discussed in Lesson 4, <a href="https://datatracker.ietf.org/doc/html/rfc1930#section-3">“A</a><a href="https://datatracker.ietf.org/doc/html/rfc1930#section-3">n AS</a> <a href="https://datatracker.ietf.org/doc/html/rfc1930#section-3">is a connected group of one or more IP prefixes run by one or</a> <a href="https://datatracker.ietf.org/doc/html/rfc1930#section-3">more network operators which has a SINGLE and CLEARLY DEFINED&nbsp; routing policy.</a><a href="https://datatracker.ietf.org/doc/html/rfc1930#section-3">”</a> An AS can be an <a href="https://en.wikipedia.org/wiki/Internet_service_provider">Internet Service Provider</a> (ISP), an IXP (where ISP’s and CDN’s exchange local traffic), or a CDN (e.g., Netflix and Google). Each AS has border routers that utilize BGP to exchange routing information with one another.

The prefixes advertised by BGP are used to implement routing policies, which makes cooperation amongst ASs very important. The flexibility and scalability that BGP allows, however, comes with a cost in security. From <a href="https://en.wikipedia.org/wiki/Border_Gateway_Protocol">Wikipedia</a><a href="https://en.wikipedia.org/wiki/Border_Gateway_Protocol">:</a>

<em>By design, routers running BGP accept advertised routes from other BGP routers by default. This allows for automatic and decentralized routing of traffic across the Internet, but it also leaves the Internet potentially vulnerable to accidental or malicious disruption, known as BGP hijacking. Due to the extent to which BGP is embedded in the core systems of the Internet, and the number of different networks operated by many different organizations which collectively make up the Internet, correcting this vulnerability (such as by introducing the use of cryptographic keys to verify the identity of BGP routers) is a technically and economically challenging problem. </em>

<h2><a name="_Toc14611"></a>What Is BGP Hijacking?</h2>
BGP hijacking occurs when an attacker attempts to re-route (steal) traffic by issuing a <a href="https://orhanergun.net/bgp-route-advertisement">BGP Route</a> <a href="https://orhanergun.net/bgp-route-advertisement">Advertisement</a> for an IP prefix that is owned or controlled by another AS. Such an attack causes routing disruptions and connectivity issues for individual hosts, networks, and sometimes even entire countries. A simple search will turn up lots of information about notable <a href="https://en.wikipedia.org/wiki/BGP_hijacking#Public_incidents">public incidents</a><a href="https://en.wikipedia.org/wiki/BGP_hijacking#Public_incidents">.</a>

Because BGP favors shorter routes and more specific routes by design, a hijacking event can occur (either deliberately or by accident) when an AS advertises a prefix for which it is not the true originator and that prefix:

<ul>
<li>duplicates a correct advertisement, but has a shorter path</li>
<li>is more specific than another correct advertisement</li>
</ul>
&nbsp;

<h2><a name="_Toc14612"></a>What happens when BGP is hijacked?</h2>
When a hijack occurs, it can cause:

<ul>
<li>dropped traffic (causing disruption),</li>
<li>re-routed traffic (allowing an attacker to, for example, steal credentials), and/or</li>
<li>increased latency (causing performance degradation)</li>
</ul>
Even though the victim AS thinks the route is shorter, the reality is it may be a lot longer than the previous advertised routes. The best-case scenario of an attack is that the hijacked route will only increase latency by steering traffic to a much longer route. The worst case scenario of an attack is that an attacker re-routes traffic to a malicious site to steal confidential information.

<h2><a name="_Toc14613"></a>BGP hijacking in the real world</h2>
Attackers can use BGP hijacking in the real world to steal confidential data or electronic assets, such as when a <a href="https://arstechnica.com/information-technology/2017/04/russian-controlled-telecom-hijacks-financial-services-internet-traffic/">Russian government</a><a href="https://arstechnica.com/information-technology/2017/04/russian-controlled-telecom-hijacks-financial-services-internet-traffic/">–</a><a href="https://arstechnica.com/information-technology/2017/04/russian-controlled-telecom-hijacks-financial-services-internet-traffic/">controlled telecom re</a><a href="https://arstechnica.com/information-technology/2017/04/russian-controlled-telecom-hijacks-financial-services-internet-traffic/">–</a><a href="https://arstechnica.com/information-technology/2017/04/russian-controlled-telecom-hijacks-financial-services-internet-traffic/">routed large chunks of network traffic</a> <a href="https://arstechnica.com/information-technology/2017/04/russian-controlled-telecom-hijacks-financial-services-internet-traffic/">belonging to MasterCard, Visa, and more than two dozen other financial services</a> in 2017 or when <a href="https://therecord.media/klayswap-crypto-users-lose-funds-after-bgp-hijack">hackers stolen almost $2m from South Korean cryptocurrency platform KLAYswap</a> in 2022.

Hijack incidents can also occur when routes “leak” by mistake, such as whe<a href="https://blog.apnic.net/2021/04/26/a-major-bgp-route-leak-by-as55410/">n </a><a href="https://blog.apnic.net/2021/04/26/a-major-bgp-route-leak-by-as55410/">AS55410 (controlled</a> <a href="https://blog.apnic.net/2021/04/26/a-major-bgp-route-leak-by-as55410/">by Vodafone Idea Ltd.) mistakenly announced over 30,000 BGP prefixes causing a 13x spike in</a> <a href="https://blog.apnic.net/2021/04/26/a-major-bgp-route-leak-by-as55410/">inbound traffic to their network</a> or when <a href="https://web.archive.org/web/20150704012111/http:/research.dyn.com/2006/01/coned-steals-the-net/">Con Edison</a> <a href="https://web.archive.org/web/20150704012111/http:/research.dyn.com/2006/01/coned-steals-the-net/">“stole the Internet”</a> for most of a full day.

Read <a href="https://www.cloudflare.com/learning/security/glossary/bgp-hijacking/">What is BGP hijacking?</a> For a terrific overview.

&nbsp;

<h1><a name="_Toc14614"></a>Goal</h1>
In this project, which is based on the <a href="https://github.com/mininet/mininet/wiki/BGP-Path-Hijacking-Attack-Demo">BGP Path Hijacking Attack Demo</a> included in the Mininet project, we will explore some of the vulnerabilities of Border Gateway Protocol (BGP). In particular, we will see how BGP is vulnerable to abuse and manipulation through a class of attacks called BGP hijacking attacks. A malicious AS can mount these attacks through false BGP announcements from a rogue AS, causing victim ASes to route their traffic bound for another AS through the malicious AS. This attack succeeds because the false advertisement exploits BGP routing behavior by advertising a shorter path to reach a particular prefix, which causes victim ASes to attempt to use the newly advertised (and seemingly better!) route.

&nbsp;

In this project you will explore a vulnerability of the <a href="https://en.wikipedia.org/wiki/Border_Gateway_Protocol">Border Gateway Protocol</a> (BGP). Specifically, your goal is to recreate a <a href="https://www.cloudflare.com/learning/security/glossary/bgp-hijacking/">BGP Hijacking</a> attack where a “rogue” AS (<a href="https://en.wikipedia.org/wiki/Autonomous_system_(Internet)">autonomous</a> <a href="https://en.wikipedia.org/wiki/Autonomous_system_(Internet)">system</a><a href="https://en.wikipedia.org/wiki/Autonomous_system_(Internet)">)</a> hijacks a prefix from another AS, thereby “stealing” traffic.

<strong>&nbsp;</strong>

<h1><a name="_Toc14615"></a>BGP Hijacking Simple Demo</h1>
&nbsp;

This is a demo to help better understand BGP Hijacking on mininet.

<h2><a name="_Toc14616"></a>Part 1: Background reading</h2>
<strong>Please read the resources, and example BGP router configurations. And the project slide. </strong>

<ol>
<li>Browse this <a href="https://www2.cs.arizona.edu/~bzhang/paper/07-dsn-hijack.pdf">paper </a><a href="https://www2.cs.arizona.edu/~bzhang/paper/07-dsn-hijack.pdf">a</a>s a reference for subsequent tasks and for some important background on Prefix Hijack Attacks.</li>
<li>Refer to this <a href="https://docs.frrouting.org/en/latest/bgp.html#bgp-router-configuration">resource</a> on configuring a BGP router with Quagga. Also, the <a href="http://docs.frrouting.org/en/latest/zebra.html#id3">FRR docs for zebra</a> can be helpful as well.</li>
<li>The “BGP Bible” is here <a href="https://www.cisco.com/c/en/us/td/docs/ios/iproute_bgp/command/reference/irg_book.html">https://www.cisco.com/c/en/us/td/docs/ios/iproute_bgp/command/reference/irg_book.html</a></li>
</ol>
<h2><a name="_Toc14617"></a>Part 2: Demonstration using a Mininet Topology and simulated prefixes/paths</h2>
&nbsp;

The demo creates the network topology shown below, consisting of four ASes and their peering relationships. AS4 is the malicious AS that will mount the attack. Once again, we will be simulating this network in Mininet, however there are some important distinctions to make from our previous projects. In this setup, each object is not a single host, but an entire autonomous system. In each AS, a router runs a routing daemon (quagga), communicates with other ASes using BGP (bgpd), and configures its own isolated set of routing entries in the kernel (zebra). Each AS router has multiple IP addresses, to connect to the hosts in the AS and to other routers.

&nbsp;

&nbsp;

NOTE: In this topology solid lines indicate peering relationships, and the dotted boxes indicate the prefix advertised by that AS.

<h3><a name="_Toc14618"></a>STEPS TO START DEMO</h3>
As part of completing this project,

<ol>
<li>Download and unzip the project files. This should create a directory named</li>
</ol>
BGPHijacking (the “Project Directory”). The file permissions and ownership should be correct, but if not, adjust them appropriately. It’s okay to freely discuss this aspect of the project on Edstem.

<ol start="2">
<li>For some of the steps below, you will use the <strong>sudo</strong> You might be asked to enter your password. If <strong>sudo</strong> asks you to enter a password, use “mininet.”</li>
<li>Open a terminal in the Project Directory. Type: <strong>sudo python ./bgp.py</strong>. After loading the topology, the Mininet CLI should be visible. Keep this terminal open throughout the experiment.</li>
<li>Open a second terminal in the Project directory. You will use this terminal to access R1’s routing daemon (bgpd). Do that by executing the following command: <strong>./connect.sh</strong></li>
<li>The <strong>sh</strong> script uses <strong>run.py</strong> to connect to the bgpd shell on the router specified in the variable <strong>$router</strong>. Accessing the bgpd shell will start quagga, which will ask for a password. The password is: “<strong>en</strong>”. Once you have authenticated, you will have access to the administration shell and R1 routing table. When you get the <strong>bgpd-R1#</strong> prompt, type the following command: <strong>sh ip bgp</strong></li>
<li>You should see output very much like the screen grab below. Notice that AS1 has chosen the path via AS2 and AS3 to reach the prefix 13.0.0.0/8. <strong>NOTE: It may take a minute for the routes to settle. Try the command until you see all three routes.</strong></li>
</ol>
&nbsp;

<ol start="7">
<li>Next, verify that network traffic is traversing this path. Open a third terminal in the Project Directory (keeping all other terminals open). In this terminal, you will start a script that continuously makes web requests from a host within AS1 to a web server in AS3. Type in the following: <strong>./website.sh</strong></li>
<li>Now, you will start a rogue AS (AS4) that will connect directly to AS1 and advertise the same 13.0.0.0/8 prefix. This will allow AS4 to hijack the prefix due to the shorter AS Path Length. Open a third terminal in the Project Directory (keeping all other terminals open) and type the following: <strong>./start_rogue.sh</strong></li>
<li>Return to the third terminal window and observe the continuous web requests. After the BGP routing tables converge on this simple network, you will see the attacker start responding to requests from AS1, rather than AS3.</li>
<li>You should also return to the second terminal and rerun the command to print the routing table. You should now see the fraudulent advertisement for the 13.0.0.0/8 prefix in the routing table, in addition to the longer unused path to the legitimate owner of the route.</li>
<li>Finally, stop the attack by switching to the fourth terminal and typing:</li>
</ol>
<strong>./stop_rogue.sh</strong>

<ol start="12">
<li>You should notice a fast reconvergence to the original legitimate route in the third terminal window, which should now be delivering the original traffic. Additionally, you can check the BGP routing table again to see that the original path is being traversed.</li>
</ol>
<strong>&nbsp;</strong>

<h1><a name="_Toc14619"></a>BGP Hijacking Attack</h1>
&nbsp;

<strong>This is the graded part of the project. </strong>

<h2><a name="_Toc14620"></a>Part 1: Simple BGP Hijacking on a customized topology</h2>
&nbsp;

Your task is to replicate a different topology and attack scenario to demonstrate the effects of a Prefix Hijack Attack. <strong>Your goal is to impersonate true origin AS1 using the false origin AS6.</strong>

<strong>IMPORTANT NOTE: It’s recommended to build your attack scenario off the demo files. Make a backup of your demo files so you can refer to them as you modify the files. </strong>

<h3><a name="_Toc14621"></a>STEPS FOR YOUR ATTACK SCENARIO</h3>
&nbsp;

&nbsp;

Topology for the project’s hijack scenario (Figure 2 in the <a href="https://www2.cs.arizona.edu/~bzhang/paper/07-dsn-hijack.pdf">paper</a><a href="https://www2.cs.arizona.edu/~bzhang/paper/07-dsn-hijack.pdf">)</a>

<ol>
<li>First, according to the topology above taken from Figure 2 in the referenced <a href="https://www2.cs.arizona.edu/~bzhang/paper/07-dsn-hijack.pdf">paper</a><a href="https://www2.cs.arizona.edu/~bzhang/paper/07-dsn-hijack.pdf">.</a> Draw a topology map using any drawing tool of your choice. See Slide 7 of the presentation slides for an example of the level of detail desired in your topology diagram.</li>
</ol>
You may hand-draw your topology with pencil and paper and scan or photograph your drawing. All configuration values drawn on the map must<u> be legible</u>! Save your topology diagram in PDF format with the name fig2_topo.pdf. You must use this filename as part of your submission to receive credit for your diagram. <strong>We find that if you do your diagram first, the following steps will be much easier!</strong>

<ol start="2">
<li>We recommend making a copy of the code provided to you in the Project files (the full demo folder). This will make it easier to complete this project, and you will likely find it more approachable if you <strong><em>spend time exploring</em></strong> the demo code and <strong><em>fully understanding how each part works</em></strong> rather than immediately trying to edit the code.</li>
<li>Next, refer to the topology above or in the <a href="https://www2.cs.arizona.edu/~bzhang/paper/07-dsn-hijack.pdf">paper</a><a href="https://www2.cs.arizona.edu/~bzhang/paper/07-dsn-hijack.pdf">,</a> and create/edit the necessary files to reconstruct the topology.</li>
</ol>
(<strong>TIPS: BGP message won’t be propagated before establishing connectivity between nodes</strong>)

&nbsp;

Please figure out all the config files and python/shell scripts to edit to carry out the attack on the topology. After modifying all the necessary files, you should be able to use the commands from the demo to recreate the attack on the new topology you built in the Project Directory. You can assume the following:

&nbsp;

<ul>
<li><strong>All links are bidirectional peering links.</strong></li>
<li>Each AS advertises a single prefix: AS1: 11.0.0.0/8, AS2: 12.0.0.0/8, AS3:</li>
</ul>
13.0.0.0/8, AS4: 14.0.0.0/8, AS5: 15.0.0.0/8, AS6: 11.0.0.0/8

<ul>
<li>The number of hosts in each AS is the same as in the provided code (the demo).</li>
<li><strong>You don’t need to modify the helper scripts (run.py, webserver.py, connect.sh), and you should read through all the shell scripts</strong>.</li>
</ul>
&nbsp;

<ol start="4">
<li>Do <strong>not</strong> change passwords in zebra and conf files. If you change the passwords, the autograder will fail, resulting in 0 for the assignment. All passwords need to follow the demo and be ‘en’</li>
<li>Do not change the names of the config files, follow the pattern when creating new config files.</li>
<li>When complete, you should be able to use the commands from the demo to start a Rogue AS and demonstrate a similar change in routing table information as was shown in the demo and see the screen printout (website.sh) as in the demo. <strong>Your goal is to impersonate true origin AS1 using the false origin AS6. The attack should be observed on hosts connected to AS5.</strong></li>
</ol>
<strong>&nbsp;</strong>

<h2><a name="_Toc14622"></a>Part 2: Advanced BGP Hijacking on a customized topology</h2>
&nbsp;

Your task is to demonstrate an advanced BGP Hijacking based on the topology you just created.

<strong>Your goal is to also observe the attack on the whole network (besides the true origin).</strong>

<h3><a name="_Toc14623"></a>STEPS FOR YOUR ATTACK SCENARIO</h3>
&nbsp;

&nbsp;

Topology for the project’s hijack scenario (Figure 2 in the <a href="https://www2.cs.arizona.edu/~bzhang/paper/07-dsn-hijack.pdf">paper</a><a href="https://www2.cs.arizona.edu/~bzhang/paper/07-dsn-hijack.pdf">)</a>

<ol>
<li>After completing part 1, you should be able to see the attack on hosts connected to AS5. But for hosts connected to, say AS2, they won’t be affected. Why? (You may use “<em>./website.sh h2-1</em>” to check it)</li>
<li>Your goal is to also see the attack on hosts connected to other AS, using AS6 as a false origin (basically, impersonate AS1 and hijack the whole network).</li>
<li>Please read the <strong><em>sh</em></strong>, this is used to carry out the advanced attack. <strong>Create/edit necessary configs according to the <em>start_rogue_hard.sh</em> script</strong>.</li>
<li>After completion, you should observe hosts connected to AS2. (All the hosts connected to AS other than AS1 should be able to see the attack)</li>
<li>You may use “<em>./website.sh h[2-5]-[1,2]</em>” to check it</li>
<li><strong>You must use AS6 as the false origin, you should not modify start_rogue_hard.sh.</strong></li>
<li>Tips:
<ul>
<li>Try to understand the BGP protocol, different type of BGP Hijacking, and the rationale behind prefix hijacking.</li>
<li><strong>Only config modification is needed for this part. You should be able to reuse your bgp.py and other scripts from part 1. </strong></li>
<li>You are free to modify the prefix AS6 is broadcasting.</li>
</ul>
</li>
</ol>
<strong>&nbsp;</strong>

<h2><a name="_Toc14624"></a>Appendix: Configuration Debugging Tips</h2>
<ul>
<li>Ensure connectivity between routers suing Zebra before working on the BGP messages.</li>
<li>When viewing the BGP Tables note the “Status codes”. Give your topology enough time to converge before recreating the hijack simulation portion. It may take a minute or so for your topology to fully converge. You may continue to check the BGP Tables to determine whether the topology has converged</li>
<li>The order that you set up your peering links using addLink() matters. In previous projects, we manually selected which port on the switch to use. There is an optional parameter to the addLink() call which allows you to specify which switch port to use. In this project, you will not use those options. Therefore, the order of the links matters.</li>
<li>Some of the commands in the boilerplate code may not be necessary to complete the graded part. Some of it is there just so that you know it exists.</li>
<li>Check for more descriptive errors in the /logs directory. See the zebra files for the location of additional log files.</li>
<li>Run “links” on the Mininet CLI terminal to see if all links are connected and OK.</li>
<li>Run “net” on the Mininet CLI terminal to see if your ethernet links are connected as you expect.</li>
<li>Run “ifconfig -a” on all routers and hosts to ensure that all IP addresses are assigned correctly.</li>
<li>Run “sh ip bgp” and “sh ip bgp summary” on all routers.</li>
<li>The command <em>pingall</em> may not work and that is fine.</li>
<li>The website.sh may sometimes hang intermittently. If this happens restart the simulation. We are aware of this issue, and we keep this in mind as we grade your submission. You will not lose points if website.sh hangs so long as we are eventually able to run the simulation.</li>
<li>Again, read all the provided scripts.</li>
</ul>
&nbsp;

<h1><a name="_Toc14625"></a>What to Turn In:</h1>
<h2><a name="_Toc14626"></a>Your BGP Hijacking on a more complex topology</h2>
For this project you need to turn in all the files that are necessary for your code to run. Please submit your code to Gradescope. <strong>Be sure to use the -r option so your conf and logs subdirectories are part of the zip file</strong>

Use the following command to zip for t:

<strong>zip -r bgph.zip BGPHijacking/ </strong>

You need to make sure the pdf file fig2_topo.pdf is present inside your BGPHijacking directory along with all files and directories to run the attack scenario you created. Run the above zip command when above your project folder. Zip the directory BGPHijacking<strong>. </strong>All the files and folders needed must be in the BGPHijacking folder – <strong>zip the files in the VM using the Linux command is recommended.</strong>

Please submit the zip archive to Gradescope section <strong>“BGP Hijacking”</strong>. And please note that:

<ul>
<li>Improper zip structure will result in Gradescope autograder failure, please adjust the folder structure and resubmit if you encounter “Sanity Test Failure” on Gradescope</li>
<li>The &nbsp;&nbsp;&nbsp;&nbsp; correct &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; folder &nbsp; structure &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; should show</li>
</ul>
“BGPHijacking/” as a folder in front when uploading onto Gradescope

<ul>
<li>Please note that the autograder may take up to 10 minutes to process your assignment. As the deadline approaches and traffic increases, the grading time may be further delayed, and in some cases, the system may time out. To avoid these issues, we strongly recommend submitting your assignment early. We are not responsible for delays caused by last-minute submissions.</li>
</ul>
<strong>&nbsp;</strong>

<h2><a name="_Toc14627"></a>WHAT YOU CAN AND CAN NOT SHARE</h2>
While discussion of the project, in general, is always permitted on Edstem, you are not permitted to share your code generated for the graded part. You may quote snippets of the unmodified skeleton code provided to you when discussing the project.

<ul>
<li>You may <strong>not </strong>share the topology diagram you created in. (private post to instructors is always OK)</li>
<li>You may not share your IP addresses publicly (private post to instructors is always OK)</li>
<li>Sharing of completed code pseudo code is ok, but if in doubt, please make a private post to the instructors.</li>
</ul>
&nbsp;

<strong>RUBRIC</strong> (out of 150 points)

<table width="632">
<tbody>
<tr>
<td width="61">5 pts</td>
<td width="87">Fig 2 Topo

Diagram
</td>
<td width="484">For turning in the correctly named Topology diagram file: <strong>fig2_topo.pdf </strong>

Please use legible configuration values! Even autograder give full points on the diagram, we will manually deduct points of this part if it’s not legible.
</td>
</tr>
<tr>
<td width="61">125 pts</td>
<td width="87">BGPHijacking

Part 1
</td>
<td width="484">For accurately recreating the topology, links, router configuration, and attack per the instructions. <strong>Partial credit</strong> is available for this rubric item as follows:

10 points for efforts in router configuration (zebra/bgp).

30 points for accurately recreating the topology, links, connectivity.

40 points for seeing default message when you run <em>website.sh</em>, on hosts h[1-5]-[1,2], we will randomly choose some hosts to test.

40 points for seeing attack message with <em>website.sh h5-1</em> after running start_rogue.sh, and default message on other hosts.

5 points for seeing default message after stop_rogue.sh is run.

&nbsp;
</td>
</tr>
<tr>
<td width="61">20 pts</td>
<td width="87">BGPHijacking

Part 2
</td>
<td width="484">20 points for seeing default message on h1-1, and attack message on other hosts (h[2-5]-[1,2]). We will randomly choose some hosts to test.</td>
</tr>
</tbody>
</table>
&nbsp;

<a href="https://github.com/mininet/mininet/wiki/BGP-Path-Hijacking-Attack-Demo">[</a><a href="https://github.com/mininet/mininet/wiki/BGP-Path-Hijacking-Attack-Demo">1] </a><a href="https://github.com/mininet/mininet/wiki/BGP-Path-Hijacking-Attack-Demo">T</a>his Project inspired by a Mininet Demo originally presented at SIGCOMM 2014.

Bibliography

Cloudflare. (n.d.). Retrieved 2020, from cloudflare.com:

https://www.cloudflare.com/learning/security/glossary/bgp-hijacking/
