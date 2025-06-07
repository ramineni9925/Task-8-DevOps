
  <h1>🚀 DevOps Internship - Task 8: Running a Java Maven Build in Jenkins</h1>

  <h2>📌 Objective</h2>
  <p>Learn how to set up a Jenkins pipeline to build a simple Java application using Maven, taking the next step into Continuous Integration/Continuous Deployment (CI/CD).</p>

  <h2>📋 What I Did</h2>
  <ul>
    <li>Built a simple "Hello World" Java application</li>
    <li>Automated the build process using Jenkins</li>
    <li>Configured Maven as the build tool</li>
    <li>Verified the build success through Jenkins console output</li>
  </ul>

  <h2>🛠 Tools Used</h2>
  <ul>
    <li>Jenkins (via Docker)</li>
    <li>Apache Maven 3.9.10</li>
    <li>Java JDK 17.0.15</li>
    <li>Git for version control</li>
  </ul>

  <h2>📂 Project Structure</h2>
  <pre>
Running-a-Java-Maven-Build-Job-in-Jenkins/
├── src/
│   └── main/
│       └── java/
│           └── com/
│               └── example/
│                   └── HelloWorld.java
├── pom.xml
├── jenkins-screenshot.png
├── local-test.png
└── README.md
  </pre>

  <h2>🚀 Step-by-Step Implementation</h2>

  <h3>1. Created the Java Application</h3>
  <p><strong>File:</strong> <code>src/main/java/com/example/HelloWorld.java</code></p>
  <pre><code>public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, Jenkins + Maven!");
    }
}</code></pre>

  <h3>2. Configured Maven Build</h3>
  <p><strong>File:</strong> <code>pom.xml</code></p>
  <pre><code>&lt;project&gt;
  &lt;modelVersion&gt;4.0.0&lt;/modelVersion&gt;
  &lt;groupId&gt;com.example&lt;/groupId&gt;
  &lt;artifactId&gt;hello&lt;/artifactId&gt;
  &lt;version&gt;1.0&lt;/version&gt;
  &lt;build&gt;
    &lt;plugins&gt;
      &lt;plugin&gt;
        &lt;groupId&gt;org.apache.maven.plugins&lt;/groupId&gt;
        &lt;artifactId&gt;maven-compiler-plugin&lt;/artifactId&gt;
        &lt;version&gt;3.9.10&lt;/version&gt;
        &lt;configuration&gt;
          &lt;source&gt;1.8&lt;/source&gt;
          &lt;target&gt;1.8&lt;/target&gt;
        &lt;/configuration&gt;
      &lt;/plugin&gt;
    &lt;/plugins&gt;
  &lt;/build&gt;
&lt;/project&gt;</code></pre>

  <h3>3. Set Up Jenkins via Docker</h3>
  <pre><code>docker run -d --name jenkins -p 8080:8080 -p 50000:50000 jenkins/jenkins:lts</code></pre>

  <h3>4. Configured Jenkins</h3>
  <ul>
    <li>Installed suggested plugins</li>
    <li>Created admin user</li>
    <li>Configured Maven in <em>Manage Jenkins &gt; Tools</em></li>
  </ul>

  <h3>5. Created Jenkins Job</h3>
  <ul>
    <li><strong>Type:</strong> Freestyle project</li>
    <li><strong>Source Code Management:</strong> GitHub repository</li>
    <li><strong>Build Step:</strong> Invoke top-level Maven targets</li>
    <li><strong>Maven Version:</strong> Maven-3.9.10</li>
    <li><strong>Goals:</strong> clean package</li>
  </ul>

  <h3>6. Executed the Build</h3>
  <p>Triggered the build manually and verified success in the console output.</p>

  <h2>✅ Successful Build Screenshot</h2>
  <img src="jenkins-screenshot.png" alt="Jenkins Build Screenshot" width="600"/>

  <h2>💡 Key Learnings</h2>
  <ul>
    <li>Jenkins Jobs: Automated build/test workflows</li>
    <li>Maven Lifecycle: Understanding clean and package phases</li>
    <li>CI/CD Fundamentals: First step in automation pipeline</li>
    <li>Troubleshooting: Reading console output to debug failures</li>
  </ul>

  <h2>❓ Interview Questions & Answers</h2>
  <ul>
    <li><strong>What is Jenkins?</strong> <br>Open-source automation server for CI/CD pipelines.</li>
    <li><strong>How do you create a Jenkins job?</strong> <br>New Item → Enter name → Select Freestyle project → Configure build steps.</li>
    <li><strong>What is Maven used for?</strong> <br>Build automation tool for Java projects (dependency management, compilation, packaging).</li>
    <li><strong>How does Jenkins use build tools like Maven?</strong> <br>Jenkins executes Maven commands (e.g., <code>mvn clean package</code>) via build steps.</li>
    <li><strong>What is the difference between compile and package in Maven?</strong> <br><code>compile</code>: Builds source code → .java to .class <br><code>package</code>: Compiles + packages into distributable format (JAR/ZIP)</li>
    <li><strong>Where do you configure tools in Jenkins?</strong> <br>Manage Jenkins → Tools (global configurations for JDK, Git, Maven).</li>
    <li><strong>How do you debug a failed Jenkins build?</strong> <br>Check Console Output for error messages and stack traces.</li>
  </ul>

  <h2>⚠️ Troubleshooting Tips</h2>
  <ul>
    <li>Check Maven installation in Jenkins</li>
    <li>Ensure correct file paths in the repository</li>
    <li>Verify Java version compatibility</li>
    <li>Check internet connectivity for downloading dependencies</li>
    <li>Always check Console Output first for errors</li>
  </ul>

  <p>This project demonstrates fundamental CI/CD concepts using industry-standard tools — a crucial skill for DevOps engineers.</p>
</body>
</html>
