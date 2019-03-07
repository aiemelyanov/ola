# Check PING Service URL availability
check_sql microservice using Spring Boot 

The detailed instructions to run *Red Hat Helloworld MSA* demo, can be found at the following repository: <https://github.com/redhat-helloworld-msa/helloworld-msa>


Dependancies
----------------------------
Java S2I

Build and Deploy Ping Monitor service locally
----------------------------
OpenShift Java S2I image, which allows you to automatically build and deploy your Java microservices, enables developers to automatically build, deploy and run java applications on demand, in OpenShift Container Platform, by simply specifying the location of their application source code or compiled java binaries. 

1. Create a new project or use an existing one.

oc new-project myproject
 

2. Before we start using the Java S2I image we need to tell OpenShift how to find it. This is done by creating an image stream. I’ve created an image stream definition here that you can download and use. To add the image stream to your project run the following command:

oc create -f openjdk-s2i-imagestream.json

3. Open the openshift console and navigate to the project you created and click on Add to Project.
https://developers.redhat.com/blog/wp-content/uploads/2017/02/image01.png

4. In the Browse Catalog window type openjdk in the search field.

https://developers.redhat.com/blog/wp-content/uploads/2017/02/image00.png



5. Click select and give the application a name and point to a git repo containing the application source code.


https://developers.redhat.com/blog/wp-content/uploads/2017/02/image03-768x376.png

https://github.com/aiemelyanov/ola/ola.git


6. Wait for the build to finish and click on the route (the URL in the upper right corner of the dashboard).
https://developers.redhat.com/blog/wp-content/uploads/2017/02/image02-1024x399.png

7. For the WildFly example application, the swagger console should now be displayed.
https://developers.redhat.com/blog/wp-content/uploads/2017/02/image04-1024x508.png

8. Try adding /api/hola to the address bar (or /api/ola for the Spring Boot example) and the outcome should be similar to the picture below.

http://ping-monitor-myproject.192.168.99.100.nip.io/

The application will be running at the following URL: <http://localhost:8080/api/ping-monitor>
http://ping-monitor-myproject.192.168.99.100.nip.io/api/ping-status


9. DONE



Deploy the application in OpenShift
-----------------------------------

1. Make sure to be connected to the OpenShift
2. Execute
 

