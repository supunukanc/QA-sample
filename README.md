# QA-sample
My first QA automation code
package automationFramework;
 
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.firefox.FirefoxDriver;
public class Gecko_Driver {
 
 public static void main(String[] args) throws InterruptedException {
 
 System.setProperty("webdriver.gecko.driver", "C:\\\\Users\\\\supun\\\\Downloads\\\\geckodriver-v0.24.0-win64\\\\geckodriver.exe");
 WebDriver driver = new FirefoxDriver();
 driver.get("http://automationpractice.com/index.php");

 driver.findElement(By.className("sf-with-ul")).click();
 driver.findElement(By.className("checker")).click();
 
 WebElement Checkbx = driver.findElement(By.xpath("/html/body/div/div[2]/div/div[3]/div[1]/div[2]/div[1]/form/div/div[2]/ul/li[3]/label/a"));
 Checkbx.click();
 Thread.sleep(2000L);
 
 driver.findElement(By.xpath("/html/body/div/div[2]/div/div[3]/div[1]/div[2]/div[1]/form/div/div[3]/ul/li[2]/label/a")).click();
 Thread.sleep(2000L);
 //driver.findElement(By.xpath("/html/body/div/div[2]/div/div[3]/div/div/div/div[4]/form/div/div[3]/div/p/button/span")).click();
 //driver.findElement(By.xpath("/html/body/div/div[2]/div/div[3]/div[2]/ul/li[1]/div/div[2]/div[2]/a[2]/span")).click();

 driver.get("http://automationpractice.com/index.php?id_product=2&controller=product");
 Thread.sleep(2000L);
 driver.findElement(By.xpath(".//*[@id='add_to_cart']/button")).click();
 Thread.sleep(2000L);
 driver.findElement(By.xpath(".//*[@id='layer_cart']/div[1]/div[2]/div[4]/a/span")).click();
 Thread.sleep(2000L);
 driver.findElement(By.xpath("/html/body/div/div[2]/div/div[3]/div/p[2]/a[1]/span")).click();
 Thread.sleep(2000L);

 
 driver.findElement(By.className("login")).click();
 driver.findElement(By.xpath(".//*[@id='email']")).sendKeys("careware@gmail.com");
 driver.findElement(By.id("passwd")).sendKeys("password");
 driver.findElement(By.cssSelector("#SubmitLogin")).click();
 String text = driver.findElement(By.xpath(".//*[@id='center_column']/div[1]/ol/li")).getText();
 Assert.assertEquals(text, "Authentication failed.");
 Thread.sleep(3000L);
 driver.quit();
 }
}
