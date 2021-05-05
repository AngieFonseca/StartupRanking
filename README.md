# StartupRanking
Challenge
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

public class Test {
   private WebDriver driver;
   By principalPageLocator = By.className("col-md-6");
   By userName = By.className("user-submitted-name");
   By userEmail = By.className("user-submitted-email");
   By userProduct = By.className("user-submitted-title");
   By userUrl = By.className("user-submitted-url");
   By userContent = By.className("user-submitted-content");
   
 //  @Before
     public void setUp(){
	   System.setProperty("webdriver.chrome.driver", "./chromeDriver/chromedriver.exe");  
       driver = new ChromeDriver();
       driver.manage().window().maximize();
       driver.get("https://apprater.net/add/");
       
   }
   
 //  @After 
   
   public void tearDown() throws Exception {
//	   driver.quit();
   }
   
 //  @Test
   public void sendMessage() throws InterruptedException {
	   
	   Thread.sleep(2000);
	   if (driver.findElement(principalPageLocator).isDisplayed()) {
		   driver.findElement(userName).sendKeys("Angie Fonseca");
		   driver.findElement(userEmail).sendKeys("angie@hotmail.com");
		   driver.findElement(userProduct).sendKeys("Fotografia de producto");
		   driver.findElement(userUrl).sendKeys("www.google.com");
		   driver.findElement(userContent).sendKeys("Este es un mensaje de prueba de ANGIE FONSECA");
	   }
	   
	   
	   
   }
   
}
