<!-- .slide: data-state="title" -->

# Mastering Code
JSON

>>Author Notes:
- JSON has become a standard for sharing data, especially inside web application. It's a surprisingly simple format that translates easily into JavaScript Objects.

---

## JSON

<ul>
  <li class="fragment">JavaScript Object Notation</li>
  <li class="fragment">Based on JavaScript Objects</li>
  <li class="fragment">Language independent</li>
  <li class="fragment">Easy to read and parse</li>
</ul>

>>Author Notes:

1. JSON stands for JavaScript Object Notation and it's a text format for sharing data between clients and servers.

1. It's based on JavaScript Objects, so it's very similar to the way you can structure objects within JavaScript, but not identical. For example, the JSON format isn't designed to have embedded methods, which is one of the powerful features that gives you some object oriented features in JavaScript.

1. JSON is also language independent and there are many implementations available in different languages. So just because it's called JavaScript Object Notation, doesn't mean that it can only be used with JavaScript.

1. JSON is designed to be easy to read and parse, although there is a lot of punctuation in JSON and it's not so easy to write without making mistakes.

1. In a previous video, I showed you how to use AJAX to read an existing JSON data file, let's take a look at how we can understand and access that data in our page.

---
## Resources
<ul>
  <li><a href="http://json.org/">JSON Official Site</a> | <a href="http://jsoneditoronline.org/">JSON Editor Online</a></li>
  <li style="list-style: none;">
    <ul>
      <li style="margin-bottom: 10px"><a href="https://www.linkedin.com/learning/javascript-and-json-integration-techniques?u=2125562">JavaScript and JSON: Integration Techniques</a></li>
      <li style="margin-bottom: 10px"><a href="https://www.linkedin.com/learning/javascript-and-ajax-integration-techniques">JavaScript and AJAX: Integration Techniques</a></li>
      <li style="margin-bottom: 10px"><a href="https://www.linkedin.com/learning/building-web-applications-with-ajax/welcome">Building Web Applications with Ajax</a></li>
      <li style="margin-bottom: 10px"><a href="https://www.linkedin.com/learning/learn-api-documentation-with-json-and-xml?u=2125562">Learn API Documentation with JSON and XML</a></li>
    </ul>
  <li style="list-style: none; font-size: 1.3rem;"><a href="hhttps://www.linkedin.com/in/planetoftheweb">linkedin.com/in/planetoftheweb</a> | <a href="https://www.twitter.com/planetoftheweb">@planetoftheweb</a> | <a href="https://www.linkedin.com/learning/instructors/ray-villalobos">courses</a> | <a href="https://raybo.org">raybo.org</a></li>
</ul>

>> Author Notes:
- Here's some pages where you can get more information about working with this technology as well as some related courses with information on developer tools. If you have some ideas for this weekly series, maybe you want to share with me some questions you've been asked or have asked in interviews connect with me in LinkedIn or just about any social media network like twitter or github @planetoftheweb.

https://www.dropbox.com/s/g78cocil517k4ca/2017-06-26_21-24-56.png
https://www.dropbox.com/s/f74vukg0pyspq1h/2017-06-26_21-26-42.png

```
var data, DOMNode;
var request = new XMLHttpRequest();

DOMNode = document.querySelector('.artists');

request.open('GET', 'js/data.json');

request.onreadystatechange = function() {
  if(
    request.status === 200 &&
    request.readyState === 4
  ) {
    data = JSON.parse(request.responseText);

    for (var item in data.artists) {
      if (data.artists.hasOwnProperty(item)) {
        var listItem = document.createElement('div');
        listItem.className = 'artist';
        listItem.innerHTML = '<h4>' + data.artists[item].name + '</h4>'
          + '<p>' + data.artists[item].bio + '</p>';
        DOMNode.appendChild(listItem);
      }
    }
  }
}

request.send();
```
