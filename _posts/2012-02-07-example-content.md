---
layout: post
title: It's time to bring out the programmer
---
### Task: Open the Firefox and go to Google.com

If you have been given the above task what will you do? You will open Firefox browser and type www.google.com. TATADA! Task finished!!!

Great! Now we are going to do this with the help of a program.

<div class="message">
  Remember! Coding is like teaching a small kid to do things. If we instruct it clearly, it will do miracles for you!
</div>

#### Your first automation code
Below is the `code` to open the firefox and  navigate to google.com

{% highlight java %}
package seleniumBasics;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.firefox.FirefoxDriver;
/**
 * 
 * @author Arulprasath
 *
 */
public class OpenGoogle {

public static void main(String[] args) throws InterruptedException {
	
	// code to open the browser and go to google.com
	System.setProperty("webdriver.gecko.driver", "path where u stored\\geckodriver.exe");  
		WebDriver driver = new FirefoxDriver();
		driver.get("http://www.google.com");
		driver.quit();
}

}

{% endhighlight %}

If you have knowledge in using Eclipse, you can straight away use the code. If you are unsure on what to do, Please follow the below steps.

#### How to write Your first automation code
* Open the installed Eclipse and click on File->New->Java Project
* Give a suitable project name. (seleniumBasics) and click on Finish.
* There will be an src folder inside the project. Right-click on that -> New -> Package ->Give a suitable package name (com.selenium.learning)
* Right click on that package -> new Class -> Give a name to the class (OpenGoogle)
* Copy the code from the above code segment and paste in the main method of your OpenGoogle class.

#### Are you getting the errors? Great you are on right track!

* You should get errors on lines like `import org.openqa.selenium.By; import org.openqa.selenium.WebDriver; import org.openqa.selenium.firefox.FirefoxDriver; WebDriver driver = new FirefoxDriver();` and `driver.findElement(By.name("q")).sendKeys("Bishop heber trichy");` 

* The errors are because, the code above is a combination of Java and Selenium (A web automation framework). So far we have created a Java project and we didn't instruct the compiler that our code is also related to Selenium. So we have to tell our compiler to refer, Selenium also. 

* Right click on your project->Build Path -> Configure Buildpath -> Libraries Tab -> Add External Jar

*And then add the Jar you have downloaded in " Installation and Environment set up " step.

* Also mention the correct path of the Gecko driver or chrome driver as explained in the code.

* If you are sing chrome driver then use, `System.setProperty("webdriver.chromedriver.driver", "path of your chrome driver\\chromedriver.exe"); `

<img src="{{'https://github.com/Arulprasath36/Arulprasath36.github.io/blob/master/assets/img/buildpath.PNG'}}" alt=""> 

#### Run the program
*If you had add the selenium Jar in the buildpath, your program is ready to run.

* Right click on the Java class -> Run As -> Java application.

* You will get some warnings, ignore those as of now. Your browser will be launched and it will launch the firefox and it will go to google.com

<div class="message">
  Cooool!!!! I ran my first automation program. It would be better if I know how it works.
</div>

#### Code Explanation
Congrats on successfully running the first program. Let me explain the code line by line here.

* `public static void main(String[] args) throws InterruptedException ` = This is where the program is begining to execute. The compiler will do the operations from here.

* `System.setProperty("webdriver.gecko.driver", "path where u stored\\geckodriver.exe");` = This is the line helps the compiler to invoke the Firefox browser when 
 `WebDriver driver = new FirefoxDriver(); ` is encountered. The code cannot directly click on the browser and open it, it needs a intermediary and that is the geckodriver or chrome driver. 
 
* `WebDriver driver = new FirefoxDriver();`= orders the program to open Firefox. `WebDriver driver = new ChromeDriver();`= for opening Chrome. Selenium supports all the major browsers. But I recommend not to use Internet Explorer.

* `driver.get("http://www.google.com");`= This will tell the browser to open google.com

* `driver.quit` will close the browser.

##Brain Teaser

driver.get() method is used to open any URL. There is another method, we can use to hit any URL. Find out what is that and How is that different from get method?

### Gists via GitHub Pages

Vestibulum id ligula porta felis euismod semper. Nullam quis risus eget urna mollis ornare vel eu leo. Donec sed odio dui.

{% gist 5555251 gist.md %}

Aenean eu leo quam. Pellentesque ornare sem lacinia quam venenatis vestibulum. Nullam quis risus eget urna mollis ornare vel eu leo. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Donec sed odio dui. Vestibulum id ligula porta felis euismod semper.

### Lists

Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Aenean lacinia bibendum nulla sed consectetur. Etiam porta sem malesuada magna mollis euismod. Fusce dapibus, tellus ac cursus commodo, tortor mauris condimentum nibh, ut fermentum massa justo sit amet risus.

* Praesent commodo cursus magna, vel scelerisque nisl consectetur et.
* Donec id elit non mi porta gravida at eget metus.
* Nulla vitae elit libero, a pharetra augue.

Donec ullamcorper nulla non metus auctor fringilla. Nulla vitae elit libero, a pharetra augue.

1. Vestibulum id ligula porta felis euismod semper.
2. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus.
3. Maecenas sed diam eget risus varius blandit sit amet non magna.

Cras mattis consectetur purus sit amet fermentum. Sed posuere consectetur est at lobortis.

<dl>
  <dt>HyperText Markup Language (HTML)</dt>
  <dd>The language used to describe and define the content of a Web page</dd>

  <dt>Cascading Style Sheets (CSS)</dt>
  <dd>Used to describe the appearance of Web content</dd>

  <dt>JavaScript (JS)</dt>
  <dd>The programming language used to build advanced Web sites and applications</dd>
</dl>

Integer posuere erat a ante venenatis dapibus posuere velit aliquet. Morbi leo risus, porta ac consectetur ac, vestibulum at eros. Nullam quis risus eget urna mollis ornare vel eu leo.

### Images

Quisque consequat sapien eget quam rhoncus, sit amet laoreet diam tempus. Aliquam aliquam metus erat, a pulvinar turpis suscipit at.

![placeholder](http://placehold.it/800x400 "Large example image")
![placeholder](http://placehold.it/400x200 "Medium example image")
![placeholder](http://placehold.it/200x200 "Small example image")

### Tables

Aenean lacinia bibendum nulla sed consectetur. Lorem ipsum dolor sit amet, consectetur adipiscing elit.

<table>
  <thead>
    <tr>
      <th>Name</th>
      <th>Upvotes</th>
      <th>Downvotes</th>
    </tr>
  </thead>
  <tfoot>
    <tr>
      <td>Totals</td>
      <td>21</td>
      <td>23</td>
    </tr>
  </tfoot>
  <tbody>
    <tr>
      <td>Alice</td>
      <td>10</td>
      <td>11</td>
    </tr>
    <tr>
      <td>Bob</td>
      <td>4</td>
      <td>3</td>
    </tr>
    <tr>
      <td>Charlie</td>
      <td>7</td>
      <td>9</td>
    </tr>
  </tbody>
</table>

Nullam id dolor id nibh ultricies vehicula ut id elit. Sed posuere consectetur est at lobortis. Nullam quis risus eget urna mollis ornare vel eu leo.

-----

Want to see something else added? <a href="https://github.com/poole/poole/issues/new">Open an issue.</a>
