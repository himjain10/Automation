package test;

import java.util.List;
import java.util.Set;
import java.util.concurrent.TimeUnit;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class LoginAmazon {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		
		System.setProperty("webdriver.chrome.driver", "chromedriver");
		WebDriver driver=new ChromeDriver();
		driver.get("https://www.amazon.in/");
		
		driver.manage().window().maximize();
		//driver.manage().timeouts().implicitlyWait(5000, TimeUnit.MILLISECONDS);
		
		WebElement searchdropdown =driver.findElement(By.id("searchDropdownBox"));
		//searchdropdown.click();
		
		WebElement searchtext =driver.findElement(By.id("twotabsearchtextbox"));
		searchtext.sendKeys("Samsung");
		
		WebElement submittext =driver.findElement(By.id("nav-search-submit-text"));
		submittext.click();
		
		//WebDriverWait wait = new WebDriverWait(driver,30);
	   // wait.until(ExpectedConditions.visibilityOfElementLocated(By.xpath("//div[@data-component-type='s-search-result']")));
	    List<WebElement> productlist = driver.findElements(By.xpath("//div[@data-component-type='s-search-result']//h2/a"));
	    List<WebElement> Pricelist = driver.findElements(By.xpath("//div[@data-component-type='s-search-result']//span[@class='a-price']"));
	    	
       System.out.println("Total Product is" + " "+productlist.size());
       
	    for (int i=0; i<productlist.size();i++)
 {
	  System.out.println(productlist.get(i).getText()+ " "+ Pricelist.get(i).getText());
 }
	    
	    String parentwindow=driver.getWindowHandle();
	String Expectedvalue=productlist.get(0).getText();
	productlist.get(0).click();
			Set<String> allwin=driver.getWindowHandles();
		for (String win: allwin)
		{
			System.out.println(win);
			if (!win.equals(parentwindow))
			{
			
				driver.switchTo().window(win);
			}
		}
		WebElement producttitle =driver.findElement(By.id("productTitle"));
		String title=producttitle.getText();
		if(title.equals(Expectedvalue))
		{
			System.out.println("Title is matched");
		}
		else
		{
			System.out.println("Titile is not matched");
		}
		
		
		driver.quit();

	   
      
}
}