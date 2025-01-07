# Competitor Management System

This repository contains the source code, documentation, and resources for the **Competitor Management System**, developed as part of the module **5CS019 Object-Oriented Design and Programming** at the University of Wolverhampton.

## Overview
The Competitor Management System is a Java-based application designed to manage competitor details for various competitions (e.g., archery, eSports). The system includes functionality to store competitor details in a MySQL database, calculate performance scores, and generate comprehensive reports.

## Features
- **Competitor Management**: Add, update, and retrieve competitor details.
- **Database Integration**: Stores data in a MySQL database using JDBC.
- **Performance Analysis**: Calculates and displays performance scores based on competition data.
- **Reports**: Generates detailed and summary reports of competitors, including:
  - Full details of each competitor.
  - Details of the top performer.
  - Statistical summaries (e.g., frequency of scores).
- **User Interaction**: Retrieves competitor information based on user input.
- **Error Handling**: Handles invalid data and database connection issues gracefully.

---

## Project Structure

```plaintext
├── src
│   ├── models
│   │   ├── Competitor.java
│   │   ├── Name.java
│   ├── services
│   │   ├── CompetitorList.java
│   │   ├── Manager.java
│   ├── App.java
├── resources
│   ├── database
│   │   ├── CompetitionDB.sql
│   ├── diagrams
│   │   ├── class-diagram.pdf
├── test
│   ├── CompetitorTest.java
│   ├── CompetitorListTest.java
├── docs
│   ├── Javadoc
│   │   ├── index.html
├── README.md
```

---

## Instructions for Use

### Prerequisites
- **Java Development Kit (JDK)**: Version 8 or higher.
- **MySQL**: Ensure you have MySQL installed and running.
- **JDBC Driver**: Ensure the appropriate MySQL JDBC driver is configured.

### Setting Up the Database
1. Create a MySQL database named `CompetitionDB`.
2. Execute the `CompetitionDB.sql` script located in the `resources/database` folder to set up the `Competitors` table.
3. Update database connection settings in the `Manager.java` file:
   ```java
   private static final String DB_URL = "jdbc:mysql://localhost:3306/CompetitionDB";
   private static final String USER = "your_username";
   private static final String PASSWORD = "your_password";
   ```

### Running the Application
1. Clone this repository:
   ```bash
   git clone https://github.com/devrahulbanjara/Competitor-Management-System.git
   ```
2. Navigate to the project directory:
   ```bash
   cd Competitor-Management-System
   ```
3. Compile the application:
   ```bash
   javac -d bin src/**/*.java
   ```
4. Run the application:
   ```bash
   java -cp bin App
   ```

### Testing
- Unit tests are included in the `test` folder.
- Run the tests using a testing framework like JUnit:
   ```bash
   java -cp bin:lib/junit-4.13.2.jar org.junit.runner.JUnitCore test.CompetitorTest
   ```

---

## Submission Requirements

### Deliverables
- **Code**: Fully functional Java code implementing the requirements.
- **Reports**:
  - Design decisions.
  - Known bugs and limitations.
  - Tests performed.
- **Diagrams**: Class diagrams showing instance variables, methods, and relationships.
- **Javadoc Documentation**: Include generated HTML files.

### Packaging for Submission
1. Create a folder containing:
   - Source code (`src` folder).
   - Class diagrams (`resources/diagrams`).
   - Database SQL script (`resources/database/CompetitionDB.sql`).
   - Reports.
   - Javadoc documentation (`docs/Javadoc`).
2. Compress the folder into a `.zip` file.
3. Submit the `.zip` file to Canvas.

---

## Example Outputs

### Example Competitor Data
| Competitor ID | Name         | Level         | Scores       | Overall Score |
|---------------|--------------|---------------|--------------|---------------|
| 200           | Alice Green  | Beginner      | 4, 3, 5, 2, 4 | 3.6           |
| 201           | Bob Brown    | Intermediate  | 3, 4, 4, 5, 4 | 4.0           |
| 202           | Carol White  | Advanced      | 5, 5, 4, 4, 5 | 4.6           |
| 203           | David Black  | Advanced      | 4, 4, 5, 5, 4 | 4.4           |

### Reports
#### Competitor Table
```
Competitor ID Name         Level        Scores         Overall
200           Alice Green  Beginner     4,3,5,2,4      3.6
201           Bob Brown    Intermediate 3,4,4,5,4      4.0
202           Carol White  Advanced     5,5,4,4,5      4.6
203           David Black  Advanced     4,4,5,5,4      4.4
```
#### Top Performer
```
Competitor with the highest score: Carol White with an overall score of 4.6
```
#### Summary Statistics
```
Total competitors: 4
Frequency of individual scores:
Score:    2   3   4   5
Frequency: 1   6   10  7
```

---

## Known Bugs and Limitations
- The system assumes valid input for simplicity.
- Additional error handling and validation may be required for production use.

---

## License
This project is licensed under the MIT License. See the `LICENSE` file for more details.

---

## Author
- **Rahul Banjara**
- Module Leader: Dr. Adeel Rafiq
- University of Wolverhampton, Faculty of Science and Engineering
