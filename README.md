# Python WebSocket chat application on cloudControl

First, let's clone the WebSocket Chat application from our repository on Github:

~~~bash
$ git clone git://github.com/cloudControl/python-websocket-example-app.git
$ cd python-websocket-example-app
~~~

Now you have a small but fully functional WebSocket chat application.

## Pushing and Deploying the App
Choose a unique name to replace the `APP_NAME` placeholder for your application and create it on the cloudControl platform:

~~~bash
$ cctrlapp APP_NAME create python
~~~

Push your code to the application's repository, which triggers the deployment image build process:

~~~bash
$ cctrlapp APP_NAME/default push
Counting objects: 18, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (16/16), done.
Writing objects: 100% (18/18), 317.54 KiB, done.
Total 18 (delta 3), reused 0 (delta 0)
       
-----> Receiving push
-----> No runtime.txt provided; assuming python-2.7.3.
-----> Preparing Python runtime (python-2.7.3)
-----> Installing Distribute (0.6.36)
-----> Installing Pip (1.3.1)
-----> Installing dependencies using Pip (1.3.1)
       ... 
       Successfully installed argparse gevent gevent-socketio gevent-websocket greenlet
       Cleaning up...
-----> Building image
-----> Uploading image (24M)
       
To ssh://APP_NAME@cloudcontrolled.com/repository.git
 * [new branch]      master -> master

~~~

Last but not least deploy the latest version of the app with the cctrlapp deploy command:

~~~bash
$ cctrlapp APP_NAME/default deploy
~~~

Congratulations, you can now see your WebSocket Chat app running at `http[s]://APP_NAME.cloudcontrolapp.com`. Please note that WebSocket would not work under the `APP_NAME.cloudcontrolled.com` subdomain. You can learn more about two routing tiers on our [official documentation]

