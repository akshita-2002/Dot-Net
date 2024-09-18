- bUnit is used for UI testing
- bUnit is used for testing blazor project

- Fact attribute
[Fact]
The Fact attribute is used to mark a method as a test method. It signifies that the method represents a fact that should always be true.

A test marked with the Fact attribute represents a single test case.
If the test method throws an exception or fails an assertion, the test is considered failed.
using Xunit;
```c#
public class MathTests
{
    [Fact]
    public void Add_TwoPlusTwo_ReturnsFour()
    {
        // Arrange
        var calculator = new Calculator();

        // Act
        var result = calculator.Add(2, 2);

        // Assert
        Assert.Equal(4, result);
    }
}
```

- Theory attribute

[Theory]
The Theory attribute is used to define a parametrized test. It allows testing multiple inputs against the same test logic.
You provide one or more data sources (via attributes like InlineData, MemberData, etc.) to supply the test with different input values.
Each set of input values is treated as a separate test case.
If any of the test cases fail, the entire theory is considered failed.
using Xunit;

```c#
public class MathTests
{
    [Theory]
    [InlineData(2, 3, 5)]
    [InlineData(0, 0, 0)]
    [InlineData(-1, 1, 0)]
    public void Add_ValidInputs_ReturnsCorrectResult(int a, int b, int expected)
    {
        // Arrange
        var calculator = new Calculator();

        // Act
        var result = calculator.Add(a, b);

        // Assert
        Assert.Equal(expected, result);
    }
}
```


# AAA(Arrange Act Assert)

- The Arrange section of a unit test method initializes objects and sets the value of the data that is passed to the method under test.

- The Act section invokes the method under test with the arranged parameters.

- The Assert section verifies that the action of the method under test behaves as expected. For .NET, methods in the Assert class are often used for verification.



# CODE COVERAGE

- quantifies the extent to which the source code of a program is tested
- Statement Coverage : Measures whether each line of code is executed.
- Branch Coverage : Measures whether each possible branch (true/false) from each decision point is executed.
- Function Coverage : Measures whether each function or subroutine in the code is called.
- Condition Coverage : Measures whether each Boolean sub-expression is evaluated to both true and false.
- Path Coverage : Measures whether all possible paths through the code are executed.
- Line Coverage : Measures the number of executed lines divided by the total number of lines.
- Loop Coverage : Measures whether loops are executed and how many times.



