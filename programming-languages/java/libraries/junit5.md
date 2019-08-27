# JUnit 5

## Parameterised Tests

-   A tutorial -
    <https://blog.codefx.org/libraries/junit-5-parameterized-tests/>.

-   Some examples from Excel library,

    ```java
    static List<ExcelWriter> getTestWorkbookWriters() {
        val streaming = testWriter().isStreaming(true).build();
        val nonStreaming = testWriter().isStreaming(false).build();

        return Arrays.asList(streaming, nonStreaming);
    }

    @ParameterizedTest
    @MethodSource("getTestWorkbookWriters")
    void testSimpleWritesOfOscars(ExcelWriter writer) {
        val sheetWriter = writer.getRowDataWriter("Oscars");

        sheetWriter.writeRow(Arrays.asList("Name", "Year", "Movie"));
        sheetWriter.writeRow(Arrays.asList("Warner Baxter", 1929, "In Old Arizona"));

        ExcelSheetWriter sw = (ExcelSheetWriter) sheetWriter;
        val sheet = sw.getSheet();
        assertEquals(5, sheet.getLastRowNum() + 1); // number of rows = last row num (zero based) + 1
    }
    ```

> - TODO: To test exceptions

JUnit parameterised tests still feel quite constrained compared to
flexible ScalaTest etc. Thus for a big Java project, it might be worth
looking at Groovy based [Spock framework](http://spockframework.org/)
for testing.
