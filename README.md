# Documenting Your Applications: Strategies and Examples  In English 

## 1. Self-Describing Code

## Definition
Self-describing code is a practice in programming where the names of methods, functions, variables, and classes are chosen to be clear and descriptive. This means that the names themselves provide an understanding of what the code does without requiring additional comments or documentation.

#### Example
Consider the task of writing a function to validate email addresses. A self-describing name for this function would be `validateEmailAddress`. This name immediately informs the reader of its purpose.

```python
def validateEmailAddress(email):
    # Check if the email contains an '@' symbol
    if '@' in email:
        return True
    return False
```

## Purpose
The primary purpose of self-describing code is to enhance code readability and maintainability. Here are several specific benefits:

1. **Improved Readability**: When code is easy to read, it is easier to understand. Descriptive names act as documentation that explains what the code does.
2. **Easier Maintenance**: When other developers (or even your future self) need to work on the code, they can quickly grasp the functionality without needing to decipher cryptic names or search for additional documentation.
3. **Reduced Need for Comments**: While comments are useful, they can become outdated if not maintained properly. Self-describing names remain accurate as long as the code structure remains consistent with the names.
4. **Enhanced Collaboration**: Clear code fosters better collaboration among team members, as everyone can understand and contribute to the codebase more effectively.

#### Detailed Explanation with Examples

##### Variables
Use meaningful variable names that convey the purpose of the variable.

**Poor Example:**
```python
x = 10
y = 20
z = x + y
```

**Good Example:**
```python
numberOfApples = 10
numberOfOranges = 20
totalFruits = numberOfApples + numberOfOranges
```

In the good example, the variable names clearly indicate what each value represents, making the code easier to understand.

##### Functions/Methods
Name functions and methods based on the action they perform.

**Poor Example:**
```python
def proc(data):
    # process data
    pass
```

**Good Example:**
```python
def processData(data):
    # process data
    pass
```

The good example tells us that the function processes data, making the code more intuitive.

##### Classes
Class names should represent the objects or concepts they model.

**Poor Example:**
```python
class D:
    pass
```

**Good Example:**
```python
class Document:
    pass
```

The good example clearly indicates that the class represents a document.

##### Constants
Constants should be named to indicate their purpose and should be written in uppercase with words separated by underscores.

**Poor Example:**
```python
pi = 3.14159
```

**Good Example:**
```python
PI = 3.14159
```




### Next.js (JavaScript/TypeScript)
```javascript
// Function to fetch user data from an API
async function fetchUserData(userId) {
    const response = await fetch(`/api/users/${userId}`);
    const data = await response.json();
    return data;
}

// Component to display user profile
function UserProfile({ user }) {
    return (
        <div className="user-profile">
            <h1>{user.name}</h1>
            <p>Email: {user.email}</p>
        </div>
    );
}
```

### Python
```python
def calculate_average(numbers):
    """
    Calculate the average of a list of numbers.
    
    Parameters:
    numbers (list of float): A list of numbers.
    
    Returns:
    float: The average of the numbers.
    """
    return sum(numbers) / len(numbers)
```

### Flutter (Dart)
```dart
// Function to validate an email address
bool isValidEmail(String email) {
  return RegExp(r'^[^@]+@[^@]+\.[^@]+').hasMatch(email);
}

// Widget to display a user's profile
class UserProfile extends StatelessWidget {
  final String name;
  final String email;

  UserProfile({required this.name, required this.email});

  @override
  Widget build(BuildContext context) {
    return Column(
      children: [
        Text(name, style: TextStyle(fontSize: 24)),
        Text(email, style: TextStyle(fontSize: 16)),
      ],
    );
  }
}
```

## 2. Inline Comments

- **Definition:** Place comments within the code to explain specific decisions, logic, or functions.
- **Usage:** Use inline comments to provide context or rationale for complex or non-obvious parts of the code.
- **Balance:** Avoid over-commenting; include enough to explain critical parts without cluttering the code.



