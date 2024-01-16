Reproduction of how the Prometheus Exporter does not return any data if used in a dotnet 6 project.

Inside this Repo you will find two completely identical projects, the only distinction being that one targets net6, while the other targets net8.

To run a project, navigate to either WebMetric6 or WebMetric8.
For WebMetric6, use:
```
docker build -t temp6 .
docker run -p 8080:80 temp6
```
For WebMetric8, use:
```
docker build -t temp8 .
docker run -p 8080:8080 temp8
```

Now navigate to http://localhost:8080/ to generate some metrics, then head over to http://localhost:8080/metrics to see metrics if you ran the WebMetric8 project, or if you ran WebMetric6, to see `# EOF`.