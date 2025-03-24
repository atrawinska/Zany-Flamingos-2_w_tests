
We discovered after submission that there were problems with symlink so the file couldn't be opened. Thus we wanted to send another repository with the same files.
The main branch has up to date code but the tests are in the work branch (also in the main repository we went). We had some problems with files this time and couldn't make it on time.
https://github.com/atrawinska/school_app


# Project Responsibilities

## Team Members and Their Responsibilities

### Agnieszka Alicja Trawinska
- *JSON Reading and Saving*
- *Password Hashing*
- *Student and Teacher*
  - Views
  - ViewModels
  - Models
- *Subject Model*

### Mikolaj Kluba
- *Login and Role Selection*
  - Views
  - ViewModels
  - Models
- *Unit Tests*


# Test Descriptions

## Enrollment Rules Test
- *Objective*: Ensure that a student cannot be enrolled in the same subject more than once.
- *Steps*:
  1. Create a student and a subject.
  2. Simulate the enrollment process.
  3. Verify that if the student is already enrolled in the subject, a second enrollment is prevented.
  4. Confirm that the student’s enrolled subject list contains the subject only once.
- *Additional test fails on purpose to show how it could catch a potential mistake of student enroling twice for the same course*

## Data Persistence Test
- *Objective*: Verify that data saved and loaded matches the expected number of entries.
- *Steps*:
  1. Create a list of student objects.
  2. Save the list using the JsonReader.SaveData method.
  3. Load the data back with JsonReader.ReadData.
  4. Assert that the number of students read matches the number saved.
  - *Note*: In a production test, consider using dependency injection to override file paths to prevent tests from affecting actual data.

## Access Control Test
- *Objective*: Ensure that only the assigned teacher can modify the subject.
- *Steps*:
  1. Create two teacher objects.
  2. Assign a subject to teacherA.
  3. Simulate that teacherB should not be allowed to modify the subject because the subject’s teacher ID does not match `teacherB`’s ID.
  4. This check forms the basis of an access control rule in the business logic.
