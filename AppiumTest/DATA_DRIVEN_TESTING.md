# Data-Driven Testing with Appium

This project demonstrates data-driven testing using TestNG's DataProvider feature with multiple data formats.

## Test Files Created

### 1. SecondTest.java

- Contains data-driven login tests
- Uses TestNG's `@DataProvider` annotation
- Tests multiple login scenarios with different data sets
- Includes validation for both successful and failed login attempts

### 2. Data Files

- **CSV Format**: `src/test/resources/login_data.csv`
- **JSON Format**: `src/test/resources/login_data.json`
- **Excel Format**: `src/test/resources/login_data.xlsx`

### 3. Utility Class

- `CSVDataReader.java`: Utility class to read CSV data files

## How to Run

### Run the data-driven test:

```bash
mvn test -Dtest=SecondTest
```

### Run all tests:

```bash
mvn test
```

## Test Data Structure

Each test case contains:

- **Email**: Test email address
- **Password**: Test password
- **Expected Result**: "success" or "failure"
- **Description**: Human-readable description of the test case

## Test Scenarios Covered

1. ✅ Valid login credentials
2. ❌ Invalid password
3. ❌ Invalid email format
4. ✅ Multiple valid users
5. ❌ Password too short
6. ❌ Empty email field
7. ❌ Empty password field

## Key Features

- **Data-driven**: Tests run with multiple data sets automatically
- **Parameterized**: Each test execution shows which data set is being tested
- **Flexible**: Easy to add new test data without changing code
- **Comprehensive**: Tests both positive and negative scenarios
- **Detailed Reporting**: Each test case shows expected vs actual results

## Customization

To add more test cases:

1. Edit the CSV file and add new rows
2. Or modify the CSVDataReader to use JSON/Excel formats
3. Tests will automatically pick up the new data

## Notes

- Each test method gets a fresh app instance (using `@BeforeMethod`)
- App is reset between tests to ensure clean state
- Validation logic can be customized based on your app's behavior
- Timeouts and waits are configurable
