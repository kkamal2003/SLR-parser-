# SLR Parser Web Application

This project implements an **SLR (Simple LR) Parser** using Python and the **Streamlit** framework. It provides a web-based interface that allows users to input a **context-free grammar (CFG)** and a sequence of **tokens**, then processes the input through the SLR parsing algorithm. The application visualizes the parsing process, showing the construction of the **FIRST** and **FOLLOW** sets, the **parsing table**, and the step-by-step parsing results.

## Features

- **Grammar Input**: Enter a context-free grammar in standard form (e.g., `S -> A B | C`).
- **Token Input**: Provide a sequence of tokens (e.g., `a b`).
- **SLR Parsing Process**: Visualize the parsing process step-by-step.
- **FIRST and FOLLOW Sets**: Displays the computed FIRST and FOLLOW sets for the grammar.
- **Parsing Table**: Shows the SLR parsing table, which guides the parser’s decisions.
- **Interactive Interface**: User-friendly web interface with error handling and real-time feedback.
- **Error Handling**: Provides detailed messages if the input format is incorrect.

## Requirements

- Python 3.7+
- Streamlit
- Graphviz
- pandas (for data manipulation)
- Required libraries can be installed via `requirements.txt`.

## Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/kkamal2003/SLR-parser.git
    cd slr-parser
    ```

2. Create a virtual environment and activate it:
    ```bash
    python3 -m venv venv
    source venv/bin/activate  # On Windows: venv\Scripts\activate
    ```

3. Install dependencies:
    ```bash
    pip install -r requirements.txt
    ```

## Usage

### Running the Application

To run the Streamlit app, execute the following command:

```bash
streamlit run app.py
```

After running this command, a local server will be created, and you can access the application in your web browser (usually at `http://localhost:8501`). Follow the instructions on the interface to enter your grammar and tokens, and view the parsing results.

## Code Structure

This code includes both the core SLR parsing logic and the Streamlit-based web interface. Below is a breakdown of the key functions:

1. **Core SLR Parsing Logic**:
    - **`items`**: Constructs LR(0) items, which form the basis for the SLR parsing states.
    - **`construct_table`**: Generates the SLR parse table using the computed LR(0) items and the FIRST and FOLLOW sets.
    - **`LR_parser`**: Parses an input string, showing the sequence of actions (shift, reduce, or accept) at each step, and logs any errors or conflicts.

2. **Streamlit Interface**:
    - The Streamlit app provides fields to input the grammar and tokens, displays the FIRST and FOLLOW sets, the parse table, and shows a step-by-step parsing log for the entered tokens.

3. **Grammar Analysis**:
    - The application computes **FIRST** and **FOLLOW** sets from the input grammar, crucial for constructing the SLR parsing table.

## Example

To parse an expression such as `id + id * id`, follow these steps in the application:

1. **Enter Grammar**: Input grammar in the appropriate text box in CFG format.
2. **Provide Tokens**: Input tokens such as `id + id * id` in the token input field.
3. **View Results**: The app will display the FIRST and FOLLOW sets, the constructed parsing table, and a detailed parsing log.

The output shows each parsing action, including shifts, reduces, and any errors or conflicts that may arise during parsing.

## Troubleshooting

- **Incorrect Grammar Format**: Ensure that the grammar follows the CFG standard format. The app provides feedback on format errors.
- **Conflicts**: If the parsing table has conflicts (e.g., shift/reduce conflicts), the app will report them in the log.
- **Unrecognized Symbols**: If the input contains symbols not present in the grammar, the app will indicate these as errors.

## Additional Information

This application is useful for visualizing the SLR parsing process, ideal for students and developers interested in understanding parser construction and grammar analysis.

---

This README file gives a comprehensive overview of the SLR Parser Web Application, covering installation, usage, features, and troubleshooting.