## Python web app to find plagiarism ##
### This is configured to deploy to Elastic Beanstalk ###

To run locally
```
$ pip install -r requirements.txt
$ python application.py

$ python application.py 
 * Serving Flask app "application" (lazy loading)
 * Environment: production
   WARNING: This is a development server. Do not use it in a production deployment.
   Use a production WSGI server instead.
 * Debug mode: off
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
```
To deploy to Elastic Beanstalk
```
$ eb init -p python-2.7 my-cc-assign --region us-east-2
$ eb init ## to create the ssh key pair to change your settings later, run eb init -i
$ eb create plagiarism-demo 
```
Once you execute this, it'll take ~5 minutes to create your environment with following resources:

- EC2 Instance
- Security Group for instance
- Load balancer
- Auto Scaling group
- Amazon CloudWatch alarms
- Domain name

Now you'll be able to open the website

```
$ eb open
```
Finally to do the cleanup,

```
$ eb terminate plagiarism-demo 
```
### The idea is developed for this code base for EBS deployment from the following blogs ###
[here](http://amunategui.github.io/idea-to-pitch/index.html)
&
[here](https://opensource.com/article/20/3/open-source-writing-tools)