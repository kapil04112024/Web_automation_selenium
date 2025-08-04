# Web_automation_selenium
Selelnium file for automate the web
<br>
i am going to automate Proposal maker 


import org.openqa.selenium.By;
import org.openqa.selenium.JavascriptExecutor;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

import java.sql.SQLOutput;

public class Example_Selenium {
    public static void main(String[] args) throws InterruptedException {

        System.setProperty("webdriver.chrome.driver","src/test/resources/chromedriver.exe");
        WebDriver driver = new ChromeDriver();
        driver.get("http://192.168.3.95:8097/web/Login.aspx");
        String title = driver.getTitle();//input[@id='MainContent_TxtClientOrProposalName']
        System.out.println(title);
        driver.manage().window().maximize();
        driver.findElement(By.xpath("//input[@id='txtEmail']")).click();
        driver.findElement(By.xpath("//input[@id='txtEmail']")).sendKeys("kapil@factohr.com");
        driver.findElement(By.xpath("//input[@id='txtPassword']")).click();
        driver.findElement(By.xpath("//input[@id='txtPassword']")).sendKeys("123");
        driver.findElement(By.xpath("//input[@id='btnLogin']")).click();
        driver.findElement(By.xpath("//a[@id='HyperLink2']")).click();
        driver.findElement(By.xpath("//span[normalize-space()='Add New Client']")).click();
        driver.findElement(By.xpath("//input[@id='MainContent_txt_ClientName']")).click();
        driver.findElement(By.xpath("//input[@id='MainContent_txt_ClientName']")).sendKeys("Atul auto pvt ltd");
        Thread.sleep(3000);
        driver.findElement(By.xpath("//select[@id='MainContent_ClientTypeDropDownList']")).click();
        Thread.sleep(2000);
        driver.findElement(By.xpath("//*[@id=\"MainContent_ClientTypeDropDownList\"]/option[2]")).click();
        Thread.sleep(3000);
       // driver.findElement(By.xpath(" //label[normalize-space()='Browse Files']")).click();
        WebElement fileInput = driver.findElement(By.id("FileUploadInput"));
        fileInput.sendKeys("C:\\Users\\kapils\\Pictures\\Saved Pictures\\download.jpg");
        driver.findElement(By.xpath("//a[@id='MainContent_LinkButton1']")).click();
// Step 2: Click Save button
        //driver.findElement(By.xpath("//button[normalize-space()='Save']")).click();
        driver.findElement(By.id("HyperLink1")).click();
        driver.findElement(By.id("MainContent_btnAddNewProposal")).click();
        driver.findElement(By.id("ClientDropDownDiv")).click();
        driver.findElement(By.xpath("//li[text()='Atul auto pvt ltd']")).click();
        Thread.sleep(2000);
        JavascriptExecutor js = (JavascriptExecutor) driver;          //Method to scroll vertically
        js.executeScript("window.scrollBy(0,200)");
        driver.findElement(By.xpath("//input[@id='ExpiryDateInput']")).click();
        System.out.println("calender gets opened");

        Thread.sleep(2000);
        driver.findElement(By.xpath("//i[@class='chevron right icon']")).click(); //Click right button to change the month

        driver.findElement(By.xpath("//div[contains(@class,'calendar') and contains(@class,'visible')]//td[text()='1' and contains(@class,'link')]" )).click();
        driver.findElement(By.xpath("//input[@type='submit']")).click(); //click on Next button











        // driver.findElement(By.id("ExpiryDateInput")).sendKeys("07/2/2025"); // Adjust format if needed


//        while (true){                                                   //Applied condition for selecting date
//            String month = driver.findElement(By.xpath("//div[@class= 'ui input left icon w-80']")).getText();
//            String year =driver.findElement(By.xpath("//span[@class='ui-datepicker-year']")).getText();
//            System.out.println("month::::"+month);
//            System.out.println("year::::"+year);
//
//            if(year.equals("2020")&& month.equalsIgnoreCase("january")){
//                driver.findElement(By.xpath("//a[@data-date='1']")).click();
//                break;
//            }
//            else{
//                driver.findElement(By.xpath("//i[@class="chevron left icon"]")).click();
//            }                                                           // Keep on clicking back button till the desired date is not visible
//        }


    }

}

