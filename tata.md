# Function Analysis
| Function Name | Input Parameters | Output Parameters | Purpose |
| --- | --- | --- | --- |
| userExists | String username | boolean | Check if a user exists in the database |
| readFile | String filename | String | Read the contents of a file |
| doStuff | int a, int b | int | Perform an unclear operation on two integers |
| printUpperCase | String s | None | Print a string in uppercase |
| encryptPassword | String password | String | Encrypt a password (not actually implemented) |

# Risk Analysis
| Code | Explanation | Proposed Modification |
| --- | --- | --- |
| `private static String DB_PASS = "password";` | Hardcoded password is a security issue | Use environment variables or a secure secrets manager to store sensitive credentials |
| `String sql = "SELECT * FROM users WHERE username = '\" + username + "'";` | SQL Injection vulnerability | Use prepared statements with parameterized queries to prevent SQL injection |
| `// reader.close(); // Bug: resource not closed` | Resource not closed, potential memory leak | Close resources in a finally block or use try-with-resources statement |
| `catch(IOException e) { // Silently ignore errors }` | Silently ignoring errors, potential issues | Log or handle exceptions properly to ensure error visibility and debugging |
| `if(a > 100) return b / (a - 100); // possible divide by zero` | Possible divide by zero error | Add a check for division by zero and handle it accordingly |
| `System.out.println(s.toUpperCase());` | Null dereference risk | Check for null before calling methods on an object |
| `// TODO: Implement encryption (never done)` | Encryption not implemented, potential security issue | Implement encryption as intended to ensure secure password storage |

# Maintainability Analysis
| Function Name | Maintainability Issues |
| --- | --- |
| userExists | Poor code structure and organization, Inconsistent naming conventions, Violation of SOLID principles |
| readFile | Poor code structure and organization, Inconsistent naming conventions, Low readability, Violation of SOLID principles |
| doStuff | Poor code structure and organization, Inconsistent naming conventions, Low readability, Violation of SOLID principles, Code Duplication |
| printUpperCase | Poor code structure and organization, Inconsistent naming conventions, Low readability, Violation of SOLID principles |
| encryptPassword | Poor code structure and organization, Inconsistent naming conventions, Low readability, Violation of SOLID principles, Code Duplication |