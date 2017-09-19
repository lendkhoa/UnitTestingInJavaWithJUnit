# Unit testing in java with JUnit
> Kansas city, Sep 19, 2017

- Packaged as a single jar file

## Annotation

- @BeforeClass (1 time each must be static)
    - execute method before any tests are executed
- @AfterClass (1 time each must be static etc clean up the database)
    - executes methods after all tests are executed
- @Ignore

## Exception testing
- @Test(expected=Exception.class)
    - if we set the expected field equal to an exception class, the test will
    only pass if an exception of that type is thrown.

```
    @Test(expected = InvalidGoalException.class) 
    public void testThrowException() throws InvalidGoalException {
        classUnderTest.setGoal(-1);
    }
```

## Timing out @Test(timeout=100)
- Test network connection.
- Make the test to fail if it takes too long and blocks other tests

```
    @Test(timeout=100)
```

## Assertions
- assertArrayEquals
- assertEquals
- assertTrue
- assertFalse
- assertNull
- assertNotNull
- assertSame
- assertNotSame
- fail

## Test Suites
- Run a selected test classes together
- Eclipse will use the **Suite.class** runner that is built 
into the IDE to run.
- use @IncludeCategory to include test class
- use @ExcludeCategory to exclude test class

```
    import org.junit.runners.Suite;
    import org.junit.runner.RunWith;

    @IncludeCategory(className.class)
    @ExcludeCategory(className.class)
    @RunWith(Suite.class)
    @Suite.SuiteClasses({LibraryTest.class})

    public class TestSuite {
        
    }
```

## Category
- In JUnit we can add @Category to any test class or test method
- Inheritance does apply to category -> can apply hierarchies
- Create a category in Eclipse is by creating an interface
    - Then use the interface at the @Category
    ```
        @Category(interfaceName.class)
    ```

## Parameterized Tests
