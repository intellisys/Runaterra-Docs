# Overview

Ekko is the service in charge of the front-end dashboard that will consume all the services and serve as a unified access point to all intellisys services.

It's developed using the javaScript framework [Vue.js](https://vuejs.org)(Version 2) and its accountable for:

* Providing an easy user experience for each one of Runaterra's services.
* Providing front-end validations to user input

#### This Service should NOT

* Store any kind of sensitive information
* Perform business login


## Front-end

The base for Ekko's styles is the Vue.JS version of the template [CoreUI](http://coreui.io) which is built using [Twitter's Bootstrap](http://getbootstrap.com) framework.

> Template demo [here](http://getbootstrap.com).

# Notes

## [Axios](https://alligator.io/vuejs/rest-api-axios/) - (Cosuming api's)

Axios is a great http client library. It uses promises by default and runs on both the client and the server (which makes it appropriate for fetching data during server-side rendering). It’s also quite easy to use with Vue. Because it uses promises, you can combine it with async/await to get an amazingly concise and easy-to-use API.