Inline comments provide additional context where necessary. Avoid over-commenting; include enough to explain critical parts without cluttering the code.

### Next.js
```javascript
async function fetchUserData(userId) {
    // Fetch user data from the API
    const response = await fetch(`/api/users/${userId}`);
    
    // Parse the response as JSON
    const data = await response.json();
    
    return data;
}
```

### Python
```python
def calculate_average(numbers):
    """
    Calculate the average of a list of numbers.
    """
    # Sum the numbers and divide by the count
    return sum(numbers) / len(numbers)
```

### Flutter
```dart
bool isValidEmail(String email) {
  // Regular expression to check if the email is valid
  return RegExp(r'^[^@]+@[^@]+\.[^@]+').hasMatch(email);
}

class UserProfile extends StatelessWidget {
  final String name;
  final String email;

  UserProfile({required this.name, required this.email});

  @override
  Widget build(BuildContext context) {
    // Display the user's name and email
    return Column(
      children: [
        Text(name, style: TextStyle(fontSize: 24)),
        Text(email, style: TextStyle(fontSize: 16)),
      ],
    );
  }
}
```

## 3. GitHub Comments

- **Definition:** Use commit messages and pull request descriptions to document changes and reasons for those changes.
- **Purpose:** Provides a historical context and reasoning for changes, which is useful for tracking the evolution of the codebase.



Using commit messages and pull request descriptions to document changes and reasons for those changes provides historical context and rationale for changes.

#### Commit Message Examples
- **Next.js**: `git commit -m "Add fetchUserData function to handle API requests"`
- **Python**: `git commit -m "Implement calculate_average function to compute the average of a list"`
- **Flutter**: `git commit -m "Create UserProfile widget to display user details"`

#### Pull Request Description Example
- **Next.js**: 
  ```markdown
  ## Summary
  This PR adds a new function, `fetchUserData`, to fetch user data from the API. It also includes a `UserProfile` component to display the user's information.

  ## Changes
  - Added `fetchUserData` function in `utils/api.js`
  - Created `UserProfile` component in `components/UserProfile.js`

  ## Test Plan
  - Verified that the `fetchUserData` function correctly fetches data from the API.
  - Ensured that the `UserProfile` component displays the fetched data correctly.
  ```

## 4. External Documentation

