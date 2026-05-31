# Day 11 - Install and Configure Apache Tomcat

## Objective

Install Apache Tomcat on App Server 3 (`stapp03`), configure a custom port, deploy a Java web application using a WAR file, and verify application accessibility.

---

## Task 1: Tomcat Deployment on Port 8089

### Requirements

* Install Tomcat on `stapp03`
* Configure Tomcat to run on port `8089`
* Deploy `ROOT.war`
* Verify application using:

  ```bash
  curl http://stapp03:8089
  ```

### Commands Used

Install Tomcat:

```bash
yum install -y tomcat
```

Update Tomcat Port:

```bash
vi /etc/tomcat/server.xml
```

Change:

```xml
<Connector port="8080" ...
```

To:

```xml
<Connector port="8089" ...
```

Deploy Application:

```bash
cp /tmp/ROOT.war /var/lib/tomcat/webapps/
```

Restart Service:

```bash
systemctl restart tomcat
systemctl status tomcat
```

Verify:

```bash
curl http://stapp03:8089
```

---

## Task 2: Tomcat Deployment on Port 3002

### Requirements

* Configure Tomcat to run on port `3002`
* Deploy `ROOT.war`
* Verify application using:

  ```bash
  curl http://stapp03:3002
  ```

### Commands Used

Update Tomcat Port:

```bash
vi /etc/tomcat/server.xml
```

Change:

```xml
<Connector port="8080" ...
```

or

```xml
<Connector port="8089" ...
```

To:

```xml
<Connector port="3002" ...
```

Deploy Application:

```bash
cp /tmp/ROOT.war /var/lib/tomcat/webapps/
```

Restart Service:

```bash
systemctl restart tomcat
```

Verify:

```bash
curl http://stapp03:3002
```

---

## Key Learnings

* Installing Apache Tomcat
* Managing Tomcat services using systemctl
* Configuring custom Tomcat ports
* Understanding Tomcat Connector configuration
* Deploying Java applications using WAR files
* ROOT.war deployment and root context mapping
* Verifying application availability using curl
* Basic troubleshooting of Tomcat deployments

---

## Result

Successfully installed and configured Apache Tomcat, deployed the Java web application using `ROOT.war`, and verified application accessibility on custom ports **8089** and **3002**.

