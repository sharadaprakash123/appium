Setting Up Appium Configuration
Launch the Appium GUI application. Click Android icon and enter these details:

App Path — browse to the .apk location under the app folder
Platform Name — select Android
Automation Name — select Appium
Platform Version — select 5.1 Lollipop (API Level 22) from the drop-down
Once the preceding settings are done, click on the General Settings icon and choose the following settings:

Select Pre-launch Application
Select Strict Capabilities
Select Override Existing Sessions
Select Kill Processes Using Server Port Before Launch
Select New Command Timeout and enter the value 7200.

Also, you need to install your application on the emulator. You can use the emulator from Android Studio. When it is done — launch the Appium server.

When you start the Appium app, you will see icons at the top. I highlighted the Appium Inspector in red.

When you click on the highlighted icon (Appium Inspector), it will open a new window with the application UI state capture.

Click on any element on the right panel to find the details about it. After clicking Details you will see a group of attributes listed for the selected element:

You might notice the attribute “resource-id” and the value of id attribute. It can be used as an identifier for the element in your tests.

Step 1: Create a Gradle-project and add required dependencies for JUnit, Appium, Cucumber, and log4J to your “build.gradle” file. The current “build.gradle” and the source code of the project .

Step 2: Add Cucumber plugin and create “.feature” file.

Step 3: Create steps definition. Press Alt+Enter to show the Create Step Definition intention action. Select the target step definition file from the pop-up list.

Step 4: Every testing scenario should be executed on some specific testing environment. The desired capabilities for the mobile emulator for Android and iOS:

Step 5: Now we need to add the page with elements and methods using Page Object Pattern:

Step 6: Cucumber has a very interesting feature called hooks. They help us execute a block of code before or/and after each scenario. Add them:
Step 9: Since we want to use the JUnit framework to run Cucumber, we need to create the class:

package io.testproject.appium.pom.tests.pages;
import io.appium.java_client.android.AndroidDriver;
import io.appium.java_client.android.AndroidElement;
import io.appium.java_client.android.AndroidKeyCode;
import io.appium.java_client.pagefactory.AndroidFindBy;
import io.appium.java_client.pagefactory.AppiumFieldDecorator;
import org.openqa.selenium.support.PageFactory;
