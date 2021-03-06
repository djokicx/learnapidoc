---
title: Documenting code samples and tutorials
permalink: /docapis_codesamples_bestpractices.html
keywords:
course: "Documenting REST APIs"
weight: 5.6
sidebar: docapis
section: docnonref
path1: /docnonref.html
---

As you write documentation for developers, you'll start to include more and more code samples. You might not include these more detailed code samples with the endpoints you document, but as you create tasks and more sophisticated workflows about how to use the API to accomplish a variety of tasks, you'll end up leveraging different endpoints and showing how to address a variety of scenarios. The following sections list some best practices around code samples.

{% if site.format == "web" %}
* TOC
{:toc}
{% endif %}

## Code samples are like candy for developers

Code samples play an important role in helping developers use an API. No matter how much you try to explain and narrate *how*, it's only when you *show* something in action that developers truly get it. Additionally, although some project teams feel that the reference documentation is all you need, that's only because the team is already familiar with the API. In an article on the Programmable Web called [The Six Pillars of Complete Developer Documentation
](https://www.programmableweb.com/news/six-pillars-complete-developer-documentation/2011/09/12), the authors explain:

> While a developer’s guide should walk a developer through the basic usage of an API and its functionality, it can’t cover every possible use of that API in a coherent way. That is where articles and tutorials come in, to teach developers tangential or specialized uses of an API, like combining it with another service, framework, or API.

Developers often make the mistake of assuming that their developer audience has a skill set similar to their own, without recognizing different developer specializations. Developers will often say, "If the user doesn't understand this code, he or she shouldn't be using our API."

It might be important to remind developers that users often have technical talent in different areas. For example, a user might be an expert in Java but only mildly familiar with JavaScript. Also, as a technical writer rather than a developer, you aren't your audience. Developers aren't newbies when it comes to code, but different developers have different specializations. Someone who is a database programmer will have a different skill set than someone who is a Java developer who will have a different skillset from a JavaScript developer, and so on. Given these differences and the likely possibility that you will have many novice (or unfamiliar) users, more extensive code tutorials are warranted.

{% include course_image.html size="medium" border="true" filename="nonref_codetutorials" ext_print="png" ext_web="svg" alt="Code tutorials" caption="Code is in another language, so as much as you might try to describe the communication in this other language through text, it often falls short. When developer see code, they can often read the code and understand it natively." %}

## Focus on the why, not the what

In any code sample, you should focus your explanation on the *why*, not the *what*. Explain why you're doing what you're doing, not the detailed play-by-play of what's going on.

Here's an example of the difference:

* **what**: In this code, several arguments are passed to jQuery's `ajax` method. The response is assigned to the data argument of the callback function, which in this case is `success`.
* **why**: Use the `ajax` method from jQuery because it allows cross-origin resource sharing (CORS) for the weather resources. In the request, you submit the authorization through the header rather than including the API key directly in the endpoint path.

## Explain your company's code, not general coding

Developers unfamiliar with common code not related to your company (for example, the `.ajax()` method from jQuery) should consult outside sources for tutorials about that code. You shouldn't write your own version of another service's documentation. Instead, focus on the parts of the code unique to your company. Let the developer rely on other sources for the rest (feel free to link to other sites).

{% include random_ad.html %}

## Keep code samples simple

Code samples should be stripped down and as simple as possible. Providing code for an entire HTML page is probably unnecessary. But including it doesn't hurt anyone, and for newbies it can help them see the big picture.

Avoid including a lot of styling or other details in the code that will potentially distract the audience from the main point. The more minimalist the code sample, the better.

When developers take the code and integrate it into a production environment, they will make a lot of changes to account for scaling, threading, and efficiency, and other production-level factors.

## Add both code comments and before-and-after explanations

Your documentation regarding the code should mix code comments with some explanation either after or before the code sample. Brief code comments are set off with forward slashes `//` in the code; longer comments are set off between slashes with asterisks, like this: `/* .... */`.

Comments within the code are usually short one-line notes that appear after every 5-10 lines of code. You can follow up this code with more robust explanations later.

This approach of adding brief comments within the code, followed by more robust explanations after the code, aligns with principles of progressive information disclosure that help align with both advanced and novice user types.

## Make code samples copy-and-paste friendly

Many times developers will copy and paste code directly from the documentation into their application. Then they will usually tweak it a little bit for their specific parameters or methods.

Make sure that the code works. When I first used used some sample `ajax` code, the `dataType` parameter was actually spelled `datatype`. As a result, the code didn't work (it returned the response as text, not JSON). It took me about 30 minutes of troubleshooting before I consulted the [`ajax` method](http://api.jquery.com/jquery.ajax/) and realized that it should be `dataType` with a capital `T`.

Ideally, test out all the code samples yourself. This allows you to spot errors, understand whether all the parameters are complete and valid, and more. Usually you just need a sample like this to get started, and then you can use the same pattern to plug in different endpoints and parameters. You don't need to come up with new code like this every time.

## Provide a sample in your target language

With REST APIs, developers can use pretty much any programming language to make the request. Should you show code samples that span across various languages?

Providing code samples is almost always a good thing, so if you have the bandwidth, follow the examples from Evernote and Twilio. However, providing just one code example in your audience's target language is probably enough, if needed at all. You could also skip the code samples altogether, since the approach for submitting an endpoint follows a general pattern across languages.

Remember that each code sample you provide needs to be tested and maintained. When you make updates to your API, you'll need to update each of the code samples across all the different languages.

## Code samples require heavy maintenance with new releases

Getting into code samples leads us more toward user guide tasks than reference tasks. However, keep in mind that code samples are a bear to maintain. When your API pushes out a new release, will you check all the code samples to make sure the code doesn't break with the new API (this is called regression testing by QA).

What happens if new features require you to change your code examples? The more code examples you have, the more maintenance they require.

## General code samples

Although you could provide general code samples for every language with every call, it's usually not done. Instead, there's often a page that shows how to work with the code in various languages. For example, with the Wunderground Weather API, they have a page that shows general code samples:

<a href="http://www.wunderground.com/weather/api/d/docs?d=resources/code-samples&MR=1"><img src="images/wundergroundcodesamples.png" alt="Wunderground code samples" /></a>

The OpenWeatherMap API has a number of [example integrations](https://openweathermap.org/examples) that provide more advanced user interfaces with weather.

**Samples of code tutorials**

The following are a few samples of code tutorials in API documentation.

{: .note}
This section is currently under construction ...

**Eventful**

{% include course_image.html url="http://api.eventful.com/tools/tutorials/search" filename="eventfulcodesample" ext_print="" ext_web="" alt="Eventful code samples" caption="Eventful code samples" %}

**Twilio**

{% include course_image.html url="https://www.twilio.com/docs/quickstart" filename="twiliocodesamples" ext_print="png" ext_web="png" alt="Twilio code samples" caption="Twilio code samples" %}

**Mailchimp**

{% include course_image.html url="http://developer.mailchimp.com/documentation/mailchimp/guides/manage-subscribers-with-the-mailchimp-api/" filename="mailchimpcodesamples" ext_print="png" ext_web="png" alt="Mailchimp code samples" caption="Mailchimp code samples" %}

**IBM Watson**

{% include course_image.html url="https://console.bluemix.net/docs/services/conversation/tutorial.html#tutorial" filename="ibmwatsoncodesamples" ext_print="png" ext_web="png" alt="IBM Watson code samples" caption="IBM Watson code samples" %}

## Code samples for weather API

Earlier in the course we walked through [each element of reference documentation](docapis_new_endpoint_to_doc.html) for a fictitious new endpoint (`surfreport`) for the weather API we were working with. Let's return briefly to that scenario and assume that we also want to add a code tutorial for showing the surfreport on a web page. What might that tutorial look like? Here's an example:

<div class="docSample">

<h2>Code tutorial for surfreport endpoint</h2>

<p>The following code samples shows how to use the <code>surfreport</code> endpoint to get the surf height for a specific beach.</p>

{% if site.format == "web" or site.format == "pdf" %}
{% highlight javascript %}
<!DOCTYPE html>
<head>
<script src="http://code.jquery.com/jquery-2.1.1.min.js"></script>
<script>
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.openweathermap.org/surfreport/25&days=1",
  "method": "GET"
}

$.ajax(settings).done(function (response) {
  console.log(response);
  $("#surfheight").append(response.surfreport.conditions);
});
</script>
</head>
<body>
<h2>Surf Height</h2>
<div id="surfheight"></div>
</body>
</html>
{% endhighlight %}

{% elsif site.format == "kindle" %}

<pre>
&lt;!DOCTYPE html&gt;
&lt;head&gt;
&lt;script src=&quot;http://code.jquery.com/jquery-2.1.1.min.js&quot;&gt;&lt;/script&gt;
&lt;script&gt;
var settings = {
  &quot;async&quot;: true,
  &quot;crossDomain&quot;: true,
  &quot;url&quot;: &quot;http://api.openweathermap.org/surfreport/25?days=1&amp;units=metric&quot;,
  &quot;method&quot;: &quot;GET&quot;
}

$.ajax(settings).done(function (response) {
  console.log(response);
  $(&quot;#surfheight&quot;).append(response.query.results.channel.surf.height);
});
&lt;/script&gt;
&lt;/head&gt;
&lt;body&gt;
&lt;h2&gt;Surf Height&lt;/h2&gt;
&lt;div id=&quot;surfheight&quot;&gt;&lt;/div&gt;
&lt;/body&gt;
&lt;/html&gt;
</pre>
{% endif %}

<p>In this example, the <code>ajax</code> method from jQuery is used because it allows us to load a remote resource asynchronously.</p>

<p>In the request, you submit the authorization through a query string URL. The endpoint limits the days returned to 1 in order to increase the download speed.</p>

<p>For demonstration purposes, the response is assigned to the <code>response</code> argument of the <code>done</code> method, and then written out to the <code>surfheight</code> tag on the page.</p>

<p>We're just getting the surf height, but there's a lot of other data you could choose to display.</p>
</div>

Obviously, one could go into a lot more detail with the explanation, even going line by line through the code. But here the commentary is already about half the length of the code.
