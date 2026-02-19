Project Overview — what the calculator does and its three feature areas in a formatted table
Key Concepts Used — all Python concepts covered (type casting, loops, functions, lists, etc.)
Step-by-Step Guide — a 10-step numbered table walking through exactly how to build the project from scratch (setup → imports → helpers → each feature → testing → running)
Project Structure — a visual file tree showing how the code is organized
Functions Explained — a plain-English description of every function and what it does
Sample Output — a real example session showing the statistics feature in action
Possible Enhancements — ideas to extend the project further

<?xml version="1.0" encoding="UTF-8"?>
<project>

  <metadata>
    <name>Python Advanced Calculator</name>
    <filename>untitled2.py</filename>
    <origin>Google Colab</origin>
    <language>Python</language>
    <version>1.0</version>
    <type>Console Application</type>
    <description>
      A menu-driven command-line calculator built in Python that supports
      basic arithmetic operations, percentage calculations, and statistical
      analysis including mean, median, mode, and more.
    </description>
  </metadata>

  <dependencies>
    <library>
      <name>statistics</name>
      <type>built-in</type>
      <purpose>Provides mean() and median() functions for statistical calculations</purpose>
    </library>
    <library>
      <name>collections.Counter</name>
      <type>built-in</type>
      <purpose>Counts frequency of each number to determine mode</purpose>
    </library>
  </dependencies>

  <features>
    <feature id="1">
      <title>Basic Arithmetic</title>
      <operations>
        <operation symbol="+">Addition</operation>
        <operation symbol="-">Subtraction</operation>
        <operation symbol="*">Multiplication</operation>
        <operation symbol="/">Division</operation>
      </operations>
      <notes>
        Handles division by zero gracefully with a user-friendly error message.
        Uses eval() safely since both operands are pre-validated floats.
      </notes>
    </feature>

    <feature id="2">
      <title>Percentage Calculator</title>
      <modes>
        <mode id="2.1">
          <name>Percent of a Number</name>
          <formula>(percentage / 100) * number</formula>
          <example>20% of 150 = 30</example>
        </mode>
        <mode id="2.2">
          <name>What Percent is A of B</name>
          <formula>(A / B) * 100</formula>
          <example>30 of 150 = 20%</example>
        </mode>
        <mode id="2.3">
          <name>Percentage Increase or Decrease</name>
          <formula>((new - old) / abs(old)) * 100</formula>
          <example>100 to 120 = +20% increase</example>
        </mode>
      </modes>
    </feature>

    <feature id="3">
      <title>Statistics</title>
      <operations>
        <operation id="3.1">
          <name>Mean / Average</name>
          <method>statistics.mean(nums)</method>
          <description>Sum of all values divided by the count of values</description>
        </operation>
        <operation id="3.2">
          <name>Median</name>
          <method>statistics.median(nums)</method>
          <description>Middle value when numbers are sorted; average of two middles for even count</description>
        </operation>
        <operation id="3.3">
          <name>Mode</name>
          <method>Counter(nums)</method>
          <description>Most frequently occurring value(s); reports "No mode" if all values are unique</description>
        </operation>
        <operation id="3.4">
          <name>All Statistics</name>
          <description>Runs Mean, Median, Mode together plus Sum, Min, Max, and Count</description>
        </operation>
      </operations>
    </feature>
  </features>

  <functions>
    <function>
      <name>get_number(prompt)</name>
      <returns>float</returns>
      <description>
        Prompts the user for input and type-casts it to float.
        Loops indefinitely until a valid numeric value is entered.
        Handles ValueError on invalid input.
      </description>
    </function>

    <function>
      <name>get_numbers_list()</name>
      <returns>list[float]</returns>
      <description>
        Collects multiple numbers from the user one at a time.
        User types "done" to finish. Requires at least one valid entry.
        Each entry is type-cast to float with error handling.
      </description>
    </function>

    <function>
      <name>divider()</name>
      <returns>None</returns>
      <description>Prints a decorative horizontal line of 42 dashes for UI formatting.</description>
    </function>

    <function>
      <name>header(title)</name>
      <returns>None</returns>
      <description>Prints a formatted section header wrapped between two dividers.</description>
    </function>

    <function>
      <name>basic_arithmetic()</name>
      <returns>None</returns>
      <description>
        Handles the arithmetic menu flow. Collects two numbers and an operator,
        validates input, and prints the result.
      </description>
    </function>

    <function>
      <name>percentage_menu()</name>
      <returns>None</returns>
      <description>
        Handles the percentage calculation menu. Presents three sub-modes,
        collects necessary inputs, and displays formatted results.
      </description>
    </function>

    <function>
      <name>statistics_menu()</name>
      <returns>None</returns>
      <description>
        Handles the statistics menu. Collects a dataset from the user,
        then computes and displays the selected statistical measures.
      </description>
    </function>

    <function>
      <name>main()</name>
      <returns>None</returns>
      <description>
        Entry point. Displays the main menu in a loop, routes to the correct
        feature function based on user choice, and exits on option 4.
      </description>
    </function>
  </functions>

  <input_handling>
    <typecasting>
      <from>str</from>
      <to>float</to>
      <method>float(input(prompt))</method>
      <error_handling>ValueError caught with user-friendly re-prompt</error_handling>
    </typecasting>
    <validation>
      <rule>Division by zero is checked before evaluation</rule>
      <rule>Percentage base (B) cannot be zero</rule>
      <rule>Original value in % change cannot be zero</rule>
      <rule>Statistics list requires at least one number</rule>
      <rule>Menu choices are validated against allowed options</rule>
    </validation>
  </input_handling>

  <program_flow>
    <step order="1">Program starts at __main__ guard</step>
    <step order="2">main() displays the main menu</step>
    <step order="3">User selects a feature (1, 2, or 3)</step>
    <step order="4">Corresponding function is called</step>
    <step order="5">User provides inputs via get_number() or get_numbers_list()</step>
    <step order="6">Result is calculated and printed</step>
    <step order="7">User presses Enter to return to the main menu</step>
    <step order="8">Loop repeats until user selects option 4 (Exit)</step>
  </program_flow>

  <error_handling>
    <case>
      <trigger>Non-numeric input for a number prompt</trigger>
      <response>ValueError caught; user is re-prompted</response>
    </case>
    <case>
      <trigger>Division by zero</trigger>
      <response>Checked before eval(); prints warning and returns early</response>
    </case>
    <case>
      <trigger>All dataset values are unique (mode)</trigger>
      <response>Prints "No mode (all values appear equally)"</response>
    </case>
    <case>
      <trigger>Invalid menu selection</trigger>
      <response>Prints warning; returns to main menu</response>
    </case>
    <case>
      <trigger>Empty dataset in statistics</trigger>
      <response>User must enter at least one number before proceeding</response>
    </case>
  </error_handling>

  <strengths>
    <strength>Clean modular design — each feature is an isolated function</strength>
    <strength>Robust input validation with type casting and error handling</strength>
    <strength>Supports multi-mode statistics in a single pass</strength>
    <strength>Handles edge cases like zero division and no-mode datasets</strength>
    <strength>User-friendly console UI with dividers, prompts, and symbols</strength>
    <strength>Uses only Python built-in libraries — no external dependencies</strength>
  </strengths>

  <possible_enhancements>
    <enhancement>Add history log to track previous calculations</enhancement>
    <enhancement>Support standard deviation and variance in statistics</enhancement>
    <enhancement>Add exponentiation and square root to arithmetic</enhancement>
    <enhancement>Export results to a .txt or .csv file</enhancement>
    <enhancement>Build a GUI version using tkinter or a web version with Flask</enhancement>
  </possible_enhancements>

</project>

