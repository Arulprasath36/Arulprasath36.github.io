---
layout: post
title: It's time to bring out the programmer
---
### Task 1: Open the Firefox and go to Google.com

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

<img src="{{'Arulprasath36.github.io/assets/img/buildpath.PNG'}}" alt=""> 

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

### Brain Teaser

driver.get() method is used to open any URL. There is another method, we can use to hit any URL. Find out what is that and How is that different from get method?

## Task 2: Refresh, Go back and Go forward

In the previous example, we have opened google.com. Now in this task, we are going to refresh the page, go forward and backward.

{% highlight java %}
WebDriver driver = new FirefoxDriver();
driver.navigate().to("http://www.google.com");
driver.findElement(By.name("q")).sendKeys("Bishop heber trichy");
driver.navigate().back();
driver.navigate().refresh();
driver.navigate().forward(); 
{% endhighlight %}

<div class="message">
Have you Noticed?
We are not using  `driver.get()`  to get the URL, we are using `driver.navigate().to()`. Because, using `get()` we can only hit the URL and we can't perform any other operations on that. We may need to perform operations like refresh,going forward and backward. In that case, we have to opt ofr `navigate` method !
</div>

### Code explanation

I think the method names are self explanatory, refresh method is to refresh, back method is to go back and forward is to go forward. Not tough right?

You should have a question. What's the work of this line `driver.findElement(By.name("q")).sendKeys("Bishop heber trichy");`

We are instructing the program to find the text box in google home page and asking it to type "Bishop Heber trichy". That's the job of this line.Don't worry about, if you don't get it <strong> How to find the element </strong> is our next topic. 

### Web element! web element! Where are you?

We have so many tasks to be done on a webpage. For instance, we might search, click a link, download a file, upload a file and so on. For all these operations, we have to find the respective element and click that. In our code also, we are going to do the same. Let's find out how to find the elements.

### It's time to know what's behind your browser

In order to find the web elements for scripting our automation program, we need to have a browser. I will be explaining this tutorial with Chrome.

I hope you remember in the previous example, we have seen a line of code, `driver.findElement(By.name("q")).sendKeys("Bishop heber trichy");`. Now lets know deeper about this.

So far in our example, we have opened a web page (google.com), but what do we do with google? We will search isn't it? Let's say I want to search the term "say cheese". Let's find how to do that in code.

<img src="{{'Arulprasath36.github.io/assets/img/finding text box.PNG'}}" alt=""> 

First we have to find the web element (the search box). Right click on your browser, you can see an option called *Inspect element* click on that.

<img src="{{'Arulprasath36.github.io/assets/img/inspect element.PNG'}}" alt="">

<img src="{{'Arulprasath36.github.io/assets/img/inspect search box.PNG'}}" alt=""> 

As you can see from the highlighted attributes,we can select the web element by *name,id,class,xpath* and several other attributes.

For this example, I have selected the search box by name and sent the input via *sendKeys()* method to enter the search term.

### Types of locators in Selenium

Selenium webdriver uses 8 locators to find the elements on web page. The following are the list of object identifier or locators supported by selenium.

Below is the list of locators to be used when scripting.

*id* Select element with the specified @id attribute.

*Name* Select first element with the specified @name attribute.

*Linktext* Select link (anchor tag) element which contains text matching the specified link text

*Partial Linktext* Select link (anchor tag) element which contains text matching the specified partial link text

*Tag Name* Locate Element using a Tag Name .

*Class* nameLocate Element using a class Name .

*Css* Select the element using css selectors. You can check here for Css examples and You can also refer W3C CSS Locators

*Xpath* Locate an element using an XPath expression.

<div class="message">
  Each locator is important and helps the programmer at different contexts. We will look at all these with examples.
</div>


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