- **External Documentation**
  - **Definition:** Create a comprehensive document (using tools like Google Docs) that describes the application's architecture, major functionalities, and design choices.
  - **Structure:**
    - **Introduction:** Overview of the application and its purpose.
    - **Architecture:** Detailed explanation of the system's architecture.
    - **Functionality:** Breakdown of major functions or modules.
    - **Design Decisions:** Explanation of why certain design choices were made, especially if they are complex or non-standard.
    - **Accessibility:** Ensure this document is easily accessible to all team members.

  - **Example:** For a sample of such documentation, see this [Google Docs Example](https://docs.google.com/document/d/1VSYOIBKA_9jR1sDVQPjxYS7cSEdNGsrPtCj-nxrBBsg/edit?usp=sharing).








Creating a comprehensive document (using tools like Google Docs) that describes the application's architecture, major functionalities, and design choices ensures that your code remains maintainable, understandable, and easier to work with for current and future developers.


### Example (Google Docs)
```txt
Project Documentation

Overview
This project is a user management application built with Next.js. It allows administrators to manage user profiles.

Architecture
- Pages: Contains the main application pages.
- Components: Reusable UI components.
- Utils: Utility functions for API calls and data processing.

Major Functionalities
Fetch User Data
The `fetchUserData` function in `utils/api.js` is responsible for fetching user data from the API. It takes a `userId` as a parameter and returns the user data in JSON format.

Display User Profile
The `UserProfile` component in `components/UserProfile.js` displays the user's name and email. It receives a `user` object as a prop.

Design Decisions
- API Structure: The decision to use `/api/users/:id` was made to keep the API endpoint RESTful.
- Component Design: The `UserProfile` component was designed as a functional component to simplify state management.

```

**Example:** For a sample of such documentation, see this [Google Docs Example](https://docs.google.com/document/d/1VSYOIBKA_9jR1sDVQPjxYS7cSEdNGsrPtCj-nxrBBsg/edit?usp=sharing) and this [YouTube Video](https://youtu.be/ce4ZbsAovl4?si=vbK3jqW_z1cBnNzF).

###################################################################################################

# مستند کردن برنامه‌های خود: استراتژی‌ها و مثال‌ها به فارسی
## ۱. کد خودتوضیحی

## تعریف
کد خودتوضیحی یک روش در برنامه‌نویسی است که در آن نام‌های متدها، توابع، متغیرها و کلاس‌ها به صورت واضح و توصیفی انتخاب می‌شوند. این بدان معناست که نام‌ها خودشان توضیح می‌دهند که کد چه کاری انجام می‌دهد، بدون نیاز به توضیحات یا مستندات اضافی.

#### مثال
وظیفه نوشتن یک تابع برای اعتبارسنجی آدرس‌های ایمیل را در نظر بگیرید. یک نام خودتوضیحی برای این تابع می‌تواند `validateEmailAddress` باشد. این نام بلافاصله هدف آن را به خواننده اطلاع می‌دهد.

```python
def validateEmailAddress(email):
    # Check if the email contains an '@' symbol
    if '@' in email:
        return True
    return False
```

## هدف
هدف اصلی کد خودتوضیحی افزایش خوانایی و قابلیت نگهداری کد است. در اینجا چندین مزیت خاص آورده شده است:

۱. **بهبود خوانایی**: وقتی کد خواندنش آسان باشد، درک آن نیز آسان‌تر است. نام‌های توصیفی مانند مستندات عمل می‌کنند که توضیح می‌دهند کد چه کاری انجام می‌دهد.

۲. **نگهداری آسان‌تر**: وقتی دیگر توسعه‌دهندگان (یا حتی خود شما در آینده) نیاز به کار روی کد دارند، می‌توانند به سرعت عملکرد را بدون نیاز به رمزگشایی نام‌های مبهم یا جستجو برای مستندات اضافی درک کنند.

۳. **نیاز کمتر به توضیحات**: در حالی که توضیحات مفید هستند، اگر به درستی نگهداری نشوند می‌توانند قدیمی شوند. نام‌های خودتوضیحی تا زمانی که ساختار کد با نام‌ها سازگار باشد، دقیق باقی می‌مانند.

۴. **افزایش همکاری**: کد واضح همکاری بهتری بین اعضای تیم ایجاد می‌کند، زیرا همه می‌توانند کد را درک کرده و به طور موثر به کدبیس کمک کنند.

#### توضیح کامل با مثال‌ها

##### متغیرها
از نام‌های متغیر معنی‌دار استفاده کنید که هدف متغیر را نشان می‌دهند.

**مثال بد:**
```python
x = 10
y = 20
z = x + y
```

**مثال خوب:**
```python
numberOfApples = 10
numberOfOranges = 20
totalFruits = numberOfApples + numberOfOranges
```

در مثال خوب، نام‌های متغیر به وضوح نشان می‌دهند که هر مقدار چه چیزی را نمایندگی می‌کند، و این باعث می‌شود کد راحت‌تر درک شود.

##### توابع/متدها
نام توابع و متدها را بر اساس عملی که انجام می‌دهند انتخاب کنید.

**مثال بد:**
```python
def proc(data):
    # process data
    pass
```

**مثال خوب:**
```python
def processData(data):
    # process data
    pass
```

مثال خوب به ما می‌گوید که تابع داده‌ها را پردازش می‌کند، و این باعث می‌شود کد بیشتر قابل درک باشد.

##### کلاس‌ها
نام کلاس‌ها باید نمایانگر اشیاء یا مفاهیمی باشند که مدل می‌کنند.

**مثال بد:**
```python
class D:
    pass
```

**مثال خوب:**
```python
class Document:
    pass
```

مثال خوب به وضوح نشان می‌دهد که کلاس نمایانگر یک سند است.

##### ثوابت
ثوابت باید طوری نامگذاری شوند که هدف آن‌ها را نشان دهند و باید با حروف بزرگ و کلمات جدا شده با زیرخط نوشته شوند.

**مثال بد:**
```python
pi = 3.14159
```

**مثال خوب:**
```python
PI = 3.14159
```

### Next.js (JavaScript/TypeScript)
```javascript
// Function to fetch user data from an API
async function fetchUserData(userId) {
    const response = await fetch(`/api/users/${userId}`);
    const data = await response.json();
    return data;
}

// Component to display user profile
function UserProfile({ user }) {
    return (
        <div className="user-profile">
            <h1>{user.name}</h1>
            <p>Email: {user.email}</p>
        </div>
    );
}
```

### Python
```python
def calculate_average(numbers):
    """
    Calculate the average of a list of numbers.
    
    Parameters:
    numbers (list of float): A list of numbers.
    
    Returns:
    float: The average of the numbers.
    """
    return sum(numbers) / len(numbers)
```

### Flutter (Dart)
```dart
// Function to validate an email address
bool isValidEmail(String email) {
  return RegExp(r'^[^@]+@[^@]+\.[^@]+').hasMatch(email);
}

// Widget to display a user's profile
class UserProfile extends StatelessWidget {
  final String name;
  final String email;

  UserProfile({required this.name, required this.email});

  @override
  Widget build(BuildContext context) {
    return Column(
      children: [
        Text(name, style: TextStyle(fontSize: 24)),
        Text(email, style: TextStyle(fontSize: 16)),
      ],
    );
  }
}
```

## ۲. توضیحات خطی

- **تعریف:** قرار دادن توضیحات درون کد برای توضیح تصمیمات خاص، منطق یا توابع.
- **استفاده:** از توضیحات خطی برای ارائه زمینه یا دلایل برای بخش‌های پیچیده یا غیر واضح کد استفاده کنید.
- **تعادل:** از توضیح بیش از حد پرهیز کنید؛ به اندازه کافی توضیحات برای توضیح قسمت‌های بحرانی بدون ایجاد شلوغی در کد اضافه کنید.

توضیحات خطی در جایی که لازم است زمینه اضافی فراهم می‌کنند. از توضیح بیش از حد پرهیز کنید؛ به اندازه کافی توضیحات برای توضیح قسمت‌های بحرانی بدون ایجاد شلوغی در کد اضافه کنید.

### Next.js
```javascript
async function fetchUserData(userId) {
    // Fetch user data from the API
    const response = await fetch(`/api/users/${userId}`);
    
    // Parse the response as JSON
    const data = await response.json();
    
    return data;
}
```

### Python
```python
def calculate_average(numbers):
    """
    Calculate the average of a list of numbers.
    """
    // Sum the numbers and divide by the count
    return sum(numbers) / len(numbers)
```

### Flutter
```dart
bool isValidEmail(String email) {
  // Regular expression to check if the email is valid
  return RegExp(r'^[^@]+@[^@]+\.[^@]+').hasMatch(email);
}

class UserProfile extends StatelessWidget {
  final String name;
  final String email;

  UserProfile({required this.name, required this.email});

  @override
  Widget build(BuildContext context) {
    // Display the user's name and email
    return Column(
      children: [
        Text(name, style: TextStyle(fontSize: 24)),
        Text(email, style: TextStyle(fontSize: 16)),
      ],
    );
  }
}
```

## ۳. توضیحات GitHub

- **تعریف:** استفاده از پیام‌های کامیت و توضیحات درخواست‌های کششی برای مستند کردن تغییرات و دلایل آن‌ها.
- **هدف:** فراهم کردن زمینه تاریخی و دلیل برای تغییرات، که برای ردیابی تکامل کدبیس مفید است.

استفاده از پیام‌های کامیت و توضیحات درخواست‌های کششی برای مستند کردن تغییرات و دلایل آن‌ها زمینه تاریخی و دلیل برای تغییرات فراهم می‌کند.

#### مثال‌های پیام کامیت
- **Next.js**: `git commit -m "Add fetchUserData function to handle API requests"`
- **Python**: `git commit -m "Implement calculate_average function to compute the average of a list"`
- **Flutter**: `git commit -m "Create UserProfile widget to display user details"`

#### مثال توضیحات درخواست کششی
- **Next.js**: 
  ```markdown
  ## Summary
  This PR adds a new function, `fetchUserData`, to fetch user data from the API. It also includes a `UserProfile` component to display the user's information.

  ## Changes
  - Added `fetchUserData` function in `utils/api.js`
  - Created `UserProfile` component in `components/UserProfile.js`

  ## Test Plan
  - Verified that the `fetchUserData` function correctly fetches data from the API.
  - Ensured that the `UserProfile` component displays the fetched data correctly.
  ```

## ۴. مستندات خارجی

- **مستندات خارجی**
  - **تعریف:** ایجاد یک سند جامع (با استفاده از ابزارهایی مانند Google Docs) که معماری برنامه، عملکردهای اصلی و انتخاب‌های طراحی را توصیف می‌کند.
  - **ساختار:**
    - **مقدمه:** نمای کلی از برنامه و هدف آن.
    - **معماری:** توضیح دقیق معماری سیستم.
    - **عملکرد:** تجزیه و تحلیل عملکردهای اصلی یا ماژول‌ها.
    - **تصمیمات طراحی:** توضیح اینکه چرا انتخاب‌های طراحی خاصی انجام شده‌اند، به ویژه اگر پیچیده یا غیر معمول باشند.
    - **دسترسی:** اطمینان حاصل کنید که این سند به راحتی برای همه اعضای تیم قابل دسترسی است.

  - **مثال:** برای نمونه‌ای از چنین مستنداتی، این [مثال Google Docs](https://docs.google.com/document/d/1VSYOIBKA_9jR1sDVQPjxYS7cSEdNGsrPtCj-nxrBBsg/edit?usp=sharing) را ببینید.

ایجاد یک سند جامع (با استفاده از ابزارهایی مانند Google Docs) که معماری برنامه، عملکردهای اصلی و انتخاب‌های طراحی را توصیف می‌کند، اطمینان می‌دهد که کد شما قابل نگهداری، قابل فهم و برای توسعه‌دهندگان فعلی و آینده راحت‌تر کار خواهد بود.

### مثال (Google Docs)
```txt
Project Documentation

Overview
This project is a user management application built with Next.js. It allows administrators to manage user profiles.

Architecture
- Pages: Contains the main application pages.
- Components: Reusable UI components.
- Utils: Utility functions for API calls and data processing.

Major Functionalities
Fetch User Data
The `fetchUserData` function in `utils/api.js` is responsible for fetching user data from the API. It takes a `userId` as a parameter and returns the user data in JSON format.

Display User Profile
The `UserProfile` component in `components/UserProfile.js` displays the user's name and email. It receives a `user` object as a prop.

Design Decisions
- API Structure: The decision to use `/api/users/:id` was made to keep the API endpoint RESTful.
- Component Design: The `UserProfile` component was designed as a functional component to simplify state management.
```

**Example:** For a sample of such documentation, see this [Google Docs Example](https://docs.google.com/document/d/1VSYOIBKA_9jR1sDVQPjxYS7cSEdNGsrPtCj-nxrBBsg/edit?usp=sharing) and this [YouTube Video](https://youtu.be/ce4ZbsAovl4?si=vbK3jqW_z1cBnNzF).
