
<p align="center">
  <img src="LOGO.png" alt="SketchMatch Logo" width="250"/>
</p>

# SketchMatch-Forensic Face Sketch Construction and Recognition  
**(My B.E. Final Year Project)**

## 📁 SOURCE CODE  
[Download Source Code](https://drive.google.com/drive/folders/1P1n0r9g0GNnU01YvyujoYcedxA0vzk0c)  
> **Note**: Please mention the purpose for which you need the source code in the message box.

## 🛠️ How to Run the Project

The project includes two major modules:

---

### 🔹 Part 1: Face Sketch Construction (`SketchMatch v2`)

This module allows users to create composite face sketches using a drag-and-drop interface built in JavaFX.

**Requirements:**

- Java JDK 8: [Download](https://www.oracle.com/in/java/technologies/javase/javase-jdk8-downloads.html)  
- IntelliJ IDEA: [Download](https://www.jetbrains.com/idea/download/)  
- JavaFX SDK: [Download](https://gluonhq.com/products/javafx/)  
- JavaFX Scene Builder: [Download](https://gluonhq.com/products/scene-builder/)  
- DB Browser for SQLite: [Download](https://sqlitebrowser.org/dl/)

---

**Setup in IntelliJ IDEA:**

1. **Clone the Repository**:
   - Open IntelliJ IDEA and select "Get from Version Control" → Paste the GitHub link.

2. **Configure JDK and JavaFX**:
   - File → Project Structure → Project SDK → Add Java 8.
   - Under "Libraries", click "+" → Java → Add JavaFX SDK’s `/lib` folder.

3. **Add VM Options for JavaFX**:  
   Go to:
   ```
   Run > Edit Configurations > VM options:
   ```
   Add:
   ```bash
   --module-path "path-to-javafx-sdk/lib" --add-modules javafx.controls,javafx.fxml
   ```

4. **Set up Scene Builder**:
   - Install Scene Builder and link `.fxml` files to open in it (Right-click → Open in Scene Builder).

5. **Import External JARs**:
   - File → Project Structure → Modules → Dependencies → Click `+` → JARs or directories → Select all `.jar` files from `SketchMatch v2/lib`.

6. **Configure the SQLite Database**:
   - Use DB Browser to open `login.sqlite` inside the project directory.
   - Add your user credentials to enable OTP-based login.

7. **Update Email Credentials**:
   - Open `Login_screenController.java` → Line 144.
   - Enter your Gmail credentials to send OTP.
   - Ensure "Less Secure Apps" is enabled in your Gmail settings.

8. **Adjust File Paths (Optional)**:
   - In `dashboard_controller.java`, Line 508, update any hardcoded file paths as per your system setup.

9. **Run the Application**:
   - Click the green "Run" button or press `Shift + F10`.
   - Log in using email + OTP, then navigate to “Create Sketch”.

---

### 🔹 Part 2: Face Sketch Recognition (`SketchMatch_FaceMatch`)

This module performs facial matching against a dataset using **AWS Rekognition**.

**Requirements:**

- AWS Free Tier account  
- AWS CLI: [Install](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html)

---

**Setup Instructions:**

1. **Create AWS Account**:
   - Sign up at [AWS Free Tier](https://aws.amazon.com/free/) and activate your account.

2. **Create IAM User with Programmatic Access**:
   - Give full access to Amazon S3 and Rekognition.

3. **Configure AWS CLI**:
   - Run `aws configure` in terminal and enter:
     - Access Key
     - Secret Key
     - Region (e.g., `us-east-1`)

4. **Setup AWS S3 & Rekognition**:
   - Create an S3 bucket.
   - Open and run `collection_create.java` in IntelliJ to create a Rekognition collection.
   - Use `collection_add_image.java` to upload and index reference images.

5. **Match Sketches**:
   - Open and run `collection_search_face.java` to match the sketches drawn in Part 1 with the database.


## 📄 DESCRIPTION / ABSTRACT  

In forensic science, hand-drawn face sketches are still limited and time-consuming when integrated with modern technologies used for criminal recognition and identification.  
This project presents a **standalone application** that enables users to:

- Create composite face sketches of suspects using a **drag-and-drop interface**, eliminating the need for professional forensic artists.
- Automatically match the created sketches with a police face database using **deep learning algorithms** and **cloud infrastructure** for **fast and efficient identification**.

---

## 📚 PUBLISHED TECHNICAL PAPER  
Read the official technical paper published in IJIT Journal:  
👉 [Read the Technical Paper](https://ijcrt.org/papers/IJCRT2504722.pdf)

---
