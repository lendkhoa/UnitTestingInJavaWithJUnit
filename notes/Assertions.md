# JUnit: Advance Assertions
> Kansas Sep 20, 2017

## AssertThat([value],[matcherstatement])
- matcher statement
    - for ex all the statements in the collection 
    contain a string witht text 'high' in them.
- Import hamcrest matcher (similar to jasmine)

```
import static org.hamcrest.CoreMatchers.*;
import static org.junit.matchers.JUnitMatchers;

assertThat(action(), is(10));
assertThat(lib.addNumber(input), allOf(is(expected), instanceOf(Integer.class)));

```

## Using Expected Exception
```
    @Rule
    public ExpectedException thrown = ExpectedException.none();

    @Test
    public void test() throws someException {
        thrown.expect(someException.class);
        thrown.expectMessage(containString()); // check contain specific word
    }
```

## Rule
- a Hook to specify the before and after test action

**Samples**
- TemporaryFolder
- ExternalResource
- ErrorCollector
- Verifier
- TestWatcher
- TestName
- Timeout (can be set for an entire set of test)
- ExpectedException
- RuleChain

**The rule is applied to the entire class**
```
@Rule
public Timeout timeout = Timeout.millis(1);

```