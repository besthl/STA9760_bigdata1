# Analyzing Millions of NYC Parking Violations
The NYC Open Data project makes available freely data published by NYC agencies and other partners. These datasets range from a few thousand rows to millions, depending on department and time frame. For the really large datasets, attempting to download is unfeasible as some of these files are upwards of 5-10 Gbs in size. As such, this service offers an Application Programming Interface - known colloquially as an API - for ease of querying and loading the data via web requests in terminal (via curl) or code (via python, javascript, etc). Furthermore, these APIs are made available via the Socrata Open Data API, which provides a well established and easy to use set of conventions for querying public datasets such as the one we will be using. For this project, we will leverage a python client of the Socrata API to connect to the Open Parking and Camera Violations (OPCV) API, load all the data into an ElasticSearch instance, and visualize / analyze with Kibana. To accomplish this, we will leverage our knowledge of containerization, working with the terminal and python scripting. We will “share” our findings by deploying our docker images to Dockerhub and our code to Github.

# This is only for part 1.
___________________________
docker build -t bigdata1:2.0 .  
___________________________
docker run -e APP_KEY={YOUR_APP_KEY} -t bigdata1:2.0 python -m main --page_size=1000 --num_pages=4 --output=results.json
___________________________
docker login --username=besthl docker images docker tag e9ccc9990668 besthl/bigdata1:2.0 docker push besthl/bigdata1
