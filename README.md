# demo-vagrant
1. clone the project and build it
2. go to vagrant/Vagrantfile and change the path to shared folder
3. run `vagrant up` from the vagrant dir
4. after image is downloaded and machine is up, run `vagrant ssh`
5. go to mounted folder on the machine (should be "/java-projects" in the root)
6. run the app `java -Xdebug -Xrunjdwp:server=y,transport=dt_socket,address=8000,suspend=n -jar target/demo-0.0.1-SNAPSHOT.jar`
7. switch to IDE, for Eclipse go to 
   Run > Debug Configurations > Remote Java Application and create a new app:
   ![path](https://www.dropbox.com/s/26rpwhexfr80dwc/Screen%20Shot%202017-10-10%20at%2001.15.48.png?raw=true "Screenshot")
   IDEA should have similar options
8. Install a breakpoint in `com.example.demo.DemoController.capitalize(String)`
9. access http://localhost:9115/test/?input=somestring from browser
ER: the app should stop at the breakpoint
