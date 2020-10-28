![test-cherry](https://socialify.git.ci/Hazem-Ben-Khalfallah/test-cherry/image?description=1&descriptionEditable=An%20Intellij%20Plugin%20that%20generates%20unit%20test%20methods%20from%20%40should%20tags%20in%20methods%20javadoc&font=Source%20Code%20Pro&language=1&logo=https%3A%2F%2Fgithub.com%2FHazem-Ben-Khalfallah%2Ftest-cherry%2Fraw%2Fmaster%2Fsnapshots%2Fcherry.png&owner=1&pattern=Brick%20Wall&stargazers=1&theme=Dark)

<h1>Test Cherry  Plugin </h1>

This Project is based on <a href="https://github.com/hablutzel1/GenerateTestCases">GenerateTestCases</a> project.


<h2>What it does?</h2>

**Test Cherry Plugin** aides java developers with writing **@should** style test units.

It aims to make it easier to make **TDD** with a really cool and easy approach that consist in
 annotating interface method with desired behaviours like this:
```java
public interface Person {

    /**
     *
     * @return
     * @should say hello, and nothing more that that
     */
    String sayHello();
}
```

So with this plugin you could generate a test class for this interface like this one automatically:
```java
import org.junit.Assert;
import org.junit.Test;

public class PersonTest {

	/**
	 * @see Person#sayHello()
	 * @verifies say hello, and nothing more that that
	 */
	@Test
	public void sayHello_shouldSayHelloAndNothingMoreThatThat() throws Exception {
		//TODO auto-generated
		Assert.fail("Not yet implemented");
	}
}
```

And then test your implementation code like this
```java
    public void sayHello_shouldSayHelloAndNothingMoreThatThat() throws Exception {
        assertThat(intance.sayHello(), is("hello world"));
    }
```

This way you can realize that for testing this behaviour you just wrote the @should annotation in the sut (system under test) in a really
descriptive way.
```java
    /**
     *
     * @return
     * @should say hello, and nothing more that that
     */
    String sayHello();
```
Auto-generated the test class and test method (using the plugin) and then tested the actual expected behaviour with (hamcrest style junit test):
```java
     assertThat(intance.sayHello(), is("hello world"));
```
Nothing more.

<h2>How to install</h2>

You can download the plugin "**testCherry**" directly from the IDE. 
* Go to **Settings > Plugin** enter "**testCherry**" 
* Hit enter 
* Select the plugin and press install.

<h2>How to use</h2>

* Open class in editor
* Add some test use cases using **@should** style annotation in method javadoc
* Press the "Generate Test Methods" ![logo](src/main/resources/images/logo.png) button in toolbar to generate test methods for each test use case.
![logo](snapshots/cherryTest_image1.png)
* A unit test will be generated automatically
![logo](snapshots/cherryTest_image2.png)

<h2>How to test from source code</h2>

* Clone repository
* run ```gradlew runIde```


<h2>How to build</h2>

* run ```gradlew build```

<h2>Change Notes</h2>

**2.0**
* Fix at should comment rename
* Fix test lib initialization
* Add plugin icon
       
**1.0**
* Implement test case generation for with IntelliJ IDEA version **2020.2**

<h2>Credits</h2>

* To <a href="https://github.com/hablutzel1/GenerateTestCases">GenerateTestCases</a> project author <a href="https://github.com/hablutzel1">Jaime Hablutzel</a>
* To <a href="https://wiki.openmrs.org/display/docs/Generate+Test+Case+Plugin">OpenMRS</a> team for @should style testing
