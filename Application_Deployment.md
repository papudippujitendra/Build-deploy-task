**Application Deployment**

**Step:1**

\*Launch 2 instances and name it as Build and Deploy.

\*Install java

![](media/image1.png){width="6.268055555555556in" height="1.275in"}

\*Install maven

![](media/image2.png){width="6.268055555555556in" height="0.375in"}

\*Clone the code from github.

![](media/image3.png){width="4.841666666666667in"
height="1.9402066929133859in"}

![](media/image4.png){width="6.268055555555556in"
height="0.6013888888888889in"}

\*mvn package

![](media/image5.png){width="6.268055555555556in"
height="0.7368055555555556in"}

\*Here the build will be Success.

![](media/image6.png){width="5.691666666666666in"
height="1.805366360454943in"}

**Step :2**

Take another server named as (Deploy).

\*Here we need to install Java and Tomcat.

\*Install java.

![](media/image1.png){width="6.268055555555556in"
height="1.6166666666666667in"}

\*Install Tomcat.

![](media/image7.png){width="6.268055555555556in"
height="0.3902777777777778in"}

untar the tomcat.

![](media/image8.png){width="6.268055555555556in"
height="0.7055555555555556in"}

Rename it.

![](media/image9.png){width="6.268055555555556in"
height="0.7944444444444444in"}

Comment in webapps/host manager and manager /META/context.xml

![](media/image10.png){width="6.268055555555556in"
height="0.4388888888888889in"}

![](media/image11.png){width="6.268055555555556in"
height="0.4847222222222222in"}

-   Change the password in conf/tomcat-user.xml

![](media/image12.png){width="5.541666666666667in"
height="0.7798611111111111in"}

Give port number in Security group as 8080

![](media/image13.png){width="6.268055555555556in" height="2.0375in"}

Start tomcat

./start.sh

![](media/image14.png){width="6.268055555555556in"
height="1.198611111111111in"}

Access Tomcat in web browser with public ip and port number.

![](media/image15.png){width="6.268055555555556in"
height="2.365972222222222in"}

Login to Manager with username and password(admin)

![](media/image16.png){width="6.268055555555556in"
height="2.7291666666666665in"}

Step :3(Build server).

-   Create ssh-keygen

-   Cat public id generated

-   Copy the public key and paste it in Deploy server (Authorized keys.

![](media/image17.png){width="6.268055555555556in"
height="0.8291666666666667in"}

> **Step:4(Deploy server)**
>
> \*Go to .ssh
>
> \*vi authorized keys paste the keys generated in Bulid server.
>
> **Step:5**

\*Copying the War file from Build server to Deploy server.

(scp /home/ubuntu/Javawebcal/target/\*.war
ubuntu@deploy-public-ip:/home/ubuntu/tomcat/webapps).

![](media/image18.png){width="6.268055555555556in"
height="0.44027777777777777in"}

![](media/image19.png){width="6.268055555555556in"
height="0.46111111111111114in"}

![](media/image20.png){width="6.268055555555556in"
height="2.5375in"}![](media/image21.png){width="3.733657042869641in"
height="3.4252963692038496in"}
