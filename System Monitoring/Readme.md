# Site Monitoring

## Site Reliability Engineering (SRE)

## Monitoring components
Depending on how broad you want to be, we can find some or all of these components in the following topics:

* **Metrics:** This exposes a certain system resource, application action, or business characteristic as a specific point in time value. This information is obtained in an aggregated form; for example, you can find out how many requests per second were served but not the exact time for a specific request, and without context, you won't know the ID of the requests.

* **Logging:** Containing much more data than a metric, this manifests itself as an event from a system or application, containing all the information that's produced by such an event. This information is not aggregated and has the full context.

* **Tracing:** This is a special case of logging where a request is given a unique identifier so that it can be tracked during its entire life cycle across every system. Due to the increase of the dataset with the number of requests, it is a good idea to use samples instead of tracking all requests.

* **Alerting:** This is the continuous threshold validation of metrics or logs, and fires an action or notification in the case of a transgression of the said threshold.

* **Visualization:** This is a graphical representation of metrics, logs, or traces.

## Whitebox versus blackbox monitoring

### For more informaiton See
* [Wiki](https://en.wikipedia.org/wiki/Site_Reliability_Engineering)
* [Google](https://landing.google.com/sre/)
* [The Prometheus blog](https://prometheus.io/blog/2016/07/23/pull-does-not-scale-or-does-it)
* [Site Reliability Book](https://landing.google.com/sre/sre-book/chapters/monitoring-distributed-systems)
* [The USE Method](http://www.brendangregg.com/usemethod.html)
* [The RED Method](https://www.weave.works/blog/the-red-method-key-metrics-for-microservices-architecture)